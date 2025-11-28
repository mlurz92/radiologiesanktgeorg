# Anwendungsdokumentation: Webportal Radiologie & Nuklearmedizin St. Georg

## 1. Einleitung und Zweckbestimmung

Das Webportal **Radiologie & Nuklearmedizin Sankt Georg** dient als zentrale digitale Schnittstelle zwischen der medizinischen Einrichtung, den Patienten und den zuweisenden Ärzten. In seiner aktuellen Ausbaustufe stellt die Anwendung eine **hochoptimierte, patientenzentrierte Informationsplattform** dar. 

Der primäre Zweck der Anwendung ist die **barrierefreie und intuitive Bereitstellung essenzieller Informationen** über das medizinische Leistungsspektrum, das behandelnde Personal sowie logistische Details (Kontakt, Anfahrt, Terminvergabe). Die Architektur der Seite wurde spezifisch darauf ausgelegt, Nutzern unabhängig von ihrem technischen Endgerät oder ihrer digitalen Kompetenz einen schnellen Zugriff auf relevante Gesundheitsinformationen zu ermöglichen.

---

## 2. Globale UI-Konzepte und User Experience (UX)

Die Benutzeroberfläche (UI) folgt einer strengen **"Content-First"-Philosophie**, eingebettet in ein modernes, responsives Design-System.

### 2.1 Visuelle Sprache und Corporate Identity
* **Farbpalette:** Die Anwendung nutzt ein vertrauenserweckendes Farbschema, das primär auf Weißräumen (Whitespace) und den Corporate-Farben des Klinikums (Akzente in Blau/Rot) basiert. Dies fördert die Lesbarkeit und vermittelt klinische Reinheit sowie Professionalität.
* **Typografie:** Es kommt eine serifenlose, moderne Schriftart zum Einsatz, die für Bildschirmlesbarkeit optimiert ist. Klare Hierarchien durch Variationen in **Schriftgröße** und **Schriftschnitt (Fettung)** leiten den Blick des Nutzers gezielt durch die Inhalte.

### 2.2 Responsives Verhalten und Layout
Das Layout ist **vollständig responsiv (Fluid Design)**.
* **Desktop-Ansicht:** Nutzt die volle Bildschirmbreite für mehrspaltige Layouts (z.B. Text links, Bild rechts oder Grid-Views für das Team).
* **Mobile & Tablet:** Inhalte werden automatisch in eine vertikale Scroll-Struktur (Single Column) umgebrochen. Elemente wie Navigationsleisten transformieren sich in platzsparende Menüs (Hamburger-Menü), und Touch-Targets (Buttons/Links) werden automatisch vergrößert, um die Bedienung per Fingerzeig zu erleichtern.

### 2.3 Navigation
Die Navigation ist **persistent** gestaltet:
* **Header-Bereich:** Enthält das Logo (Home-Link) und die primären Navigationspunkte (Start, Leistungsspektrum, Team, Kontakt). Auf Desktop-Systemen ist dies als horizontale Leiste ausgeführt, mobil als ausklappbares Overlay.
* **Footer-Bereich:** Bietet sekundäre Navigationsmöglichkeiten, rechtliche Hinweise (Impressum, Datenschutz) und schnelle Kontaktinformationen.

---

## 3. Detaillierte Funktionsmodule

Die Anwendung gliedert sich in fünf logische Hauptbereiche, die nahtlos ineinandergreifen.

### 3.1 Modul: Startseite (Dashboard)
Die Startseite fungiert als Verteiler und erster Kontaktpunkt ("Landing Page").
* **Hero-Sektion:** Ein prominenter Bereich mit visueller Begrüßung und einer klaren Zusammenfassung der fachlichen Kompetenz (Radiologie & Nuklearmedizin).
* **Schnellzugriff (Teaser):** Interaktive Kacheln oder Textabschnitte, die direkt zu den wichtigsten Unterbereichen (Leistungen, Team) verlinken.
* **Zweck:** Der Nutzer soll innerhalb von Sekunden verstehen, wo er sich befindet und wie er sein Ziel (z.B. Terminvereinbarung) erreicht.

### 3.2 Modul: Leistungsspektrum
Dieses Modul ist das inhaltliche Herzstück und dient der medizinischen Aufklärung.
* **Strukturierte Auflistung:** Die Leistungen sind logisch gruppiert (z.B. CT, MRT, Mammographie, Nuklearmedizin).
* **Detailansichten:** Zu jedem Verfahren werden verständliche Erklärungen geboten:
    * **Was ist das?** (Methodik)
    * **Wann wird es angewandt?** (Indikation)
    * **Besonderheiten:** Spezifische Hinweise zur Vorbereitung oder zum Ablauf.
* **Interaktion:** Nutzer können durch die Inhalte scrollen oder über Anker-Links direkt zu spezifischen Untersuchungen springen. Fachbegriffe werden kontextuell erläutert, um die Laienverständlichkeit zu maximieren.

### 3.3 Modul: Das Team
Dieses Modul baut Vertrauen durch Personalisierung auf.
* **Grid-Layout der Experten:** Die Ärzte und das Fachpersonal werden in einem übersichtlichen Raster präsentiert.
* **Profilkarten:** Jedes Teammitglied wird durch ein professionelles Porträtfoto (z.B. Dr. Lurz, Dr. Torki, Fachärzte) und den Namen sowie die Funktion dargestellt.
* **Visuelle Hierarchie:** Die Leitungsebene (Chefärzte) und Fachärzte sowie das technische Personal (MTRA) werden visuell oder strukturell gruppiert, um die Organisationsstruktur abzubilden.

### 3.4 Modul: Fachbereiche (Radiologie vs. Nuklearmedizin)
Die Anwendung unterscheidet klar zwischen den beiden medizinischen Hauptsäulen, integriert sie aber visuell einheitlich.
* **Radiologie:** Fokus auf bildgebende Diagnostik (Röntgen, CT, MRT).
* **Nuklearmedizin:** Fokus auf funktionelle Diagnostik (Szintigraphie, Schilddrüsendiagnostik).
* **Integration:** Trotz der fachlichen Trennung bleibt das "Look & Feel" konsistent, sodass der Nutzer die Seite nicht "verlässt", sondern lediglich den Kontext wechselt.

### 3.5 Modul: Kontakt und Terminvereinbarung
Der operative Abschluss der Nutzerreise.
* **Informationsblöcke:** Klare Darstellung von Adresse, Telefonnummern und Öffnungszeiten.
* **Interaktive Elemente:**
    * **Telefon-Links:** Auf mobilen Geräten löst ein Klick auf die Telefonnummer direkt den Anruf aus (`tel:`-Protokoll).
    * **E-Mail-Links:** Öffnen den Standard-Mail-Client.
* **Standortvisualisierung:** Integration oder Verlinkung zu Kartendiensten zur einfachen Routenplanung.

---

## 4. Technische Interaktionen und Systemverhalten

### 4.1 Ladeverhalten und Performance
Die Anwendung ist auf **minimale Ladezeiten** optimiert. Bilder (Teamporträts, Gerätefotos) werden in web-optimierten Formaten ausgeliefert, um auch bei mobilen Datenverbindungen einen sofortigen Seitenaufbau zu gewährleisten (Lazy Loading Prinzipien).

### 4.2 Fehlerbehandlung aus Nutzersicht
* **Tote Links / 404:** Sollte ein Inhalt nicht verfügbar sein, wird der Nutzer über die Hauptnavigation stets auf sichere Pfade zurückgeführt.
* **Formularvalidierung (falls vorhanden):** Bei Kontaktformularen gibt das System visuelles Feedback (rote Umrandung, Hinweistext), wenn Pflichtfelder fehlen oder Formate (z.B. E-Mail-Adresse) ungültig sind.

### 4.3 Barrierefreiheit (Accessibility)
Die Anwendung berücksichtigt grundlegende Standards der Barrierefreiheit:
* **Kontrastverhältnisse:** Text hebt sich deutlich vom Hintergrund ab.
* **Semantisches HTML:** Die Struktur (Überschriften H1-H6) ist logisch aufgebaut, was Screenreadern die Interpretation der Seite ermöglicht.
* **Alt-Tags:** Bildinhalte sind mit beschreibenden Texten versehen, sodass Informationen auch ohne visuelle Darstellung zugänglich bleiben.

---

## 5. Datenmanagement und Aktualität

### 5.1 Statische Integrität
Die Anwendung basiert auf einer **statischen Architektur**. Dies bedeutet:
* **Sicherheit:** Da keine Datenbank im Hintergrund live abgefragt wird, ist die Angriffsfläche für Cyberattacken minimiert.
* **Verlässlichkeit:** Die angezeigten Informationen (Öffnungszeiten, Telefonnummern) sind fest im Code verankert ("Hardcoded") oder in Markdown-Dateien hinterlegt, was eine unveränderliche Darstellung bis zum nächsten administrativen Update garantiert.

### 5.2 Browser-Kompatibilität
Das System unterstützt alle modernen Browser (Chrome, Firefox, Safari, Edge) sowie deren mobile Äquivalente. Veraltete Browser werden durch "Graceful Degradation" unterstützt – das Layout vereinfacht sich möglicherweise, die Kerninformationen bleiben jedoch lesbar.

---

## 6. Zusammenfassung der Nutzerreise (User Journey)

Ein typischer Anwendungsfall gestaltet sich wie folgt:
1.  **Einstieg:** Der Nutzer sucht nach "Radiologie St. Georg" und landet auf der **Startseite**. Das responsive Design passt sich sofort seinem Smartphone an.
2.  **Information:** Er wählt über das **Hamburger-Menü** den Punkt "Leistungsspektrum", um sich über eine MRT-Untersuchung zu informieren.
3.  **Orientierung:** Durch klare Typografie liest er die Vorbereitungshinweise.
4.  **Validierung:** Ein Klick auf "Team" zeigt ihm die behandelnden Ärzte, was durch professionelle Bilder Vertrauen schafft.
5.  **Aktion:** Über den **Kontakt-Button** im Footer oder Header wählt er die Nummer der Anmeldung direkt an, um einen Termin zu vereinbaren.

Die Anwendung ist somit nicht nur eine Informationsbroschüre, sondern ein **aktives Werkzeug zur Patientensteuerung und -bindung**.