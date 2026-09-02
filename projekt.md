---
titel: "Ihme Zentrum Hannover"
thema: "Fotografische Dokumentation des Ihme-Zentrums in Hannover im Sommer 2026"
zielgruppe: "Menschen mit Interesse an Architektur und Stadtentwicklung, (ehemalige) Bewohner:innen und Nutzer:innen des Ihme-Zentrums, an Hannover und Brutalismus/Großstrukturen der 1970er interessierte Betrachter:innen"
typ: "Broschüre (Drahtheftung, DIN A5 hoch, 16 Seiten)"
kernidee: "Wenn jemand das Heft zuklappt, soll er vor allem die vielschichtige, ambivalente Atmosphäre des Ihme-Zentrums gesehen haben – zwischen Verfall, Aneignung, Graffiti und urbaner Alltagsnutzung."
version: "0.16"
datum_erstellung: 2026-09-01
datum_aktualisierung: 2026-09-01
---

# Ihme Zentrum Hannover – Projektbeschreibung

Dieses Dokument beschreibt die konkreten Inhalte und den aktuellen Stand der Broschüre, die gemeinsam mit Claude in Affinity erstellt wird. Es ergänzt die Meta-Informationen im Frontmatter oben und dient als Referenz für spätere Überarbeitungen. Wiederkehrende technische Probleme bei der Arbeit mit der Affinity-Skript-Schnittstelle und mögliche Lösungen/Umgehungen sind separat in `herausforderungen.md` festgehalten. Feste, vorausschauende Arbeitsregeln für KI-Agenten, die an diesem Projekt weiterarbeiten, stehen in `agent.md`. Eine schnelle inhaltliche Übersicht für Menschen bietet `README.md`.

## Druckspezifikation

- Format: DIN A5 hoch, Drahtheftung
- Endformat: 148 × 210 mm
- Datenformat (inkl. Beschnitt): 154 × 216 mm
- Beschnitt: 3 mm umlaufend, Sicherheitsabstand 3 mm
- Farbraum: CMYK, mindestens 300 dpi
- Umfang: 16 Seiten
- Bilder sind relativ (verknüpft, nicht eingebettet) im Dokument referenziert, sodass die Projektstruktur stabil bleibt

## Seitenstruktur (Stand: aktuelle Version)

| Seite | Inhalt |
|---|---|
| 1 | Vorderseite des Umschlags – Titelbild `title2.jpg`, randlos beginnend links, mit weißem Rand rechts und vertikal von unten nach oben verlaufendem Titel „Ihme Zentrum Hannover" |
| 2 | leer |
| 3 | Schmutztitel, rechtsbündig in der oberen Hälfte: „Ihme Zentrum" (Titel), „Promenadologische Betrachtungen" (Unterzeile), „Hannover 2026" (Datumszeile) – bewusst ohne Namensnennung; der Autor wird erst im Impressum auf Seite 15 genannt |
| 4 | Einleitungstext zum Ihme-Zentrum in drei Absätzen: (1) Zusammenfassung des Wikipedia-Artikels zum Ihme-Zentrum (Geschichte, Architektur, Niedergang, aktueller Status); (2) Synthese aus dem Ihme-Zentrum-Artikel und den Grundgedanken der Promenadologie (Spaziergangswissenschaft) von Lucius Burckhardt – ohne diese namentlich zu nennen –, die die Kluft zwischen geplanter und begangener/erlebter Stadt herausarbeitet; (3) Bezug zu den Fotografien der Broschüre. Textbox in Blocksatz, in Größe und Position identisch mit den Fotoboxen der Fotostrecke (128 × 160 mm, 10 mm Rand links, 25 mm oben) |
| 4–14 | Seitenzahlen jeweils außen (Seite 4, 6, 8, 10, 12, 14 unten links; Seite 5, 7, 9, 11, 13 unten rechts), 10 mm vom seitlichen Rand, 15 mm über dem unteren Blattschnitt |
| 4 | Einleitungstext dreispaltig gesetzt (ein Absatz je Spalte, Blocksatz mit Silbentrennung), Spalten mit festem, einheitlichem Zeilenabstand (Grundlinien-Rhythmus über alle drei Spalten hinweg) |
| 5–14 | Fotostrecke: `ihme-01.jpg` bis `ihme-10.jpg`, in dieser Reihenfolge, jeweils ganzseitig mit 10 mm Rand links/rechts, vertikal zentriert entsprechend dem eigenen Seitenverhältnis des Bildes |
| 15 | leer, am unteren Rand Impressum-Hinweis: Autor „Wolfram Eberius", Webseite `https://wolfram.eberius.photography`, Literaturangaben (Wikipedia-Artikel „Ihme-Zentrum" und „Promenadologie"); unterer Rand des Textblocks auf gleicher Höhe wie unterer Rand der Fotoboxen (185 mm) |
| 16 | Rückseite des Umschlags – Fortsetzung von `title2.jpg` (bildet zusammen mit Seite 1 im aufgeklappten Zustand ein durchgehendes Motiv) |

Hinweis: `ihme-11.jpg` wurde bewusst aus der Broschüre entfernt.

## Offene Punkte

- Dateiname der Affinity-Datei trägt noch die Doppel-Endung `.afpub.af` (entstanden durch einen manuellen Speichervorgang außerhalb der Skript-Sandbox); Umbenennung auf `.afpub` steht noch aus
- Seitenzahlen (Seite 4–14) sind feste Textrahmen, kein Master mit automatischem Seitenzahl-Feld (siehe Log 0.6) – bei Bedarf später in Affinity Publisher direkt als Master nachbauen
- Dreispaltiger Text auf Seite 4 (siehe Log 0.7) ebenso als einzelne, exakt ausgerichtete Textrahmen statt echtem Grundlinienraster – bei Bedarf später direkt in Affinity Publisher nachbauen
- In Affinity Publisher steht noch ein hängengebliebener „Sektionsassistent"-Dialog offen (unkritisch, einfach schließen)
- Bildreihenfolge (Seite 5–14): Das Wandbild (`ihme-07.jpg`, Seite 11) liegt im Heft vier Seiten von der Treppenhaus-Aufnahme (`ihme-03.jpg`, Seite 7) entfernt, obwohl der dritte Absatz auf Seite 4 „ein Wandbild neben verlassenen Treppenhäusern" beschreibt – siehe Abschnitt „Bildreihenfolge" unten für die vollständige Einschätzung

## Quellen

- Einleitungstext (Seite 4), erster Absatz (Geschichte/Fakten): https://de.wikipedia.org/wiki/Ihme-Zentrum
- Zweiter Absatz (Synthese): verarbeitet zusätzlich https://de.wikipedia.org/wiki/Promenadologie sowie eigene Überlegungen von Wolfram Eberius zum Ihme-Zentrum, ohne den Begriff „Promenadologie" im Fließtext selbst zu verwenden
- Dritter Absatz: Bezug auf die Fotografien der Broschüre
- Literaturangaben im Impressum auf Seite 15 verweisen auf dieselben beiden Wikipedia-Artikel (Ihme-Zentrum, Promenadologie)

## Bildmaterial

Alle Bilder liegen im Unterverzeichnis `images/` des Projektordners:

- `title2.jpg` – Umschlagmotiv (Querformat); `title.jpg` liegt unverändert im Ordner, wird im Dokument aber nicht mehr referenziert
- `ihme-01.jpg` … `ihme-10.jpg` – Fotostrecke, Hochformat, einheitliches Seitenverhältnis ca. 4:5

## Bildreihenfolge

Auf Nachfrage am 2026-09-01 wurde die Abfolge der zehn Fotostrecken-Bilder (Seite 5–14) daraufhin geprüft, ob sie eine stimmige Bildergeschichte ergibt. Zusammenfassung der Einschätzung:

Inhalt je Seite: Seite 5 (`ihme-01.jpg`) zeigt einen verwaisten Spielplatz, menschenleer. Seite 6 (`ihme-02.jpg`) einen leeren verglasten Rundbau/Pavillon mit Graffiti darunter. Seite 7 (`ihme-03.jpg`) eine komplett übersprühte Außentreppe. Seite 8 (`ihme-04.jpg`) den erhöhten Laubengang mit dem roten „GK"-Kiosk, ebenfalls stark besprüht. Seite 9 (`ihme-05.jpg`) ein frisch saniertes Gebäude mit lila/orangen Balkonen, gepflegt, ohne Graffiti. Seite 10 (`ihme-06.jpg`) ein bewohntes Fenster mit Blumenkasten und Vorhang. Seite 11 (`ihme-07.jpg`) ein großes Wandbild (Gesicht einer Frau) mit drei Passant:innen im Gespräch davor. Seite 12 (`ihme-08.jpg`) eine weite Straßenansicht mit Werbeplakaten und Alltagstrubel. Seite 13 (`ihme-09.jpg`) den Blick vom Ihmeufer mit Grün im Vordergrund und dem Schriftzug „Antifa heißt Solidarität". Seite 14 (`ihme-10.jpg`) noch einmal einen stark graffitiübersäten Laubengang, mit einer einzelnen gehenden Person.

Einschätzung: Eine stringente Handlung im klassischen Sinn ergibt sich daraus nicht, aber ein loser Spannungsbogen ist erkennbar. Der Auftakt (Spielplatz, Pavillon, Treppe, Laubengang) etabliert Leere und Verfall. Ab Seite 9/10 kippt die Stimmung Richtung gelebter Alltag (saniertes Haus, bewohntes Fenster). Seite 11 bringt mit Wandbild und Passant:innen den ersten direkten Menschenbezug. Seite 12/13 weiten den Blick auf den städtischen Kontext (Straße, Fluss). Der Schluss auf Seite 14 kehrt bewusst zum Verfall zurück, jetzt mit einer einzelnen gehenden Figur – das passt gut zur Promenadologie-Idee aus dem Einleitungstext und wirkt als Schlussbild stimmig.

Diskrepanz zum Text: Der dritte Absatz auf Seite 4 beschreibt „ein Wandbild neben verlassenen Treppenhäusern" – im Heft liegen das Wandbild (Seite 11) und die Treppenhaus-Aufnahme (Seite 7) aber vier Seiten auseinander, nicht unmittelbar nebeneinander. Mögliche Korrektur: `ihme-07.jpg` näher an `ihme-03.jpg` heranrücken (z. B. durch Tausch mit einem der dazwischenliegenden Bilder) – bislang nicht umgesetzt, siehe „Offene Punkte".

## Prompts

Chronologische Liste der Prompts, mit denen Wolfram die einzelnen Überarbeitungen angestoßen hat, mit Verweis auf den jeweils daraus entstandenen Log-Eintrag. Die Prompts zu den Versionen 0.1 und 0.2 (Projektanlage inkl. erstem Schmutztitel/Layout sowie erster ca. 200-Wörter-Einleitungstext) liegen vor dem für diese Sitzung verfügbaren Gesprächsverlauf und können hier nicht mehr zitiert werden.

- → **0.3**: „Hier sind noch einige Gedanken zum Thema Promenadologie nach Lucius Burckhardt... Der Text darf jetzt 250 Wörter lang sein."
- → **0.4**: „Die Textbox auf Seite 4 soll die Größe eines Fotos haben. Der Text soll im Blocksatz die gesamte Box ausfüllen."
- Ohne eigene Versionsnummer (fügte das Kapitel „Log" selbst hinzu, rückwirkend für 0.1–0.4): „die projekt.md sollte am schluss einen 'log' Bereich haben, in dem die Änderungen von Version zu Version zusammengefasst wird. Aktualisiere entsprechend die projekt.md in diesem Projekt."
- → **0.5**: „Überarbeite nochmals den Text von Seite 4. Es sollen drei Absätze sein: der erste Absatz fasst den Artikel zum Ihme-Zentrum von der Wikipedia zusammen; der zweite Absatz synthetisiert aus dem Artikel über das Ihme-Zentrum mit dem Artikel zur Promenadologie von https://de.wikipedia.org/wiki/Promenadologie – es soll nicht direkt Bezug auf die Promenadologie nehmen, sondern die Zusammenhänge herausarbeiten; der dritte Absatz geht auf die Bilder ein."
- → **0.6**: „Füge Seitenzahlen auf den Seite 4 bis 14 hinzu. Sie soll jeweils außen liegen. Lege hierfür einen eigenen Master an. Überprüfen, ob für alle Situationen Master hinterlegt angelegt wurden. Wenn nicht, lege die Master an." – dazu nach Rückfrage die Entscheidung „Statische Seitenzahlen per Skript (empfohlen)".
- → **0.7**: „Lege ein Grundlinienraster an. Es soll drei Spalten haben und in die Boxen passen. Der Text auf Seite 4 sollen dann Absatz für Absatz in die Spalten umgebrochen werden." – dazu nach Rückfrage die Entscheidung „Drei Spalten per Skript nachbilden (empfohlen)".
- → **0.8**: „Auf der Seite 15 ist am unteren Rand Platz für Impressum-Hinweis. Der untere Rand dieses Hinweises soll auf der gleichen Höhe, wie der untere Rand des Bildes sein. In diesem Hinweis steht, dass Autor Wolfram Eberius ist. Es gibt einen Hinweis auf die Webseite https://wolfram.eberius.photography Außerdem gibt es eine passend formatierte Literaturangabe für die Themen Ihme Zentrum und Promenadologie in der Wikipedia."
- → **0.9**: „Ich möchte, dass das Bild title gegen das Bild title2.jpg ausgetauscht wird. An der Positionierung des Bildes über die letzte und erste Seite ändert sich nichts." Dazu die klärende Rückfrage „Warum kann das skript nicht im ihme-zentrum-zine/images lesen? Das ging bisher auch." und die Präzisierung „Das bild soll gemäß projekt.md nur verlinkt werden. es soll nicht eingebetten werden. Letztes muss nur der Link ausgetauscht werden."
- → **0.10**: „Kannst Du nochmal die Abfolge der Bilder prüfen? Ergibt es einen Geschichte? Ich bin mir da unsicher" sowie „Fasse mir Deine Besprechung der Reihenfolge im projekt.md zusammen."
- → **0.11**: „Der Schmutztitel ist absichtlich und manuell geändert worden. Jetzt steht dort [...] Der Name taucht erst auf Seite 15 auf. Auch das ist absicht."
- → **0.12**: „Bitte füge in der projekt.md ein Kapitel 'Prompts' hinzu. Es soll über dem Kapitel 'Logs' stehen und enthält alle Prompts, die ich hier reingeschrieben habe. Bitte verweise dabei auf die log-Einträge"

- → **0.15**: „Enthält die agent.md auch die Anweisung an das LLM stets das Vorgehen (also Prompts und Logs) zu aktualisieren? Wenn nicht, wo müsste das hinterlegt werden?"

- → **0.16**: „Dieses Projekt funktioniert, weil Claude per MCP auf Affinity zugreifen kann. Dieser Umstand sollte in der README.md berücksichtigt werden. Außerdem wäre ein Abschnitt sinnvoll, welche Einstellungen bei Affinity, bzw. bei Claude vorgenommen werden müssen, um die Verbindung herzustellen."

## Log

- **0.1** (2026-09-01): Projekt angelegt. `projekt.md` mit Frontmatter und Seitenstruktur erstellt. Vorausgegangen war bereits eine Umstellung des Layouts: die beiden leeren Seiten wurden von 14/15 auf 3/4 vorgezogen (Seite 2 bleibt leer), das letzte Foto (`ihme-11.jpg`) wurde vollständig entfernt (vorletzte Seite dadurch leer, mit Platzhalter für einen Impressum-Hinweis am unteren Rand), und auf Seite 3 wurde der Schmutztitel ergänzt (drei Zeilen: „Ihme Zentrum" / „Hannover im August 2026" / „Fotos von Wolfram Eberius", mittig in der oberen Hälfte). Seite 4 enthielt zu diesem Zeitpunkt nur einen Platzhalter für den Einleitungstext.
- **0.2** (2026-09-01): Einleitungstext für Seite 4 ergänzt (ca. 200 Wörter, basierend auf dem Wikipedia-Artikel zum Ihme-Zentrum), Platzhalter ersetzt.
- **0.3** (2026-09-01): Einleitungstext um einen zweiten Absatz erweitert (Text jetzt bis 250 Wörter), der die Fotostrecke im Sinne der Promenadologie (Spaziergangswissenschaft) von Lucius Burckhardt deutet – auf Grundlage eigener Überlegungen von Wolfram Eberius zum Ihme-Zentrum.
- **0.4** (2026-09-01): Textbox auf Seite 4 an die Größe und Position der Fotoboxen der Fotostrecke angeglichen (128 × 160 mm, 10 mm Rand links, 25 mm oben) und Textausrichtung auf Blocksatz umgestellt, sodass der Text die gesamte Box ausfüllt (Schriftgröße dafür auf 4,3 mm erhöht).
- **0.5** (2026-09-01): Einleitungstext auf Seite 4 auf drei Absätze umgestellt: (1) Zusammenfassung des Wikipedia-Artikels zum Ihme-Zentrum, (2) Synthese aus dem Ihme-Zentrum-Artikel und den Grundgedanken der Promenadologie (Wikipedia-Artikel dazu ausgewertet), die Zusammenhänge herausgearbeitet statt der Promenadologie namentlich zu erwähnen, (3) Bezug zu den Fotografien. Schriftgröße der Blocksatz-Textbox auf 3,95 mm angepasst, damit der längere Text vollständig in die unveränderte Fotobox-Größe passt.
- **0.6** (2026-09-01): Seitenzahlen für Seite 4–14 ergänzt, jeweils außen (linke Seiten unten links, rechte Seiten unten rechts), Seite 15 bewusst ohne Seitenzahl. Technischer Hinweis: als feste Textrahmen per Skript gesetzt, nicht als automatisches Seitenzahl-Feld auf einem eigenen Master – die Affinity-Skript-Schnittstelle kann weder Master-Seiten anlegen noch automatische Seitenzahl-Felder einfügen (nur über die Programmoberfläche möglich). Bei künftigen Verschiebungen der Seitenreihenfolge müssen die Zahlen daher manuell nachgezogen werden.
- **0.7** (2026-09-01): Einleitungstext auf Seite 4 dreispaltig umgesetzt – je ein Absatz pro Spalte (40 mm Spaltenbreite, 4 mm Spaltenabstand, Blocksatz mit Silbentrennung). Alle drei Spalten nutzen denselben festen Zeilenabstand (Absolutwert), wodurch sich die Zeilen der Spalten auf gleicher Höhe treffen – ein zeilenweise abgestimmter Rhythmus statt eines im Dokument hinterlegten Grundlinienrasters. Technischer Hinweis: ein echtes, im Dokument gespeichertes Grundlinienraster sowie eine echte Spalteneinstellung an einem Textrahmen lassen sich über die Affinity-Skript-Schnittstelle nicht anlegen (nur über die Programmoberfläche, „Dokument einrichten" bzw. Textrahmen-Eigenschaften) – daher die Nachbildung über drei einzelne, exakt ausgerichtete Textrahmen.
- **0.8** (2026-09-01): Impressum-Hinweis auf Seite 15 mit Inhalt gefüllt (Autor „Wolfram Eberius", Webseite `https://wolfram.eberius.photography`, Literaturangaben zu den Wikipedia-Artikeln „Ihme-Zentrum" und „Promenadologie"). Textblock so positioniert, dass sein unterer Rand exakt auf der Höhe des unteren Rands der Fotoboxen liegt (185 mm).
- **0.9** (2026-09-01): Titelbild auf Seite 1 und 16 von `title.jpg` auf `title2.jpg` umgestellt. Die Verknüpfung wurde über die Affinity-Programmoberfläche („Bild ersetzen") ausgetauscht, nicht per Skript, da die Skript-Schnittstelle Bilder nur durch Einbetten der Pixel ersetzen kann (`ReplaceBitmap`) – laut Projektvorgabe sollen Bilder aber verknüpft bleiben. Per Skript verifiziert: beide Instanzen sind weiterhin verknüpft (nicht eingebettet), die Bildhöhe und die Position der Bildkante oben sind exakt unverändert (2551,18 pt bzw. y = −35,43 pt), die Breite hat sich durch das leicht andere Seitenverhältnis von `title2.jpg` geringfügig angepasst (von 3436,8 pt auf 3387,2 pt), wobei der relative Versatz zwischen Vorder- und Rückseiten-Ausschnitt exakt erhalten blieb – die Positionierung des Motivs über Seite 1 und 16 hinweg ist damit unverändert.
- **0.10** (2026-09-01): Bildreihenfolge der Fotostrecke (Seite 5–14) auf Nachfrage geprüft und die Einschätzung in einem neuen Abschnitt „Bildreihenfolge" dokumentiert (kein Eingriff in die Affinity-Datei). Dabei aufgefallene Diskrepanz zum Einleitungstext (Wandbild und Treppenhaus-Aufnahme liegen im Heft nicht nebeneinander, wie im dritten Absatz auf Seite 4 beschrieben) als neuen Punkt in „Offene Punkte" aufgenommen.
- **0.11** (2026-09-01): Schmutztitel auf Seite 3 wurde von Wolfram manuell und absichtlich in Affinity Publisher geändert (außerhalb der Skript-Sandbox) zu „Ihme Zentrum" / „Promenadologische Betrachtungen" / „Hannover 2026", ohne Namensnennung – bestätigt als Absicht, damit der Autorenname erst im Impressum auf Seite 15 erscheint. `projekt.md` entsprechend angepasst (Seitenstruktur-Tabelle korrigiert, zugehöriger Punkt aus „Offene Punkte" entfernt).
- **0.12** (2026-09-01): Neues Kapitel „Prompts" oberhalb von „Log" ergänzt – eine chronologische Liste aller in dieser Sitzung gestellten Prompts mit Verweis auf den jeweils daraus entstandenen Log-Eintrag. Die Prompts zu 0.1 und 0.2 liegen außerhalb des verfügbaren Gesprächsverlaufs und sind entsprechend als nicht zitierbar vermerkt.
- **0.13** (2026-09-01): Neue Datei `herausforderungen.md` angelegt, die wiederkehrende technische Probleme dieser Sitzung zusammenfasst (Skript-Zugriff auf Bilder im Projektordner scheitert an der Desktop-only-Sandbox der Affinity-Skript-Schnittstelle; fehlende SDK-Funktionen für Master-Seiten, automatische Seitenzahlen und Grundlinienraster/Spalten; instabile/abbrechende Skript-Ausführung bei blockierenden nativen Dialogen und ein durchgehend fehlerhaftes `search_sdk_hints`-Werkzeug; Vorgaben aus `projekt.md` – konkret „verknüpft, nicht eingebettet" – wurden bei der Wahl der Umsetzungsmethode für den Bildaustausch in Log 0.9 zunächst nicht berücksichtigt) und für jedes Problem Lösungsszenarien inklusive Umgehungsmöglichkeiten vorschlägt. In der Projektbeschreibung oben ein Verweis auf die neue Datei ergänzt.
- **0.14** (2026-09-01): Zwei neue Dateien angelegt. `agent.md` fasst feste, vorausschauende Arbeitsregeln für KI-Agenten zusammen (Projektregeln wie „Bilder verknüpft, nicht eingebettet", bekannte technische Grenzen der Affinity-Skript-Schnittstelle in Kurzform mit Verweis auf `herausforderungen.md`, sowie Arbeitsweise-Vorgaben wie Verifikation nach Änderungen und Aktualisierung von `projekt.md`). `README.md` bietet eine schnelle inhaltliche Übersicht für menschliche Leser:innen (Projektbeschreibung, Aufbau der Broschüre, Dateiübersicht des Ordners). In der Projektbeschreibung oben Verweise auf beide neuen Dateien ergänzt.
- **0.15** (2026-09-01): Lücke in `agent.md` behoben, auf Nachfrage entdeckt: Die Arbeitsweise-Regel zur Aktualisierung von `projekt.md` erwähnte zwar das Nachtragen eines Log-Eintrags, aber nicht das Ergänzen des zugehörigen Prompts im Kapitel „Prompts". In `agent.md` ergänzt, dass „Prompts" und „Log" bei jeder Änderung gemeinsam gepflegt werden.
- **0.16** (2026-09-01): `README.md` ergänzt: Hinweis in der Einleitung, dass das Projekt über eine MCP-Verbindung zwischen Claude und Affinity Publisher entsteht, sowie neuer Abschnitt „Voraussetzungen: Claude-Affinity-Verbindung" mit den konkreten Einstellungen auf beiden Seiten. Affinity-seitig in den Einstellungen unter „Protokoll für Modellkontext (MCP)" per Bildschirmzugriff verifiziert (Hauptschalter „Affinity-MCP aktivieren" sowie Einzelberechtigungen für Desktop-Dateizugriff, Netzwerk, Skripte und Aufgaben-Hinweise); nichts an den Einstellungen verändert, nur dokumentiert. Claude-seitig anhand der bekannten Funktionsweise der Gerätebrücke (Rechner-Verknüpfung, Ordnerfreigabe, Bildschirmsteuerungs-Freigabe) beschrieben.
