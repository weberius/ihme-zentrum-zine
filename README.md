# Ihme Zentrum Hannover – Fotobroschüre

Eine fotografische Dokumentation des Ihme-Zentrums in Hannover-Linden, entstanden im Sommer 2026. Die Broschüre richtet sich an Menschen mit Interesse an Architektur und Stadtentwicklung, (ehemalige) Bewohner:innen und Nutzer:innen des Ihme-Zentrums sowie an alle, die sich für Hannover und Brutalismus/Großstrukturen der 1970er interessieren. Ziel ist es, die vielschichtige, ambivalente Atmosphäre des Gebäudekomplexes zu vermitteln – zwischen Verfall, Aneignung, Graffiti und urbaner Alltagsnutzung.

Autor: Wolfram Eberius – [wolfram.eberius.photography](https://wolfram.eberius.photography)

Dieses Projekt entsteht in Zusammenarbeit mit Claude (Anthropic): Claude greift über das Model Context Protocol (MCP) direkt auf Affinity Publisher auf dem Rechner des Autors zu, kann darin Skripte ausführen, Seiten rendern und die Programmoberfläche bedienen. Das komplette Layout – Textboxen, Seitenzahlen, Bildplatzierung, Impressum usw. – ist auf diesem Weg entstanden. Wie diese Verbindung eingerichtet ist, steht im Abschnitt „Voraussetzungen: Claude-Affinity-Verbindung" unten.

## Format

DIN A5 hoch, Drahtheftung, 16 Seiten. Endformat 148 × 210 mm, Datenformat inkl. 3 mm Beschnitt 154 × 216 mm, CMYK, mindestens 300 dpi. Details zur Druckspezifikation stehen in `projekt.md`.

## Aufbau

- **Umschlag (Seite 1/16):** Durchgehendes Umschlagmotiv, das sich über Vorder- und Rückseite erstreckt, mit dem Titel „Ihme Zentrum Hannover".
- **Schmutztitel (Seite 3):** „Ihme Zentrum" / „Promenadologische Betrachtungen" / „Hannover 2026".
- **Einleitungstext (Seite 4):** Dreispaltiger Text in drei Absätzen – eine Zusammenfassung zur Geschichte des Ihme-Zentrums, eine Synthese mit Gedanken der Promenadologie (Spaziergangswissenschaft nach Lucius Burckhardt) und ein Bezug zu den Fotografien.
- **Fotostrecke (Seite 5–14):** Zehn ganzseitige Fotografien (`ihme-01.jpg` bis `ihme-10.jpg`), die bei einem Rundgang durch und um das Ihme-Zentrum entstanden sind. Jede Seite trägt außen eine Seitenzahl.
- **Impressum (Seite 15):** Autor, Website und Literaturangaben (Wikipedia-Artikel zu „Ihme-Zentrum" und „Promenadologie").

Die vollständige, laufend aktualisierte Beschreibung des Inhalts und Layouts steht in `projekt.md`.

## Dateien in diesem Ordner

| Datei / Ordner | Inhalt |
|---|---|
| `Ihme_Zentrum_Hannover_Broschuere.afpub.af` | Das Affinity-Publisher-Dokument – die eigentliche Arbeitsdatei der Broschüre |
| `Ihme_Zentrum_Hannover_Broschuere.pdf` | Aktueller PDF-Export der Broschüre |
| `broschuere_drahtheftung_dina5_hoch_1.pdf`, `_2.pdf` | Vorlagen/Referenzdateien des Druckdienstleisters für das Drahtheftungs-A5-Format |
| `farbprofil-wir-machen-druck/` | ICC-Farbprofil des Druckdienstleisters (`ISOcoated_v2_300_eci.icc`) |
| `images/` | Alle Bilddateien: Umschlagmotive (`title.jpg`, `title2.jpg` – aktuell verwendet) und die Fotostrecke (`ihme-01.jpg` … `ihme-11.jpg`, wobei `ihme-11.jpg` bewusst nicht in der Broschüre verwendet wird) |
| `intro-text.md` | Rohfassung der Ausgangstexte zu Ihme-Zentrum, Promenadologie und Fotografie, aus denen der Einleitungstext auf Seite 4 entwickelt wurde |
| `projekt.md` | Laufend aktualisierte Projektbeschreibung: Seitenstruktur, Druckspezifikation, Quellen, offene Punkte, verwendete Prompts und Versions-Log |
| `herausforderungen.md` | Rückblick auf technische Probleme bei der Arbeit mit der Affinity-Skript-Schnittstelle und mögliche Lösungen/Umgehungen |
| `agent.md` | Arbeitsregeln für KI-Agenten (Claude), die an diesem Projekt weiterarbeiten |
| `temp/` | Ablage für temporäre Arbeitsdateien, aktuell leer |

## Voraussetzungen: Claude-Affinity-Verbindung

Damit Claude wie in diesem Projekt direkt in Affinity Publisher arbeiten kann, müssen auf beiden Seiten Einstellungen vorgenommen werden.

### In Affinity

Affinity (Menü) → Einstellungen… → „Protokoll für Modellkontext (MCP)". Dort:

- **„Affinity-MCP aktivieren"** ist der Hauptschalter – ohne ihn kann kein KI-Assistent auf Affinity zugreifen. In diesem Projekt eingeschaltet.
- Darunter lassen sich einzelne Berechtigungen separat steuern. In diesem Projekt aktiviert: „Auf die Dateien auf Ihrem Desktop zugreifen" (**wichtig:** das beschränkt den Dateizugriff von Skripten tatsächlich auf den Desktop-Ordner – nicht auf beliebige andere Ordner wie den Projektordner, siehe `herausforderungen.md`), „Zugriff auf Netzwerke", „Gespeicherte Skripte verwenden", „Skripte in Ihrem Panel für Skripte speichern" sowie das Speichern und Teilen von Hinweisen zu Aufgaben. Deaktiviert ist „Studio-Features mit Canva AI verwenden" (verbraucht sonst das monatliche KI-Limit des Canva-Plans).
- Affinity Publisher muss geöffnet sein und das betreffende Dokument geladen haben, damit Claude per Skript darauf zugreifen und es rendern kann.

### In Claude

- Der Rechner, auf dem Affinity läuft, muss in der Claude-Desktop-App mit der jeweiligen Aufgabe/Sitzung verknüpft sein („Mit diesem Computer verknüpfen"). Erst dadurch stehen die Fernsteuerungs-Werkzeuge (Skript-Ausführung in Affinity, Bildschirmzugriff, Ordnerzugriff) zur Verfügung.
- Der Projektordner (`ihme-zentrum-zine`) muss der Unterhaltung als Ordner freigegeben sein, damit `projekt.md`, Bilder usw. gelesen und geschrieben werden können.
- Für Aktionen direkt am Bildschirm (z. B. Klicks in Affinitys Programmoberfläche, etwa beim Ersetzen eines verknüpften Bildes) muss zusätzlich einmalig die Bildschirmsteuerung für die Anwendung „Affinity" freigegeben werden – Claude fragt das bei Bedarf gezielt an.

## Stand des Projekts

Der aktuelle Bearbeitungsstand (Versionsnummer, Datum, Änderungshistorie) steht im Frontmatter und im Abschnitt „Log" von `projekt.md`.

## Versionierung

Der Ordner ist ein lokales Git-Repository.
