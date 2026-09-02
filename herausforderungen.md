# Herausforderungen bei der Arbeit mit Affinity Publisher per Skript-Schnittstelle

Dieses Dokument sammelt die technischen Probleme, die während der Arbeit an der Broschüre „Ihme Zentrum Hannover" wiederholt aufgetreten sind, zusammen mit möglichen Lösungsansätzen und Umgehungsmöglichkeiten. Es ergänzt `projekt.md` und dient als Referenz, damit dieselben Probleme in künftigen Sitzungen schneller erkannt und gelöst werden können.

## 1. Zugriff auf Bilder im Projektordner aus Skripten heraus nicht möglich

**Problem:** Die Affinity-Skript-Schnittstelle (`execute_script`) darf laut eigener Dokumentation nur auf Dateien im Desktop-Ordner des Nutzers zugreifen (`app.userDesktopPath`), nicht auf beliebige andere Ordner – auch nicht auf den eigentlichen, per Gerätebrücke verbundenen Projektordner `ihme-zentrum-zine/images`, obwohl die Bilder dort nachweislich liegen und für das Dokument selbst (über normale Verknüpfungen) sichtbar sind. Ein Versuch, `Bitmap.loadFromFile()` direkt mit einem Pfad im Projektordner aufzurufen, schlug mit `PERMISSION_DENIED` fehl.

**Konkretes Beispiel:** Beim Austausch des Titelbilds (`title.jpg` → `title2.jpg`, siehe Log 0.9) konnte das neue Bild nicht per Skript geladen werden.

**Lösungsszenarien:**

- **Umgehung über die native Programmoberfläche (empfohlen, hat funktioniert):** Statt eines Skript-Aufrufs die eingebauten Affinity-Bedienelemente nutzen (z. B. „Bild ersetzen" im Werkzeug-Panel), die einen normalen macOS-Dateidialog öffnen. Dieser Dateidialog unterliegt nicht der Skript-Sandbox, sondern der regulären App-Berechtigung, und kann daher auf den gesamten Projektordner zugreifen. Erfordert Bildschirm-/Fernsteuerungszugriff auf den Rechner.
- **Datei temporär auf den Desktop kopieren:** Die Zieldatei einmalig auf den Desktop-Ordner kopieren (z. B. durch den Nutzer selbst per Finder, oder mit expliziter Ordner-Freigabe für den Desktop-Ordner), das Skript mit dem Desktop-Pfad ausführen, anschließend die Kopie wieder löschen. Funktioniert vollautomatisch per Skript, erfordert aber einmalig eine Zugriffsfreigabe bzw. manuelles Kopieren.
- **Frühzeitig prüfen statt experimentieren:** Vor einem Bildzugriff per Skript die SDK-Präambel (`read_sdk_documentation_topic('preamble')`) konsultieren – dort steht die Desktop-Beschränkung bereits explizit vermerkt. Spart einen fehlschlagenden Versuch.

## 2. Fehlende Skript-Funktionen der Affinity-SDK

**Problem:** Für mehrere Layout-Funktionen bietet die Affinity-Skript-Schnittstelle schlicht keine API an – sie sind ausschließlich über die Programmoberfläche bedienbar:

- Neue Master-Seiten anlegen (nur Lesezugriff auf bestehende Master, keine Erstellung)
- Automatische Seitenzahl-Felder einfügen
- Ein dokumentweites Grundlinienraster setzen
- Spaltenanzahl eines Textrahmens setzen

**Konkretes Beispiel:** Seitenzahlen auf Seite 4–14 (Log 0.6) und der dreispaltige Text auf Seite 4 (Log 0.7) mussten deshalb als statische, einzeln positionierte Textrahmen nachgebildet werden, nicht als „echte" Master-Seiten-/Grundlinienraster-Funktionen.

**Lösungsszenarien:**

- **Nachbildung per Skript (bereits angewendet):** Die gewünschte Optik durch mehrere einzelne, exakt positionierte Objekte mit identischen Werten (z. B. fester `absoluteLeading` für einen einheitlichen Grundlinien-Rhythmus über mehrere Textrahmen) erzeugen. Nachteil: Bei späteren Layoutänderungen (z. B. Verschieben von Seiten) müssen diese Objekte manuell nachgezogen werden, da sie nicht automatisch mitlaufen wie eine echte Master-Seite oder ein echtes Feld.
- **Manueller Nachbau in der Programmoberfläche:** Der Nutzer baut die Funktion direkt in Affinity Publisher nach (Master-Seiten-Panel, „Dokument einrichten" für Grundlinienraster, Textrahmen-Eigenschaften für Spalten). Wurde in dieser Sitzung als Option angeboten, aber zugunsten der Skript-Nachbildung nicht gewählt.
- **Ferngesteuerte UI-Bedienung:** Diese Funktionen per Bildschirmzugriff und Klicks/Tastatur nachstellen. Erwies sich in dieser Sitzung als fehleranfällig (siehe Abschnitt 3) und wurde deshalb nicht für diese Fälle eingesetzt.
- **Vor Arbeitsbeginn abklären:** Bei Aufgaben, die typische DTP-Funktionen (Master, Grundlinienraster, Spalten, automatische Feldinhalte) betreffen, vorab kurz sondieren, ob die SDK das überhaupt unterstützt, um unnötige Iterationen zu vermeiden – und bei Bedarf direkt fragen, ob eine Nachbildung per Skript oder eine manuelle Lösung gewünscht ist.

## 3. Instabile bzw. abbrechende Skript-Ausführung

**Problem:** Mehrere technische Störungen traten unabhängig vom eigentlichen Skriptinhalt auf:

- Nach einem blockierenden Aufruf (z. B. `app.chooseFile()`, das einen nativen Dateidialog öffnet und auf Nutzereingabe wartet) brach die Verbindung mit „Device did not respond within 60s" ab; ein anschließender Skriptaufruf schlug mit „The preamble documentation topic has not yet been read" fehl, obwohl die Präambel zu Beginn der Sitzung bereits gelesen worden war – der interne Zustand der Skript-Engine ging offenbar verloren und musste durch erneutes Lesen der Präambel zurückgesetzt werden.
- Das Werkzeug `search_sdk_hints` lieferte bei jedem Aufruf unabhängig von der Suchanfrage denselben Fehler (`[json.exception.type_error.302] type must be string, but is null`) und war damit durchgehend unbenutzbar.

**Lösungsszenarien:**

- **Blockierende Dialoge im Skript vermeiden:** Keine Skript-Aufrufe verwenden, die native, auf Nutzereingabe wartende Dialoge öffnen (`chooseFile`, `alert`, `confirm`, `prompt` und deren Async-Varianten), wenn eine synchrone Antwort erwartet wird – das Risiko eines Timeouts und eines dadurch gestörten Sitzungszustands ist hoch. Stattdessen auf Datei-Dialoge über die reguläre Programmoberfläche ausweichen (siehe Abschnitt 1).
- **Bei „preamble not read"-Fehler:** Einfach `read_sdk_documentation_topic('preamble')` erneut aufrufen und das Skript danach wiederholen – das hat in dieser Sitzung zuverlässig funktioniert und deutet auf einen reinen Sitzungszustand-Reset hin, nicht auf einen Dokumentschaden. Nach einem solchen Vorfall sicherheitshalber per Skript prüfen, ob `Document.current` noch das erwartete Dokument mit der erwarteten Seitenzahl ist.
- **`search_sdk_hints` als unzuverlässig einstufen:** Nicht mehrfach mit unterschiedlichen Suchbegriffen erneut versuchen, sondern direkt auf `list_sdk_documentation` und `read_sdk_documentation_topic` sowie gezieltes Durchsuchen (grep) der Dateien ausweichen.
- **Nach jeder Änderung verifizieren:** Änderungen konsequent per `render_spread`/`render_selection` und durch kurze Kontroll-Skripte (z. B. Vergleich von Positions- und Größenwerten vor/nach einer Änderung) prüfen, bevor sie als abgeschlossen gelten – so wurden in dieser Sitzung mehrfach Fehler frühzeitig erkannt und korrigiert (u. a. eine versehentliche Objektverdopplung nach `Cmd+J`, ein versehentlich geschlossenes Dokumentfenster nach `Cmd+W`).

## 4. Vorgaben aus `projekt.md` wurden nicht immer vor der Umsetzung geprüft

**Problem:** Bei einer technischen Umsetzung wurde zunächst eine Methode gewählt, die einer bereits in `projekt.md` festgehaltenen Vorgabe widersprach, weil `projekt.md` vor der Wahl der Methode nicht erneut konsultiert wurde.

**Konkretes Beispiel:** Beim Austausch des Titelbilds (Log 0.9) wurde zunächst versucht, das neue Bild per Skript-Befehl `ReplaceBitmap` einzusetzen. Das hätte das Bild jedoch fest eingebettet, obwohl in `projekt.md` unter „Druckspezifikation" ausdrücklich steht: „Bilder sind relativ (verknüpft, nicht eingebettet) im Dokument referenziert, sodass die Projektstruktur stabil bleibt." Erst der Hinweis von Wolfram führte zur Korrektur (Umsetzung über die native „Bild ersetzen"-Funktion, die die Verknüpfung erhält).

**Lösungsszenarien:**

- **`projekt.md` vor jeder inhaltlichen Änderung gezielt querlesen** – insbesondere die Abschnitte „Druckspezifikation" und „Offene Punkte" –, nicht nur einmal zu Sitzungsbeginn. Besonders bei bildbezogenen und layoutbezogenen Aufgaben.
- **Kurze Vorgaben-Checkliste ableiten:** Feste, projektweite Konventionen aus `projekt.md` (z. B. „verknüpft, nicht eingebettet", CMYK/300 dpi, Maße für Beschnitt/Sicherheitsabstand) als kurze Prüfpunkte vor jeder passenden Aktion heranziehen, bevor eine Umsetzungsmethode gewählt wird.
- **Bei Unsicherheit gezielt nachschlagen statt raten:** Vor der Wahl einer Skript-Methode kurz per Stichwortsuche (grep) in `projekt.md` prüfen, ob es dazu bereits eine Festlegung gibt, statt sich allein auf die naheliegendste technische Lösung zu verlassen.

## Allgemeine Empfehlung für künftige Sitzungen

- SDK-Präambel und relevante Dokumentationsdateien zu Beginn einer neuen Aufgabe erneut sichten, statt sich auf frühere Kenntnisse aus vorherigen Sitzungen zu verlassen (die Skript-Engine kann zwischen Sitzungen zurückgesetzt sein).
- Bei erkannten SDK-Grenzen (Abschnitt 2) nicht wiederholt experimentieren, sondern zügig auf eine der dokumentierten Umgehungen wechseln oder aktiv nachfragen.
- Vor jeder bild- oder layoutbezogenen Änderung kurz in `projekt.md` prüfen, ob es dazu bereits eine Festlegung gibt.
- Änderungen grundsätzlich per Rendering und Kontroll-Skript verifizieren, bevor sie als erledigt gelten.
