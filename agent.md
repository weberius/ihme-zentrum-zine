# Arbeitsregeln für KI-Agenten in diesem Projekt

Diese Datei richtet sich an Claude (oder andere KI-Agenten), die in diesem Ordner arbeiten – nicht an menschliche Leser:innen (dafür gibt es `README.md`). Sie enthält feste, vorausschauende Regeln, die zu Sitzungsbeginn gelten sollen, bevor inhaltlich etwas verändert wird. Anders als `projekt.md` (beschreibt den aktuellen Inhalt der Broschüre) und `herausforderungen.md` (dokumentiert rückblickend aufgetretene Probleme) ist dies eine Regelsammlung, die unabhängig vom jeweiligen Stand des Projekts gilt.

## Feste Projektregeln

- **Bilder immer verknüpft, nie eingebettet.** In `projekt.md` unter „Druckspezifikation" festgelegt: „Bilder sind relativ (verknüpft, nicht eingebettet) im Dokument referenziert, sodass die Projektstruktur stabil bleibt." Beim Austausch oder Ersetzen eines Bildes im Affinity-Dokument ist das über die native Programmoberfläche zu tun (z. B. „Bild ersetzen"), NICHT über den Skript-Befehl `ReplaceBitmap` – dieser bettet die Pixel fest ein.
- **Originaldateien im `images/`-Ordner nicht löschen oder überschreiben**, auch wenn sie im Dokument nicht mehr referenziert werden (z. B. `title.jpg`, das durch `title2.jpg` ersetzt wurde, aber unverändert im Ordner bleibt).
- **Druckspezifikation einhalten:** DIN A5 hoch, Drahtheftung, Endformat 148 × 210 mm, Datenformat inkl. Beschnitt 154 × 216 mm, Beschnitt 3 mm umlaufend, Farbraum CMYK mit mindestens 300 dpi, 16 Seiten. Details siehe `projekt.md`.
- **Seitenzahlen (Seite 4–14) und der dreispaltige Text auf Seite 4 sind statische, einzeln positionierte Objekte**, keine automatisierten Master-Seiten-Felder bzw. kein echtes Grundlinienraster (technische Gründe siehe unten). Bei Verschiebungen der Seitenreihenfolge müssen diese Objekte von Hand nachgezogen werden.
- **Der dateiname der Affinity-Datei trägt aktuell die Doppel-Endung `.afpub.af`** (siehe „Offene Punkte" in `projekt.md`) – beim Umbenennen vorsichtig sein, da die zugehörige `~lock~`-Datei und ggf. Skript-Pfade davon abhängen.

## Bekannte technische Grenzen der Affinity-Skript-Schnittstelle

Ausführlich dokumentiert in `herausforderungen.md`. Kurzfassung, um wiederholtes Ausprobieren zu vermeiden:

- Keine Skript-API zum Anlegen neuer Master-Seiten (nur Lesezugriff auf bestehende).
- Keine Skript-API für automatische Seitenzahl-Felder.
- Kein dokumentweites Grundlinienraster und keine Spalteneinstellung an Textrahmen per Skript setzbar.
- Skript-Dateizugriff (`Bitmap.loadFromFile` u. Ä.) funktioniert **nur innerhalb des Desktop-Ordners** des Nutzers (`app.userDesktopPath`), nicht im Projektordner selbst – auch nicht, wenn dieser über die Gerätebrücke verbunden ist. Workaround: native Dateiauswahl der Programmoberfläche nutzen (funktioniert projektordnerweit) oder Datei einmalig auf den Desktop kopieren.
- Das Werkzeug `search_sdk_hints` ist unzuverlässig (liefert unabhängig von der Anfrage einen Fehler) – stattdessen `list_sdk_documentation` / `read_sdk_documentation_topic` und gezieltes Durchsuchen der Dokumentation verwenden.
- Nach einem blockierenden nativen Dialog (z. B. `app.chooseFile()`) kann die Skript-Engine ihren Sitzungszustand verlieren („preamble not read"-Fehler) – einfach die Präambel erneut lesen und danach das Dokument per Skript auf Konsistenz prüfen (`Document.current`, Seitenzahl).

## Arbeitsweise

- Vor jeder inhaltlichen Änderung `projekt.md` erneut querlesen, insbesondere „Druckspezifikation" und „Offene Punkte" – nicht nur einmal zu Sitzungsbeginn.
- Änderungen am Affinity-Dokument nach der Umsetzung per `render_spread`/`render_selection` visuell verifizieren und bei Positions-/Größenangaben mit einem kurzen Kontroll-Skript gegenprüfen.
- Bei einer bereits bekannten SDK-Grenze (siehe oben) nicht mehrfach experimentieren, sondern zügig auf einen dokumentierten Workaround wechseln oder beim Nutzer nachfragen, bevor riskante Alternativen (z. B. ferngesteuerte UI-Bedienung) versucht werden.
- Bei ferngesteuerter UI-Bedienung besonders vorsichtig sein: Seitenpaneele (z. B. Master-Seiten-Panel) reagieren erfahrungsgemäß unzuverlässig auf einzelne Klicks; Tastenkombinationen wie `Cmd+W` oder `Cmd+J` können unbeabsichtigte Wirkung haben (Dokument schließen, Objekt duplizieren) – nach jeder Aktion Screenshot prüfen und im Zweifel sofort `Cmd+Z`.
- Nach jeder inhaltlichen Änderung `projekt.md` aktualisieren: Versionsnummer im Frontmatter hochzählen, betroffene Abschnitte (Seitenstruktur, Quellen, Offene Punkte, Bildmaterial) aktuell halten, und einen Log-Eintrag mit Datum und knapper Beschreibung ergänzen. **Dabei immer auch den auslösenden Prompt (den Wortlaut der Nutzer-Nachricht, die zu dieser Änderung geführt hat) im Kapitel „Prompts" ergänzen, mit Verweis auf die zugehörige Log-Versionsnummer** – „Prompts" und „Log" werden gemeinsam gepflegt, nie nur eines von beiden.
- Das Projekt liegt in einem lokalen Git-Repository. Commits sind bisher nicht zu jeder Version erfolgt – vor einem Commit im Zweifel beim Nutzer nachfragen, ob und wann committet werden soll.

## Dateiübersicht

Eine inhaltliche Übersicht über das Projekt und alle Dateien im Ordner steht in `README.md` (für Menschen). Der aktuelle Stand der Broschüre steht in `projekt.md`.
