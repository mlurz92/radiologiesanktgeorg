# Optimiertes Web-Portal der Klinik für Radiologie und Nuklearmedizin

## 1. Einleitung und Überblick
Diese Anwendung fungiert als zentrales Informations- und Kommunikationsportal für die Klinik für Radiologie und Nuklearmedizin am Klinikum St. Georg Leipzig. Sie ist als **Single-Page-Application (SPA)** konzipiert, was bedeutet, dass die Navigation zwischen verschiedenen Inhalten (Startseite, Leistungen, Team, Kontakt) ohne sichtbare Ladezeiten oder Seiten-Reloads erfolgt.

Die Anwendung richtet sich an drei Hauptzielgruppen:
1.  **Patienten:** Zur Vorbereitung auf Untersuchungen und Terminfindung.
2.  **Zuweiser (Ärzte):** Für Informationen zu Überweisungen, Teleradiologie und Befundung.
3.  **Allgemeine Besucher:** Für Kontaktinformationen, Anfahrt und Team-Übersichten.

Das Design ist modern, responsiv und barrierefrei optimiert, wobei die Corporate Identity des Klinikums (Primärfarbe Rot) konsequent umgesetzt wird.

---

## 2. Benutzeroberfläche (UI) und Design-Konzept

### 2.1. Globales Layout und Navigation
Die Anwendung nutzt ein **Sticky-Header-Konzept**, bei dem die Hauptnavigation am oberen Bildschirmrand fixiert bleibt, um jederzeit Zugriff auf alle Bereiche zu gewährleisten.

* **Top-Bar:** Eine schmale Leiste am oberen Rand bietet Hilfsfunktionen wie "Leichte Sprache", "Gebärdensprache" sowie Direktlinks zu den Bereichen "Für Zuweiser", "Presse", "Karriere" und eine hervorgehobene "Notfall"-Information.
* **Header & Branding:** Enthält das Klinik-Logo (dient als Home-Link), den Kliniknamen und die zentrale Telefonnummer mit Öffnungszeiten. Auf mobilen Geräten erscheint hier ein "Hamburger-Menü"-Button.
* **Hauptnavigation:**
    * **Desktop:** Eine horizontale Leiste mit den Punkten Startseite, Leistungsspektrum, Nuklearmedizin, Für Patient*innen, Team und Kontakt. Der aktive Menüpunkt wird visuell hervorgehoben (dunklerer Hintergrund).
    * **Mobil:** Ein ausklappbares Menü, das die gleichen Punkte vertikal listet.
* **Breadcrumb-Navigation:** Unterhalb des Headers zeigt eine Pfad-Leiste dem Nutzer stets an, wo er sich befindet (z.B. `Startseite > Kliniken & Zentren > Leistungsspektrum`).
* **Seitenleiste (Sidebar):** Auf Desktop-Geräten befindet sich rechts eine feste Spalte mit Schnellzugriffen ("Sprechzeiten", "Terminvereinbarung", "Anfahrt") und einem prominenten Bereich für Zuweiser.

### 2.2. Responsive Verhalten
Die Anwendung passt sich dynamisch an verschiedene Bildschirmgrößen an (Mobile First Ansatz mittels Tailwind CSS).
* **Grid-System:** Inhalte, die auf dem Desktop nebeneinander stehen (z.B. Text und Sidebar), rutschen auf Tablets und Smartphones automatisch untereinander.
* **Tabellen & Listen:** Leistungsübersichten und Team-Listen transformieren sich für eine optimale Lesbarkeit auf kleinen Screens.

---

## 3. Detaillierte Beschreibung der Funktionsmodule

Die Anwendung ist in verschiedene "Views" (Ansichten) unterteilt, die über die Navigation angesteuert werden.

### 3.1. Modul: Startseite (Dashboard)
Die Einstiegsseite bietet einen schnellen Überblick und dient als Verteiler.
* **Hero-Bereich:** Ein repräsentatives Bild ("Großgeräte") und ein Begrüßungstext führen in die Klinik ein.
* **Feature-Kacheln:** Ein Gitter aus interaktiven Karten (Teasern) für Bereiche wie "MRT & CT", "Interventionelle Therapie" oder "Kinderradiologie".
    * *Interaktion:* Ein Klick auf eine Kachel leitet den Nutzer nicht nur auf die entsprechende Unterseite (z.B. Leistungsspektrum), sondern **aktiviert automatisch den passenden Filter**. Wer z.B. auf "MRT" klickt, landet im Leistungsbereich und sieht nur MRT-Leistungen.

### 3.2. Modul: Leistungsspektrum
Dies ist der Katalog aller medizinischen Dienstleistungen.
* **Filter-System:** Am oberen Rand befinden sich Filter-Buttons (Alle, MRT, CT, Röntgen, Mammographie, Intervention, Kinderradiologie). Der Nutzer kann die Liste der angezeigten Leistungen damit live eingrenzen. Der aktive Filter wird farblich (Rot) markiert.
* **Leistungskarten:** Jede Leistung wird in einer Box dargestellt, die folgende Informationen enthält:
    * Icon und Titel.
    * Beschreibungstext.
    * **Detail-Box:** Ein hervorgehobener Bereich mit **Dauer** der Untersuchung und notwendiger **Vorbereitung** (z.B. "Nüchtern", "Keine Blutverdünner").

### 3.3. Modul: Nuklearmedizin
Ein spezialisierter Bereich für funktionelle Diagnostik.
* **Information:** Einleitungstext und Bildmaterial zur Abteilung.
* **Interaktive FAQ:** Ein "Häufige Fragen"-Bereich (Akkordeon-Prinzip). Nutzer können Fragen wie "Ist die Strahlung gefährlich?" anklicken, woraufhin die Antwort sanft aufklappt.

### 3.4. Modul: Für Patient*innen
Dieser Bereich bündelt organisatorische Informationen zur Vorbereitung.
* **Checkliste:** Eine visuell aufbereitete Liste mit Icons (Häkchen), die dem Patienten sagt, was mitzubringen ist (Chipkarte, Überweisung, Vorbefunde, Laborwerte).
* **Warnhinweise (Alerts):**
    * Ein blauer Hinweis zur Pünktlichkeit.
    * Ein **gelber Warn-Kasten** für MRT-Sicherheit (Herzschrittmacher/Implantate), der hohe Aufmerksamkeit erzeugt.
* **Digitaler Befundabruf:** Erklärung des QR-Code-Verfahrens zum digitalen Abruf von Bilddaten und Befunden, visualisiert durch ein QR-Code-Icon.

### 3.5. Modul: Team
Eine strukturierte Darstellung des Personals, unterteilt in "Radiologie" und "Nuklearmedizin".
* **Hierarchie:** Das Team wird logisch gegliedert in Chefarzt, Sekretariat, Oberärzte, Assistenzärzte und MTRA (Funktionsdienst).
* **Personenkarten:** Jede Person wird mit Foto (sofern vorhanden), Name, Rolle (z.B. "Leitender Oberarzt") und Spezialisierung dargestellt. Fehlt ein Foto, wird ein neutraler Platzhalter verwendet.

### 3.6. Modul: Für Zuweiser
Ein spezialisierter Informationsbereich für ärztliche Kollegen.
* **Versorgungsauftrag:** Klare Abgrenzung, welche Patienten behandelt werden dürfen (Stationär, BG, Privat, ASV).
* **Prozess-Informationen:** Ein zweispaltiges Layout mit Details zu "Vor der Untersuchung" (Laborwerte, Metformin-Pause) und "Nach der Untersuchung" (Befundübermittlung).
* **Telefonliste:** Ein Block mit direkten Durchwahlnummern für CT/MRT, Angiographie und Nuklearmedizin, getrennt vom Patientenkontakt.
* **Teleradiologie:** Informationen zum 24/7-Netzwerk und ein "Login"-Button für das Teleradiologie-Portal.
* **Bildportal (Web-PACS):** Zugangsmöglichkeit für externe Ärzte zur Einsicht von Patientenbildern.

### 3.7. Modul: Kontakt & Anfahrt
* **Kontaktdaten:** Adresse, Telefon, Fax und E-Mail der Klinikleitung.
* **Anreise-Informationen:** Details zu ÖPNV (Straßenbahn/Bus) und Parkmöglichkeiten.
* **Interaktive Karte:** Eine integrierte **Leaflet-Karte (OpenStreetMap)**, die den genauen Standort von Haus 20 anzeigt. Ein Marker auf der Karte öffnet bei Klick ein Popup mit der genauen Adresse.

---

## 4. Interaktive Overlay-Elemente

### 4.1. Termin-Modal (Popup)
Über den Button "Terminvereinbarung" in der Sidebar öffnet sich ein modales Fenster, das den Hintergrund abdunkelt.
* **Funktion:** Der Nutzer muss zunächst seinen Versicherungsstatus wählen (Gesetzlich vs. Privat/Selbstzahler), um zum korrekten Buchungsprozess weitergeleitet zu werden.
* **Design:** Klare, große Klickflächen mit Pfeil-Icons, die beim Überfahren (Hover) animiert werden.

### 4.2. Cookie-Layer
Beim ersten Aufruf der Seite erscheint am unteren Bildschirmrand ein fixierter Hinweis zur Datennutzung.
* **Optionen:** Der Nutzer kann "Alle akzeptieren" oder "Anpassen" wählen. Das Layer bleibt bestehen, bis eine Aktion erfolgt.

---

## 5. Technische Merkmale aus Nutzersicht

* **Geschwindigkeit:** Da alle Inhalte initial geladen werden, erfolgt der Wechsel zwischen den Menüpunkten verzögerungsfrei (Instant-Navigation).
* **Ikonografie:** Die Anwendung nutzt konsistente Icons (Lucide-Set) zur visuellen Unterstützung von Textinhalten (z.B. Telefonhörer, Kalender, Warndreiecke), was die Erfassbarkeit von Informationen erhöht.
* **Typografie:** Die verwendete Schriftart "Arimo" sorgt für ein klares, gut lesbares Schriftbild, das dem medizinischen Kontext angemessen ist.
* **Barrierefreiheit (Ansätze):** Hohe Kontraste (Rot/Weiß/Dunkelgrau), klare Fokus-Zustände und semantisches HTML unterstützen die Bedienbarkeit.

---

## 6. Zusammenfassung
Die Anwendung präsentiert die Klinik für Radiologie und Nuklearmedizin als hochmoderne, serviceorientierte Abteilung. Durch die klare Trennung von Patienten- und Zuweiser-Informationen sowie die intuitiven Filter- und Navigationsmöglichkeiten findet jeder Nutzer schnell die für ihn relevante Information – sei es die Vorbereitung auf ein MRT, die Telefonnummer für einen Notfallbefund oder der Weg zur Klinik.
