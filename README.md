# 🏵️ PunjabiMaster Enhanced — Vollständige Dokumentation

> Eine umfassende, dreisprachige Punjabi-Lernplattform (Punjabi ↔ Deutsch ↔ Türkisch), gebaut als einzelne, eigenständige HTML-Datei. Kein Server, kein Build-Prozess, keine Abhängigkeiten — einfach in jedem Browser öffnen.

---

## Inhaltsverzeichnis

1. [Überblick](#überblick)
2. [Architektur & Technologie](#architektur--technologie)
3. [Inhaltsinventar](#inhaltsinventar)
4. [Funktionen im Detail](#funktionen-im-detail)
5. [Seite-für-Seite-Anleitung](#seite-für-seite-anleitung)
6. [Datenstrukturen](#datenstrukturen)
7. [Abzeichen-System](#abzeichen-system)
8. [Quiz-Engine](#quiz-engine)
9. [Fortschritt & Speicherung](#fortschritt--speicherung)
10. [Sprachausgabe](#sprachausgabe)
11. [Dunkelmodus](#dunkelmodus)
12. [Mobile Optimierung](#mobile-optimierung)
13. [Bereitstellung](#bereitstellung)
14. [Anleitung für zukünftige Erweiterungen](#anleitung-für-zukünftige-erweiterungen)

---

## Überblick

PunjabiMaster Enhanced ist eine gamifizierte Sprachlern-App, die Deutschsprachigen und Türkischsprachigen Punjabi beibringt. Sie folgt dem GER-Rahmenwerk (A1–C2) mit Karteikarten-Lektionen, Quizzen, kulturellen Inhalten zur Sikh-Geschichte und einem umfassenden Abzeichen-/XP-Belohnungssystem.

### Kennzahlen

| Metrik | Anzahl |
|--------|--------|
| Lektionen gesamt | 38 |
| Phrasen gesamt | 481 |
| GER-Stufen | 6 (A1–C2) |
| Abzeichen-Typen | 42 |
| Quiz-Fragetypen | 4 |
| Dokumentierte Sikh-Gurus | 10 |
| Dokumentierte Feste | 8 |
| Kulturelle Konzepte | 8 |
| Grammatik-Referenztabellen | 5 |
| Dateigrösse | ~174 KB |
| Abhängigkeiten | Null |

---

## Architektur & Technologie

### Einzeldatei-Design

Die gesamte Anwendung lebt in einer einzigen `.html`-Datei:

- **CSS** (~280 Zeilen): Theming mit Custom Properties, responsives Layout, Animationen, Dunkelmodus
- **HTML** (~50 Zeilen): Navigationsrahmen und Seitencontainer (Inhalt wird per JS gerendert)
- **JavaScript** (~1600 Zeilen): Alle Daten, Rendering-Logik, Quiz-Engine, Fortschrittssystem

### Technologie-Stack

| Schicht | Technologie |
|---------|-------------|
| Markup | Vanilla HTML5 |
| Styling | Vanilla CSS3 mit Custom Properties (`--primary`, `--bg`, etc.) |
| Logik | Vanilla JavaScript (ES6+), keine Frameworks |
| Speicherung | `localStorage` (Schlüssel: `punjabi_master_progress_v3`) |
| Sprache | Web Speech API (`SpeechSynthesisUtterance`) |
| Routing | SPA-Muster mit `showPage()`-Funktion (kein Hash-Routing) |

### Warum eine Einzeldatei?

Die App war ursprünglich ein React + TypeScript + Vite + Tailwind + shadcn/ui-Projekt (`app.zip`, ~180KB Quellcode). Sie wurde als Vanilla HTML/CSS/JS neu gebaut, um folgendes zu ermöglichen:

- Bereitstellung ohne Build-Schritt (per Drag-and-Drop auf jeden Host)
- Offline-Fähigkeit (funktioniert ohne Internet nach dem ersten Laden)
- Einfache zukünftige Bearbeitung (keine Toolchain erforderlich)
- Kleinere Gesamtgrösse als das kompilierte React-Bundle (174KB vs. 566KB)

---

## Inhaltsinventar

### A1 — Absoluter Anfänger (12 Lektionen, ~167 Phrasen)

| Lektion | Phrasen | Behandelte Themen |
|---------|---------|-------------------|
| Tägliche Begrüssungen | 15 | Sat Sri Akaal, formelle/informelle Begrüssungen, Verabschiedungen, Kiddan |
| Zahlen & Zählen | 20 | 0–100, Hunderter, Tausender, Lakh-System |
| Familie & Beziehungen | 15 | Eltern, Geschwister, Grosseltern, Schwiegereltern, Unterscheidung mütterlich/väterlich |
| Essen & Speisen | 15 | Grundnahrungsmittel (Roti, Daal), Gerichte (Makki di Roti), Geschmacksrichtungen |
| Personalpronomen | 12 | Ich/du/er/sie, formell vs. informell, Possessive mit Geschlechtsanpassung |
| Häufige Verben | 20 | Top 20 Verben: karna, hona, jaana, khaana, bolna, samajhna etc. |
| Fragewörter | 10 | Ki, kiven, kithe, kadon, kyon, koun, kine |
| Uhrzeit & Tage | 14 | Wochentage, Tageszeiten, heute/morgen, planetarische Namensursprünge |
| Farben | 10 | Grundfarben + kulturelle Bedeutung (Laal für Hochzeiten, Kesari für Sikhs) |
| Richtungen & Orte | 12 | Links/rechts, Gurdwara, Bazaar, Krankenhaus, Moschee, Tempel |
| Adjektive & Beschreibungen | 15 | Gross/klein, schön, alt/neu, schnell/langsam, alle mit m/f-Geschlechtsformen |
| Gurmukhi-Schrift Grundlagen | 12 | Alphabetstruktur, Vokalzeichen, Nasal-/Verdopplungszeichen, Ziffern |

### A2 — Elementarstufe (11 Lektionen, ~133 Phrasen)

| Lektion | Phrasen | Behandelte Themen |
|---------|---------|-------------------|
| Tagesablauf | 12 | Morgens bis abends, Ardas, Hausarbeit |
| Einkaufen & Geld | 12 | Preise, Feilschen, Rupien, Kleidergrössen |
| Im Restaurant | 12 | Bestellen, Schärfegrad, Koch loben, Bezahlen |
| Wetter & Jahreszeiten | 12 | Vier Jahreszeiten, Monsun, Temperatur, Wind |
| Körper & Gesundheit | 12 | Körperteile, Schmerzen, Fieber, Arztbesuch, Medizin |
| Emotionen & Gefühle | 12 | Glück, Wut, Trauer, Angst, Liebe, Hoffnung, Sorge |
| Verkehrsmittel | 10 | Bus, Zug, Rikscha, Motorrad, Flugzeug, Fahrkarten |
| Kleidung & Mode | 12 | Salwar Kameez, Dastar/Turban, Chunni, Jutti, Phulkari, Lehnga |
| Haus & Haushalt | 13 | Zimmer, Möbel, Türen/Fenster, Licht, Schlüssel, Putzen |
| Notfallphrasen | 12 | Hilfe, Polizei, Krankenwagen, Feuer, Verlaufen, Diebstahl |
| Tiere & Natur | 12 | Kuh, Büffel, Pferd, Pfau, Bäume, Blumen, Punjabs 5 Flüsse |

### B1 — Mittelstufe (8 Lektionen, ~94 Phrasen)

| Lektion | Phrasen | Behandelte Themen |
|---------|---------|-------------------|
| Komplexe Verbformen | 12 | Verlaufsform, Plusquamperfekt, Futur, Konditional, Obligation, Fähigkeit |
| Reisen & Tourismus | 12 | Visum, Hotel, Goldener Tempel, Wagah-Grenze, Dorftourismus |
| Geschäft & Arbeit | 12 | Berufe, Meetings, Fristen, Gehalt, E-Mail, Urlaub |
| Slang & Umgangssprache | 12 | Yaar, oye, chakk de, balle balle, gabru, gedi route |
| Punjabi-Musik & Bhangra | 10 | Dhol, Tumbi, Gidda, Boliyan, Sufi-Musik, Nusrat Fateh Ali Khan |
| Hobbys & Sport | 12 | Cricket, Kabaddi, Ringen, Pollywood, Lesen, Landwirtschaft |
| Technologie & Handy | 12 | Nachrichten, Anrufe, WLAN, Fotos, Akku, Apps, Online-Bestellung |
| Berufe & Jobs | 12 | Arzt, Lehrer, Kisaan (Bauer), Ingenieur, Anwalt, Koch |

### B2 — Obere Mittelstufe (3 Lektionen, ~36 Phrasen)

| Lektion | Phrasen | Behandelte Themen |
|---------|---------|-------------------|
| Formelle Sprache | 12 | Ehrentitel, formelle Bitten, Waheguru ji ka Khalsa |
| Sprichwörter & Weisheiten | 10 | Traditionelle Redewendungen mit deutschen/türkischen Entsprechungen |
| Punjabi-Hochzeiten | 14 | Vollständiger Hochzeitswortschatz: Mehndi, Sangeet, Baraat, Anand Karaj, Doli, Jaggo, Shagun |

### C1 — Fortgeschritten (3 Lektionen, ~32 Phrasen)

| Lektion | Phrasen | Behandelte Themen |
|---------|---------|-------------------|
| Redewendungen | 10 | Körper-basierte Idiome, emotionale Ausdrücke, kulturelle Metaphern |
| Poesie & Literatur | 10 | Heer Ranjha, Bulleh Shah, Waris Shah, Amrita Pritam, Sufi-Poesie |
| Tiefes Kulturwissen | 12 | Ik Onkar, Guru Granth Sahib, Seva, Langar, Drei Säulen, Ardas |

### C2 — Meisterschaft (1 Lektion, 10 Phrasen)

| Lektion | Phrasen | Behandelte Themen |
|---------|---------|-------------------|
| Meisterschaft & Nuancen | 10 | Philosophischer Ausdruck, Diaspora-Identität, Dorfnostalgie, göttliche Liebe |

### Kulturbereich (kein Unterricht — Referenzmaterial)

| Bereich | Einträge | Inhalt |
|---------|----------|--------|
| Die 10 Gurus | 10 | Vollständige Zeitleiste mit Jahren, Titeln, Beiträgen, historischem Kontext |
| Feste & Feiern | 8 | Vaisakhi, Bandi Chhor Divas, Hola Mohalla, Gurpurabs, Lohri, Maghi, Rakhar Punia |
| Schlüsselkonzepte | 8 | Langar, Seva, 5 Ks, Guru Granth Sahib, Nishan Sahib, Dasvandh, Amrit Sanchar, Sangat/Pangat |
| Grammatik-Referenz | 5 Tabellen | SOV-Wortstellung, Geschlechtersystem, Zeitformen, Postpositionen, Höflichkeitsstufen |

---

## Funktionen im Detail

### 1. Karteikarten-Lernsystem

Jede Lektion präsentiert Phrasen als interaktive Karteikarten:

- **Vorderseite**: Punjabi-Text + romanisierte Aussprache
- **Rückseite**: Übersetzung (Deutsch oder Türkisch je nach Einstellung) + Grammatikhinweis
- **3D-Flip-Animation** beim Tippen/Klicken
- **Lautsprecher-Button** für Aussprache (Web Speech API)
- **Hörübungsbereich** unter jeder Karte mit 3 Geschwindigkeiten: 🐢 langsam (0.5x), ▶ normal (0.8x), 🐇 schnell (1.2x)
- **Navigation**: Vor/Zurück-Pfeile mit Fortschrittsanzeige

### 2. Quiz-Engine

Vier Fragetypen, dynamisch aus Lektionsphrasen generiert:

| Typ | Funktionsweise |
|-----|---------------|
| **Multiple Choice** (Punjabi → Übersetzung) | „Was bedeutet ‚Sat Sri Akaal'?" mit 4 Optionen |
| **Umgekehrtes MC** (Übersetzung → Punjabi) | „Wie sagt man ‚Danke' auf Punjabi?" mit 4 Optionen |
| **Lückentext** | Ein Wort wird aus der Punjabi-Phrase entfernt; eingeben |
| **Hörverstehen** | Audio spielt automatisch ab; wähle die gehörte Phrase |

Quiz-Funktionen:
- 10 Fragen pro Quiz (zufällig aus allen Typen gemischt)
- Fortschrittsbalken zeigt Abschluss
- Hinweise verfügbar (Aussprache oder Übersetzung)
- Sofortiges Richtig/Falsch-Feedback mit Animationen
- Ergebnisseite mit Prozentsatz und verdienten XP
- **Fehlerüberprüfung** — zeigt jeden Fehler mit der richtigen Antwort
- Falsche Antworten werden für den Wiederholungsmodus gespeichert

### 3. Tagesziel-System

- Konfigurierbares Ziel: 10, 15, 20 oder 30 Phrasen pro Tag (Einstellungsseite)
- Visueller Fortschrittsbalken auf dem Dashboard (grüne Verlaufskarte)
- Verfolgt, wie viele Phrasen heute gelernt wurden
- Setzt um Mitternacht zurück
- Abschluss des Tagesziels verdient das „Tagesziel"-Abzeichen
- Abschluss an 7 verschiedenen Tagen verdient das „Wochenziel"-Abzeichen

### 4. Wiederholungsmodus

- Dashboard zeigt eine rote Karte, wenn falsche Quiz-Antworten vorhanden sind
- Antippen startet eine Karteikarten-Übung nur mit schwachen Phrasen
- Sobald eine Phrase in einem Quiz richtig beantwortet wird, wird sie aus der Wiederholungsliste entfernt
- Gespeichert in `progress.wrongPhrases`

### 5. Streak-System

- Verfolgt aufeinanderfolgende Lerntage
- Angezeigt in der oberen Navigationsleiste und im Dashboard
- **Streak-Freeze**: 1 kostenloser Ausfall pro Woche — wird automatisch angewendet, wenn genau 1 Tag verpasst wird
- Freeze-Nutzung wird pro Kalenderwoche verfolgt
- **Comeback-Abzeichen**: Rückkehr nach 3+ Tagen verdient ein spezielles Abzeichen, statt nur Bestrafung

### 6. XP & Aufstiegssystem

- **Lektionsabschluss**: +50 XP
- **Richtige Quiz-Antwort**: +5 XP pro Frage
- **Level**: berechnet als `Math.floor(XP / 500) + 1`
- Level-Fortschrittsbalken auf dem Dashboard

### 7. Dunkelmodus

- Umschalter auf der Einstellungsseite
- Vollständiges CSS-Theme mit Custom-Properties-Überschreibung
- Dunkelviolettes Farbschema (#0f0d1a Hintergrund, #1e1b2e Karten)
- In `progress.settings.darkMode` gespeichert
- Beim Seitenaufruf über `body.dark`-Klasse angewendet

### 8. Konfetti-Animation

- Wird ausgelöst bei: Lektionsabschluss, Abzeichen-Freischaltung
- 50 bunte Partikel mit zufälligen Farben, Grössen und Verzögerungen
- Entfernt sich automatisch nach 4 Sekunden
- CSS-Keyframe-Animation (keine JS-Animationsbibliothek)

### 9. Grammatik-Referenz

Ein eigener Tab im Kulturbereich mit 5 Vergleichstabellen:

1. **Wortstellung (SOV)** — Punjabi vs. Deutsch vs. Türkisch Satzstruktur
2. **Geschlechtersystem** — Maskulin (-a) vs. Feminin (-i) Adjektivendungen
3. **Zeitformen** — Präsens, Verlaufsform, Vergangenheit, Zukunft mit dreisprachigen Beispielen
4. **Postpositionen** — vich (in), te (auf), ton (von), naal (mit), lai (für)
5. **Höflichkeitsstufen** — Tu/Tussi/Aap ji Hierarchie

### 10. Fortschrittsmigration

- Erkennt automatisch altes `punjabi_master_progress_v2` im localStorage
- Migriert XP, Streaks, abgeschlossene Lektionen, Quiz-Ergebnisse ins v3-Format
- Zeigt Toast-Benachrichtigung bei erfolgreicher Migration
- Läuft nur einmal (prüft, ob v3-Schlüssel bereits existiert)

---

## Seite-für-Seite-Anleitung

### Dashboard (`page-dashboard`)

Von oben nach unten:
1. **Hero-Karte** — Willkommensnachricht mit 4 Statistiken (XP, Streak, Lektionen, Fortschritt %)
2. **Level-Fortschrittsbalken** — XP innerhalb des aktuellen Levels
3. **Tagesziel-Karte** — grüner Verlauf, heutige Phrasenzahl vs. Ziel
4. **Streak-Freeze-Anzeige** — zeigt ob Freeze diese Woche verfügbar ist
5. **Wiederholungskarte** — rote Karte, nur sichtbar bei falschen Quiz-Antworten
6. **Empfohlene Lektion** — erste nicht abgeschlossene Lektion mit farbcodiertem Level-Badge
7. **Schnellaktions-Buttons** — Alle Lektionen, Kultur, Schnell-Quiz, Abzeichen
8. **Level-Übersicht** — Fortschrittsbalken pro GER-Stufe (A1–C2)
9. **Letzte Quiz-Ergebnisse** — die letzten 3 Quiz-Ergebnisse mit farbcodierten Noten

### Lehrplan (`page-curriculum`)

- Alle 38 Lektionen nach GER-Stufe organisiert
- Jede Stufe hat ein farbiges Badge, Beschreibung und Abschlusszähler
- Lektionskarten zeigen: Icon, Titel, Beschreibung, Phrasenanzahl, XP-Belohnung, Abschlussstatus
- Grünes Häkchen bei abgeschlossenen Lektionen
- Responsives Raster: 1 Spalte mobil, 2 Spalten Tablet+

### Lektion (`page-lesson`)

- Zurück-Button zum Lehrplan
- Level-Badge + Lektionstitel
- Fortschrittsbalken (aktuelle Karte / Gesamt)
- 3D-Karteikarte mit Vorder-/Rückseite
- Navigationspfeile + Sprechen-Button + Zähler
- Hörübungskarte (3 Geschwindigkeiten)
- Abschlussaufforderung bei der letzten Karte (Abschliessen oder Quiz starten)

### Quiz (`page-quiz`)

- Fortschrittsbalken + Fragenzähler
- Fragetyp bestimmt UI:
  - MC/Hörverstehen: antippbare Optionskarten
  - Lückentext: Texteingabe mit Absenden-Button
- Hörfragen: automatische Wiedergabe + Geschwindigkeitsregler
- Ergebnisseite: Punktzahl %, Emoji, verdiente XP, Fehlerüberprüfung

### Kultur (`page-culture`)

Vier Tabs:
1. **Die 10 Gurus** — vertikale Zeitleiste mit farbigen Punkten, Jahren, Titeln, Beschreibungen
2. **Feste & Feiern** — 8 Festkarten mit Emoji, Datum, Beschreibung, Gurmukhi-Text
3. **Schlüsselkonzepte** — 8 Konzeptkarten + Drei-Säulen-Hervorhebung
4. **Grammatik** — 5 Vergleichstabellen (SOV, Geschlecht, Zeitformen, Postpositionen, Höflichkeit)

### Abzeichen (`page-badges`)

- Trophäen-Hero-Karte mit Verdient/Gesamt-Zähler und Prozentsatz
- Verdientes-Abzeichen-Raster (goldener Rand, Verlaufshintergrund)
- Gesperrtes-Abzeichen-Raster (ausgegraut, 50% Transparenz)
- Responsives Raster: 2 Spalten mobil, 3 Spalten Tablet+

### Suche (`page-search`)

- Sucheingabe mit Icon
- Echtzeit-Filterung über alle Felder: Punjabi, Aussprache, Deutsch, Türkisch, Grammatiknotizen
- Ergebnisse zeigen: Punjabi-Text, Aussprache, Übersetzung, Lektionsname, Level-Badge
- Klick auf ein Ergebnis öffnet die zugehörige Lektion
- Mindestens 2 Zeichen zum Suchen, maximal 50 angezeigte Ergebnisse

### Einstellungen (`page-settings`)

- Sprachumschalter (Deutsch/Türkisch)
- Sprechgeschwindigkeit (langsam/normal/schnell)
- Dunkelmodus-Umschalter
- Tagesziel-Auswahl (10/15/20/30)
- Statistik-Panel (XP, Streak, längster Streak, Lektionen, Quizze, Abzeichen, Level, Hör-Zähler)
- Inhaltsübersicht (Lektionen und Phrasen pro Level)
- Fortschritt-zurücksetzen-Button (mit Bestätigungsdialog)
- Suchlink

---

## Datenstrukturen

### Phrasen-Objekt

```javascript
{
  punjabi: "Sat Sri Akaal",        // Punjabi-Text (romanisiert oder Gurmukhi)
  pron: "sut sree uh-KAAL",       // Romanisierte Aussprachehilfe
  de: "Hallo / Guten Tag",        // Deutsche Übersetzung
  tr: "Merhaba (resmi)",          // Türkische Übersetzung
  note: "Universellste Begrüssung..."  // Grammatik-/Kulturnotiz
}
```

### Lektions-Objekt

```javascript
{
  id: "a1-greetings",             // Eindeutige ID (Level-Thema-Format)
  title: "Daily Greetings",       // Anzeigename
  category: "greetings",          // Kategorie für Gruppierung
  icon: "🙏",                    // Emoji-Icon
  xp: 50,                        // XP-Belohnung bei Abschluss
  description: "Essential...",    // Kurzbeschreibung
  phrases: [ /* Phrasen-Objekte */ ]
}
```

### Fortschritts-Objekt (localStorage)

```javascript
{
  xp: 0,                         // Gesamte Erfahrungspunkte
  streak: 0,                     // Aktuelle aufeinanderfolgende Tage
  longestStreak: 0,              // Allzeit-Beststreak
  lastStudyDate: null,           // ISO-Datumsstring "2024-01-15"
  completedLessons: [],          // Array von Lektions-IDs
  quizScores: [],                // Array von Quiz-Ergebnis-Objekten
  badges: [],                    // Array von verdienten Abzeichen-IDs
  level: 1,                      // Aktuelles Level (XP / 500 + 1)
  wrongPhrases: [],              // Falsch beantwortete Punjabi-Texte
  listenCount: 0,                // Gesamte Sprechen-Button-Klicks
  nightStudy: false,             // Nach 22 Uhr gelernt
  earlyStudy: false,             // Vor 7 Uhr gelernt
  sessionLessons: 0,             // Heute abgeschlossene Lektionen
  cultureRead: 0,                // Besuchte einzigartige Kultur-Tabs
  dailyGoal: { date, count, target },  // Tägliche Phrasen-Ziel-Verfolgung
  dailyGoalDays: 0,              // Tage, an denen das Tagesziel erreicht wurde
  streakFreezeUsed: 0,           // Gesamte verwendete Streak-Freezes
  settings: {
    language: "de",              // "de" oder "tr"
    speechRate: 0.8,             // 0.5, 0.8 oder 1.2
    darkMode: false              // Dunkelmodus-Umschalter
  }
}
```

---

## Abzeichen-System

### 42 Abzeichen nach Kategorie

#### Lektions-Meilensteine (5)

| Abzeichen | Anforderung |
|-----------|------------|
| 🌟 Erste Schritte / İlk Adımlar | 1 Lektion abschliessen |
| 📚 Fleissig / Çalışkan | 5 Lektionen abschliessen |
| 🧭 Forscher / Kaşif | 10 Lektionen abschliessen |
| 🎓 Gelehrter / Alim | 20 Lektionen abschliessen |
| 👑 Meister / Usta | ALLE Lektionen abschliessen |

#### Streak-Abzeichen (4)

| Abzeichen | Anforderung |
|-----------|------------|
| 🔥 Auf Kurs / Yolda | 3-Tage-Streak |
| 🔥 Woche Meister / Hafta Ustası | 7-Tage-Streak |
| 🔥 Zwei Wochen / İki Hafta | 14-Tage-Streak |
| 🔥 Monat Champion / Ay Şampiyonu | 30-Tage-Streak |

#### XP-Stufen (5)

| Abzeichen | Anforderung |
|-----------|------------|
| ⚡ Anfänger / Başlangıç | 100 XP |
| ⚡ Fortgeschritten / İleri | 500 XP |
| ⚡ Punjabi Pro | 1.000 XP |
| ⚡ Dil Meister / Dil Ustası | 2.500 XP |
| 👑 Sprachmeister / Dil Şampiyonu | 5.000 XP |

#### Quiz-Abzeichen (7)

| Abzeichen | Anforderung |
|-----------|------------|
| 🎯 Erste Quiz / İlk Sınav | 1 Quiz abschliessen |
| 🎯 Quiz Liebhaber / Sınav Sever | 5 Quizze abschliessen |
| 🎯 Quiz Fan | 10 Quizze abschliessen |
| 🎯 Quiz Veteran | 20 Quizze abschliessen |
| 💯 Perfektionist | 100% in einem Quiz |
| 🏆 Quiz Meister / Sınav Ustası | 5× 100% in Quizzen |
| 💎 Diamant / Elmas | 3× 100% hintereinander |

#### Level-Abschluss (6)

| Abzeichen | Anforderung |
|-----------|------------|
| 🟢 A1 Absolvent / A1 Mezunu | Alle A1-Lektionen abschliessen |
| 🟡 A2 Absolvent / A2 Mezunu | Alle A2-Lektionen abschliessen |
| 🔵 B1 Absolvent / B1 Mezunu | Alle B1-Lektionen abschliessen |
| 🟣 B2 Absolvent / B2 Mezunu | Alle B2-Lektionen abschliessen |
| 🟠 C1 Absolvent / C1 Mezunu | Alle C1-Lektionen abschliessen |
| 🔴 C2 Meister / C2 Usta | Alle C2-Lektionen abschliessen |

#### Spezial-Abzeichen (10)

| Abzeichen | Anforderung |
|-----------|------------|
| 🌍 Kultur Forscher / Kültür Kaşifi | Alle 3 Kultur-Tabs besuchen |
| 🦉 Nachteule / Gece Kuşu | Nach 22 Uhr lernen |
| 🐦 Frühaufsteher / Erken Kalkan | Vor 7 Uhr lernen |
| 🗣️ Polyglott / Çok Dilli | Quizze in beide Richtungen (DE und TR) |
| ⏱️ Schnelllerner / Hızlı Öğrenci | 3 Lektionen in einer Sitzung |
| 🎧 Zuhörer / Dinleyici | 10× Hörmodus verwenden |
| 🎶 Klangmeister / Ses Ustası | 50× Hörmodus verwenden |
| 🧊 Streak Saver | Einen Streak-Freeze verwenden |
| 🌗 Halbzeit / Yarı Yol | Die Hälfte aller Lektionen abschliessen |
| 🔄 Comeback Kid | Nach 3+ Tagen Pause zurückkehren |

#### Inhaltsspezifische Abzeichen (5)

| Abzeichen | Anforderung |
|-----------|------------|
| 🎯 Tagesziel / Günlük Hedef | Tagesziel erreichen (15 Phrasen) |
| 📅 Wochenziel / Haftalık Hedef | Tagesziel an 7 verschiedenen Tagen erreichen |
| 💒 Hochzeitsexperte / Düğün Uzmanı | Hochzeits-Lektion abschliessen |
| ✍️ Gurmukhi Leser / Okuyucu | Gurmukhi-Lektion abschliessen |

---

## Quiz-Engine

### Fragengenerierungs-Algorithmus

Beim Start eines Quiz für eine Lektion:

1. Jede Phrase generiert 1–3 Fragen abhängig vom Index:
   - `index % 3 === 0` ODER `index % 5 === 0` → Multiple Choice (Punjabi → Übersetzung)
   - `index % 3 === 1` → Umgekehrtes MC (Übersetzung → Punjabi)
   - `index % 3 === 2` UND Phrase hat 2+ Wörter → Lückentext
   - `index % 4 === 0` → Hörfrage

2. Falsche Optionen werden zufällig aus ALLEN Phrasen aller Lektionen gezogen (nicht nur der aktuellen), für vielfältige Distraktoren.

3. Fragen werden gemischt und auf 10 pro Quiz begrenzt.

4. Übersetzungsrichtung passt sich der Spracheinstellung an (Deutsch oder Türkisch).

### Schnell-Quiz

- Vom Dashboard zugänglich
- Wählt zufällig eine abgeschlossene Lektion
- Generiert ein Standard-10-Fragen-Quiz aus dieser Lektion

---

## Sprachausgabe

### Implementierung

Die App nutzt die Web Speech API mit Punjabi-Sprachpräferenz:

- Versucht zuerst `pa-IN` (Punjabi), fällt auf `hi-IN` (Hindi) zurück
- Drei Geschwindigkeitsmodi: 🐢 langsam (0.5x), ▶ normal (0.8x), 🐇 schnell (1.2x)
- Geschwindigkeit in den Einstellungen konfigurierbar

### Sicheres Sprechen-System

Um Fehler mit Gurmukhi-Schrift und Sonderzeichen in Inline-`onclick`-Handlern zu vermeiden, verwendet die App ein indexbasiertes System. Phrasen werden beim Rendern registriert und per Index referenziert — keine Escaping-Probleme.

### Browser-Unterstützung

| Browser | Qualität |
|---------|----------|
| Chrome (Desktop) | Beste Unterstützung, hat oft Hindi-Stimme |
| Safari (iOS) | Gute Hindi/Punjabi-Stimmen |
| Firefox | Eingeschränkte Stimmauswahl |
| Android Chrome | Hat normalerweise Hindi-Stimme |

---

## Dunkelmodus

Der dunkle Modus überschreibt CSS Custom Properties auf `body.dark`:

- Hintergrund: `#0f0d1a` (tiefes Purpur-Schwarz)
- Karten: `#1e1b2e` (dunkler Kartenhintergrund)
- Text: `#e2e0f0` (helles Purpur)
- Status wird in `progress.settings.darkMode` gespeichert und beim Laden angewendet

---

## Mobile Optimierung

### Untere Tab-Navigation

- 5 Tabs: Start, Lektionen, Kultur, Abzeichen, Mehr (Einstellungen/Suche)
- Am unteren Rand fixiert mit `safe-area-inset-bottom` für Handys mit Notch
- Auf Desktop (≥768px) ausgeblendet; Desktop nutzt obere Navigationslinks
- Aktiver Tab durch lila Punkt und Farbwechsel angezeigt

### Responsive Breakpoints

| Breakpoint | Layout-Änderungen |
|-----------|-------------------|
| < 600px | Einspaltige Lektionsraster, volle Kartenbreite |
| ≥ 600px | Zweispaltige Lektions- und Abzeichenraster |
| ≥ 768px | Untere Nav ausgeblendet, obere Nav-Links sichtbar, dreispaltige Abzeichen |

---

## Bereitstellung

### Option 1: Statischer Datei-Upload

`PunjabiMaster_Enhanced.html` auf beliebiges statisches Hosting hochladen:
- GitHub Pages, Netlify (Drag-and-Drop), Vercel, Firebase Hosting
- Jeder Webserver (Apache, Nginx)

### Option 2: Lokale Nutzung

HTML-Datei doppelklicken, um sie in einem modernen Browser zu öffnen. Funktioniert komplett offline nach dem ersten Laden.

### Option 3: PWA-bereit

Die Datei enthält Mobile-Web-App-Meta-Tags. Für eine vollständige PWA müssten ein `manifest.json` und ein Service Worker hinzugefügt werden.

---

## Anleitung für zukünftige Erweiterungen

### Benötigte Dateien

**Nur diese eine HTML-Datei.** Lade sie hoch und beschreibe die gewünschten Änderungen. Keine Build-Tools, kein package.json, keine node_modules erforderlich. Die alte `app.zip` wird nicht mehr benötigt.

### Neue Lektion hinzufügen

1. Finde das passende Level-`lessons`-Array im JavaScript
2. Füge ein neues Lektionsobjekt vor der schliessenden `]` hinzu:

```javascript
{
  id: "a1-neuelektion",         // Muss einzigartig sein, Format: level-thema
  title: "Neues Thema",
  category: "kategorie",
  icon: "🆕",
  xp: 50,                     // 50 für A1, 60 für A2, 80 für B1, 100 für B2, 120 für C1
  description: "Kurze Beschreibung",
  phrases: [
    {
      punjabi: "Punjabi-Text",
      pron: "romanisierte Aussprache",
      de: "Deutsche Übersetzung",
      tr: "Türkische Übersetzung",
      note: "Grammatik- oder Kulturnotiz"
    }
  ]
}
```

3. Quiz-Engine, Suche und Abzeichensystem erkennen die neue Lektion automatisch.

### Neues Abzeichen hinzufügen

Zum `ALL_BADGES`-Array hinzufügen:

```javascript
{
  id: "einzigartige-id",
  name: "🏅 Abzeichenname / Türkçe İsim",
  desc: "Wie man dieses Abzeichen verdient",
  condition: p => p.einFeld >= einWert
}
```

Die `condition`-Funktion erhält das vollständige Fortschrittsobjekt und gibt `true` zurück, wenn das Abzeichen vergeben werden soll.

---

## Versionshistorie

| Version | Speicherschlüssel | Beschreibung |
|---------|-------------------|-------------|
| v1 | (Original React App) | React + TypeScript + Vite Build, 566KB kompiliert |
| v2 | `punjabi_master_progress_v2` | Original bereitgestellte Version |
| v3 | `punjabi_master_progress_v3` | Diese erweiterte Version, Vanilla HTML, migriert automatisch von v2 |

---

## Dank & kultureller Hinweis

Diese App wurde mit tiefem Respekt für die punjabische Sprache, die Sikh-Geschichte und das kulturelle Erbe des Punjab erstellt. Die Inhalte umfassen Traditionen sowohl des indischen als auch des pakistanischen Punjab und beinhalten Vokabular und Begrüssungen aus Sikh-, muslimischen und hinduistischen Gemeinschaften.

Der dreisprachige Ansatz (Punjabi ↔ Deutsch ↔ Türkisch) dient den grossen Punjabi-Diaspora-Gemeinschaften im deutsch- und türkischsprachigen Raum und nutzt die grammatischen Ähnlichkeiten zwischen Punjabi und Türkisch (beides SOV-Sprachen mit Postpositionen und Agglutination).

**ਸਤ ਸ੍ਰੀ ਅਕਾਲ — Sat Sri Akaal — Wahrheit ist zeitlos**
