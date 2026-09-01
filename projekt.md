---
titel: "Ihme Zentrum Hannover"
thema: "Fotografische Dokumentation des Ihme-Zentrums in Hannover im Sommer 2026"
zielgruppe: "Menschen mit Interesse an Architektur und Stadtentwicklung, (ehemalige) Bewohner:innen und Nutzer:innen des Ihme-Zentrums, an Hannover und Brutalismus/Großstrukturen der 1970er interessierte Betrachter:innen"
typ: "Broschüre (Drahtheftung, DIN A5 hoch, 16 Seiten)"
kernidee: "Wenn jemand das Heft zuklappt, soll er vor allem die vielschichtige, ambivalente Atmosphäre des Ihme-Zentrums gesehen haben – zwischen Verfall, Aneignung, Graffiti und urbaner Alltagsnutzung."
version: "0.7"
datum_erstellung: 2026-09-01
datum_aktualisierung: 2026-09-01
---

# Ihme Zentrum Hannover – Projektbeschreibung

Dieses Dokument beschreibt die konkreten Inhalte und den aktuellen Stand der Broschüre, die gemeinsam mit Claude in Affinity erstellt wird. Es ergänzt die Meta-Informationen im Frontmatter oben und dient als Referenz für spätere Überarbeitungen.

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
| 1 | Vorderseite des Umschlags – Titelbild `title.jpg`, randlos beginnend links, mit weißem Rand rechts und vertikal von unten nach oben verlaufendem Titel „Ihme Zentrum Hannover" |
| 2 | leer |
| 3 | Schmutztitel, mittig in der oberen Hälfte: „Ihme Zentrum" (Titel), „Hannover im August 2026" (Unterzeile), „Fotos von Wolfram Eberius" (Credit-Zeile) |
| 4 | Einleitungstext zum Ihme-Zentrum in drei Absätzen: (1) Zusammenfassung des Wikipedia-Artikels zum Ihme-Zentrum (Geschichte, Architektur, Niedergang, aktueller Status); (2) Synthese aus dem Ihme-Zentrum-Artikel und den Grundgedanken der Promenadologie (Spaziergangswissenschaft) von Lucius Burckhardt – ohne diese namentlich zu nennen –, die die Kluft zwischen geplanter und begangener/erlebter Stadt herausarbeitet; (3) Bezug zu den Fotografien der Broschüre. Textbox in Blocksatz, in Größe und Position identisch mit den Fotoboxen der Fotostrecke (128 × 160 mm, 10 mm Rand links, 25 mm oben) |
| 4–14 | Seitenzahlen jeweils außen (Seite 4, 6, 8, 10, 12, 14 unten links; Seite 5, 7, 9, 11, 13 unten rechts), 10 mm vom seitlichen Rand, 15 mm über dem unteren Blattschnitt |
| 4 | Einleitungstext dreispaltig gesetzt (ein Absatz je Spalte, Blocksatz mit Silbentrennung), Spalten mit festem, einheitlichem Zeilenabstand (Grundlinien-Rhythmus über alle drei Spalten hinweg) |
| 5–14 | Fotostrecke: `ihme-01.jpg` bis `ihme-10.jpg`, in dieser Reihenfolge, jeweils ganzseitig mit 10 mm Rand links/rechts, vertikal zentriert entsprechend dem eigenen Seitenverhältnis des Bildes |
| 15 | leer, am unteren Rand Platzhalter für Impressum-Hinweis (Veröffentlichung, Fotograf, Copyright usw.) – Text liegt noch nicht vor |
| 16 | Rückseite des Umschlags – Fortsetzung von `title.jpg` (bildet zusammen mit Seite 1 im aufgeklappten Zustand ein durchgehendes Motiv) |

Hinweis: `ihme-11.jpg` wurde bewusst aus der Broschüre entfernt.

## Offene Punkte

- Impressum-/Credit-Text für Seite 15 (Veröffentlichung, Fotograf, Copyright) fehlt noch
- Dateiname der Affinity-Datei trägt noch die Doppel-Endung `.afpub.af` (entstanden durch einen manuellen Speichervorgang außerhalb der Skript-Sandbox); Umbenennung auf `.afpub` steht noch aus
- Seitenzahlen (Seite 4–14) sind feste Textrahmen, kein Master mit automatischem Seitenzahl-Feld (siehe Log 0.6) – bei Bedarf später in Affinity Publisher direkt als Master nachbauen
- In Affinity Publisher steht noch ein hängengebliebener „Sektionsassistent"-Dialog offen (unkritisch, einfach schließen)
- Schmutztitel auf Seite 3, dritte Zeile: aktuell „Wolfram Eberius" statt ursprünglich vorgesehenem „Fotos von Wolfram Eberius" – zur Kontrolle, ob das so gewollt ist

## Quellen

- Einleitungstext (Seite 4), erster Absatz (Geschichte/Fakten): https://de.wikipedia.org/wiki/Ihme-Zentrum
- Zweiter Absatz (Synthese): verarbeitet zusätzlich https://de.wikipedia.org/wiki/Promenadologie sowie eigene Überlegungen von Wolfram Eberius zum Ihme-Zentrum, ohne den Begriff „Promenadologie" im Fließtext selbst zu verwenden
- Dritter Absatz: Bezug auf die Fotografien der Broschüre

## Bildmaterial

Alle Bilder liegen im Unterverzeichnis `images/` des Projektordners:

- `title.jpg` – Umschlagmotiv (Querformat)
- `ihme-01.jpg` … `ihme-10.jpg` – Fotostrecke, Hochformat, einheitliches Seitenverhältnis ca. 4:5

## Log

- **0.1** (2026-09-01): Projekt angelegt. `projekt.md` mit Frontmatter und Seitenstruktur erstellt. Vorausgegangen war bereits eine Umstellung des Layouts: die beiden leeren Seiten wurden von 14/15 auf 3/4 vorgezogen (Seite 2 bleibt leer), das letzte Foto (`ihme-11.jpg`) wurde vollständig entfernt (vorletzte Seite dadurch leer, mit Platzhalter für einen Impressum-Hinweis am unteren Rand), und auf Seite 3 wurde der Schmutztitel ergänzt (drei Zeilen: „Ihme Zentrum" / „Hannover im August 2026" / „Fotos von Wolfram Eberius", mittig in der oberen Hälfte). Seite 4 enthielt zu diesem Zeitpunkt nur einen Platzhalter für den Einleitungstext.
- **0.2** (2026-09-01): Einleitungstext für Seite 4 ergänzt (ca. 200 Wörter, basierend auf dem Wikipedia-Artikel zum Ihme-Zentrum), Platzhalter ersetzt.
- **0.3** (2026-09-01): Einleitungstext um einen zweiten Absatz erweitert (Text jetzt bis 250 Wörter), der die Fotostrecke im Sinne der Promenadologie (Spaziergangswissenschaft) von Lucius Burckhardt deutet – auf Grundlage eigener Überlegungen von Wolfram Eberius zum Ihme-Zentrum.
- **0.4** (2026-09-01): Textbox auf Seite 4 an die Größe und Position der Fotoboxen der Fotostrecke angeglichen (128 × 160 mm, 10 mm Rand links, 25 mm oben) und Textausrichtung auf Blocksatz umgestellt, sodass der Text die gesamte Box ausfüllt (Schriftgröße dafür auf 4,3 mm erhöht).

- **0.5** (2026-09-01): Einleitungstext auf Seite 4 auf drei Absätze umgestellt: (1) Zusammenfassung des Wikipedia-Artikels zum Ihme-Zentrum, (2) Synthese aus dem Ihme-Zentrum-Artikel und den Grundgedanken der Promenadologie (Wikipedia-Artikel dazu ausgewertet), die Zusammenhänge herausgearbeitet statt der Promenadologie namentlich zu erwähnen, (3) Bezug zu den Fotografien. Schriftgröße der Blocksatz-Textbox auf 3,95 mm angepasst, damit der längere Text vollständig in die unveränderte Fotobox-Größe passt.
- **0.6** (2026-09-01): Seitenzahlen für Seite 4–14 ergänzt, jeweils außen (linke Seiten unten links, rechte Seiten unten rechts), Seite 15 bewusst ohne Seitenzahl. Technischer Hinweis: als feste Textrahmen per Skript gesetzt, nicht als automatisches Seitenzahl-Feld auf einem eigenen Master – die Affinity-Skript-Schnittstelle kann weder Master-Seiten anlegen noch automatische Seitenzahl-Felder einfügen (nur über die Programmoberfläche möglich). Bei künftigen Verschiebungen der Seitenreihenfolge müssen die Zahlen daher manuell nachgezogen werden.
- **0.7** (2026-09-01): Einleitungstext auf Seite 4 dreispaltig umgesetzt – je ein Absatz pro Spalte (40 mm Spaltenbreite, 4 mm Spaltenabstand, Blocksatz mit Silbentrennung). Alle drei Spalten nutzen denselben festen Zeilenabstand (Absolutwert), wodurch sich die Zeilen der Spalten auf gleicher Höhe treffen – ein zeilenweise abgestimmter Rhythmus statt eines im Dokument hinterlegten Grundlinienrasters. Technischer Hinweis: ein echtes, im Dokument gespeichertes Grundlinienraster sowie eine echte Spalteneinstellung an einem Textrahmen lassen sich über die Affinity-Skript-Schnittstelle nicht anlegen (nur über die Programmoberfläche, „Dokument einrichten" bzw. Textrahmen-Eigenschaften) – daher die Nachbildung über drei einzelne, exakt ausgerichtete Textrahmen.
