# DESIGN SPECIFICATION: "TOURIST BURMA (1962–1988)"
## Digital Heritage Archive & Interactive Exhibition System

* **Document Version:** 1.0.0  
* **Classification:** Public History / Digital Humanities / Archival Web Design  
* **Subject Focus:** State-Controlled Tourism under the Burma Socialist Programme Party (BSPP)  
* **Source Archive:** [archival_record_tourist_burma_1962_1988.md](file:///c:/Users/JM505%20Computers/Desktop/touristburma/archival_record_tourist_burma_1962_1988.md)  
* **Target Audience:** Historians, Cultural Researchers, Students, Museum Visitors, and Southeast Asian Heritage Enthusiasts  

---

## Table of Contents

1. [Executive Summary & Curatorial Philosophy](#1-executive-summary--curatorial-philosophy)  
2. [Information Architecture (IA) & Site Structure](#2-information-architecture-ia--site-structure)  
3. [The Core Narrative Experience: The 168-Hour Circuit](#3-the-core-narrative-experience-the-168-hour-circuit)  
4. [Visual Design Language & Design Tokens](#4-visual-design-language--design-tokens)  
   - [4.1 Color Palette & Materiality](#41-color-palette--materiality)  
   - [4.2 Typography System & Hierarchy](#42-typography-system--hierarchy)  
   - [4.3 Textures, Stamps & Skeuomorphic Restraint](#43-textures-stamps--skeuomorphic-restraint)  
   - [4.4 Insignia & Vector Motifs](#44-insignia--vector-motifs)  
5. [Key Interactive Components & Interface Blueprints](#5-key-interactive-components--interface-blueprints)  
   - [5.1 The Archival Document & Photograph Viewer](#51-the-archival-document--photograph-viewer)  
   - [5.2 Form C-102 Currency & Black Market Simulator](#52-form-c-102-currency--black-market-simulator)  
   - [5.3 The "Big Four" Circuit Logistics Map](#53-the-big-four-circuit-logistics-map)  
   - [5.4 The Central Press Ephemera Carousel](#54-the-central-press-ephemera-carousel)  
6. [Accessibility, Inclusivity & Archival Standards](#6-accessibility-inclusivity--archival-standards)  
7. [Technical Architecture & Performance Specifications](#7-technical-architecture--performance-specifications)  
8. [Implementation Reference: CSS Tokens & Tailwind Configuration](#8-implementation-reference-css-tokens--tailwind-configuration)  

---

## 1. Executive Summary & Curatorial Philosophy

### 1.1 The Paradox of Socialist Tourism
Between 1962 and 1988, under General Ne Win's military regime and the **Burma Socialist Programme Party (BSPP)**, Burma engaged in an unprecedented national experiment: complete ideological isolation known as the **"Burmese Way to Socialism" (*Lanzin*)**. Private industry was seized, foreign journalists and diplomats were kept at arm's length, and the country turned deliberately inward.

Yet the state faced a desperate, unyielding contradiction: **it needed hard foreign exchange.**

The state's solution was **Tourist Burma** (Trade Corporation No. 20)—a strict, monopolistic government enterprise tasked with escorting foreign tourists along a tightly choreographed route, milking their hard currency, and ejecting them precisely when their strict **7-day (168-hour) entry visa** expired.

### 1.2 Curatorial Tone: "The Bureaucratic Dossier Meets Tropical Nostalgia"
The website must neither romanticize an authoritarian era nor treat it with dismissive caricature. Instead, the design adopts the aesthetic posture of an **unsealed state dossier**:
* **Atmospheric Authenticity:** Evoking typewriter ribbon impressions, yellowed Manilla envelopes, official vermillion rubber stamps, carbon-copy triplicate receipts, and the faded grandeur of colonial teak and whirring brass ceiling fans.
* **Rigorous Scholarly Neutrality:** Presenting primary source documentation, verified currency schedules, and archival photography with precise historical citations.
* **Sensory Immersion:** Translating the claustrophobic urgency of the 7-day visa and the shadow economy into engaging, educational interactive tools.

---

## 2. Information Architecture (IA) & Site Structure

The platform uses a **dual-modality navigation model**:
1. **The Curated Exhibition (Linear Narrative):** For visitors seeking a documentary-style walkthrough of the era.
2. **The Open Archive (Faceted Exploration):** For researchers and students searching specific artifacts, logs, transport manifests, or geographical locations.

```
+-----------------------------------------------------------------------------------+
|                           TOURIST BURMA (1962–1988)                               |
|                         STATE ARCHIVE & EXHIBITION                                |
+-----------------------------------------------------------------------------------+
                                          |
    +-------------------------------------+-----------------------------------+
    |                                                                         |
    v                                                                         v
[ EXHIBITION: "THE 168 HOURS" ]                              [ THE DIGITAL VAULT ]
  |-- Prologue: The Iron Curtain of Lanzin (1962)              |-- Document Index (Declassified)
  |-- Act I: Trade Corp No. 20 (Monopoly)                      |-- Ephemera & Printings
  |-- Act II: The "Big Four" Transit Loop                      |-- Historical Photography
  |-- Act III: The Strand & State Fleets                       |-- Currency & Form C-102 Logs
  |-- Act IV: 555 & Johnnie Walker Economy                     |-- Oral Histories & Visitor Accounts
  |-- Epilogue: 8888 & The Great Transition                    |-- Scholarly Citations & Index
```

### 2.1 Complete URL & Route Hierarchy

| Route Path | View Title | Primary Purpose |
| :--- | :--- | :--- |
| `/` | *Gateway / Index* | Declassified archival cover page, mission statement, dual-entry portal. |
| `/exhibition` | *The 168-Hour Walkthrough* | Parallax-scrolling chronological exhibition divided into 6 distinct historical acts. |
| `/circuit` | *The "Big Four" Circuit* | Interactive cartographic explorer tracing Rangoon, Mandalay, Pagan, and Inle Lake. |
| `/strand` | *The Strand Case Study* | Deep dive into state-run hospitality, faded colonial luxury, and vintage fleet logistics. |
| `/economy` | *Kyats & Contraband* | Economic interactive: Form C-102, black market exchange, and carton diplomacy. |
| `/vault` | *Archival Repository* | Filterable database of digitized primary sources, brochures, visa stamps, and manifests. |
| `/vault/[artifact-id]` | *Document Inspector* | High-resolution deep zoom, transcription toggle, metadata citation drawer. |
| `/about` | *Archival Disclosures* | Historical methodology, source acknowledgments, and academic bibliography. |

---

## 3. The Core Narrative Experience: The 168-Hour Circuit

A signature experience of the website is **"The 168-Hour Clock"**—an interactive temporal scrubber that anchors the user's journey. Because tourists in the 1970s and 1980s were restricted to a strict 7-day visa (168 hours), the exhibition journey visualizes the pressure of state surveillance and logistical rationing:

```
[ ENTRY: Day 1 (00:00) ]  ===>  [ Day 3 (48:00) ]  ===>  [ Day 5 (96:00) ]  ===>  [ EXIT: Day 7 (168:00) ]
Mingaladon Airport              Mandalay Express         Pagan Temple Stupas      Mingaladon Departure
Form C-102 Inward Stamp         Upper-Class Sleeper      Horse Carts & Dust       Form C-102 Outward Audit
```

### 3.1 Chapter Breakdown
* **Chapter 0: The Bamboo Curtain Closes (1962 Coup)**
  * General Ne Win's revolutionary council decrees.
  * BEDC takeover and liquidation of private tour agencies.
* **Chapter 1: Trade Corporation No. 20**
  * The birth of Tourist Burma's bureaucratic apparatus at #143 Sule Pagoda Road.
  * The peacock and stupa official seal as the sole legal conduit of visitation.
* **Chapter 2: The Mandatory Circuit ("Big Four")**
  * The frantic transit between Rangoon, Mandalay, Pagan, and Inle Lake.
  * The domestic fleet: BAC Fokker F27 turboprops and rattling Hino diesel buses.
* **Chapter 3: The Strand & State Hospitality**
  * Decaying grand suites, antique ceiling fans, elderly waiters, and unpotable water warnings.
* **Chapter 4: The Kyat, The Red Label & The 555s**
  * Official rate (6.85 Kyat/$) vs. Black market reality (20–40+ Kyat/$).
  * Duty-free cigarettes and whisky as the de facto currency of transport and temple access.
* **Chapter 5: 1988 Uprising & The Reorganization**
  * The 8888 general strike, demonetization collapse, and the dissolution of BSPP.
  * Evolution into Myanmar Hotels and Tourism Enterprise (MHTE) and the 14-day/28-day thaw.

---

## 4. Visual Design Language & Design Tokens

The visual system draws directly from the physical materiality of 1960s–1980s Burmese state documents, socialist printing presses, and tropical architecture.

### 4.1 Color Palette & Materiality

```
+------------------------------------------------------------------------------------+
| COLOR PALETTE SYSTEM                                                               |
+------------------------------------------------------------------------------------+
|  [ Crimson Seal ]    [ Aged Teak ]     [ Archival Manilla ]  [ State Green ]       |
|  #8B1E1E             #3E2723           #F4EFE6               #2E3A2F               |
|  BSPP Stamp / Wax    Strand Woodwork   Form C-102 Paper      Military Bureaucracy  |
|                                                                                    |
|  [ Pagoda Gold ]     [ Carbon Ribbon ] [ Indelible Violet ]  [ Inspection Cyan ]   |
|  #C59B27             #1C1B1A           #5E3370               #1B4F72               |
|  Temple Gilding      Typewriter Text   Entry Visa Stamp      Official Bank Stamp   |
+------------------------------------------------------------------------------------+
```

#### Detailed Token Mapping

| Token Name | Hex Code | Role & Psychological Association |
| :--- | :--- | :--- |
| `--color-paper-base` | `#F4EFE6` | Primary background. Aged cellulose / warm unbleached parchment. |
| `--color-paper-muted` | `#E8DFC8` | Secondary container fill. Card backgrounds, sidebar panels, input fields. |
| `--color-paper-border` | `#D6C8AC` | Subdued borders, table dividing lines, document edge outlines. |
| `--color-ink-primary` | `#1C1B1A` | Main text. Carbon ribbon typewriter black; high contrast, zero-sheen. |
| `--color-ink-muted` | `#544E45` | Secondary captions, timestamps, accession numbers, footnotes. |
| `--color-teak-deep` | `#3E2723` | Dark theme backgrounds, footer framing, header bars, Strand furniture accents. |
| `--color-seal-crimson` | `#8B1E1E` | Primary accent. Official state banners, urgent warnings, BSPP red seals. |
| `--color-pagoda-gold` | `#C59B27` | Decorative highlights, map pinpoints, architectural callouts. |
| `--color-stamp-violet` | `#5E3370` | Secondary accent. Authentic consular visa stamps and purple ink pad seals. |
| `--color-stamp-cyan` | `#1B4F72` | Authorized state bank stamps, immigration counters, receipt markers. |
| `--color-state-olive` | `#2E3A2F` | Military-socialist administrative tags, bus chassis accents, file tabs. |

---

### 4.2 Typography System & Hierarchy

The site balances historical state gravitas with modern, accessible legibility.

```
+------------------------------------------------------------------------------------+
| TYPOGRAPHY HIERARCHY                                                               |
+------------------------------------------------------------------------------------+
|  DISPLAY / HEADLINES     Playfair Display / Cinzel Decorative                      |
|                          "TOURIST BURMA: TRADE CORPORATION NO. 20"                |
|                                                                                    |
|  BUREAUCRATIC / DATA     Courier Prime / IBM Plex Mono                             |
|                          "REF: BSPP-TB-1978-C102 | VISA VALID: 168 HRS"            |
|                                                                                    |
|  BODY / EDITORIAL ESSAY  Lora / Newsreader / Merriweather                          |
|                          "During the reign of General Ne Win, the country entered  |
|                          one of the most drastic experiments in state isolation..."|
|                                                                                    |
|  BURMESE SCRIPT          Pyidaungsu / Noto Sans Myanmar                            |
|                          "ဟိုတယ်နှင့်ခရီးသွားလာရေးလုပ်ငန်း (၁၉၆၂ - ၁၉၈၈)"                 |
+------------------------------------------------------------------------------------+
```

* **Display Font (Titles & Editorial Headers):**
  * Primary: `Playfair Display` or `Cinzel` (Webfont)
  * Fallback: `Georgia`, `Times New Roman`, serif
  * Character: Evokes Mid-Century official state publications and colonial stationery.
* **Monospace Font (Archival Metadata, Visa Numbers, Form Fields):**
  * Primary: `Courier Prime` or `IBM Plex Mono`
  * Fallback: `Consolas`, `Monaco`, monospace
  * Character: Exact mechanical rhythm of an Olympia or Remington manual typewriter.
* **Body Font (Long-form Reading & Curatorial Narratives):**
  * Primary: `Lora` or `Newsreader`
  * Fallback: `Charter`, `Baskerville`, serif
  * Character: Warm humanist serif designed for extended digital reading comfort.
* **Burmese Script Support:**
  * System Font Stack: `Pyidaungsu`, `Noto Sans Myanmar`, `Padauk`, sans-serif.
  * Ensures accurate rendering of historical Burmese text, slogans, and ministry names.

---

### 4.3 Textures, Stamps & Skeuomorphic Restraint

To maintain digital polish while honoring historical artifacts:
1. **Subtle Grain Overlay:** A low-opacity (2.5%) SVG noise filter on `--color-paper-base` eliminates flat digital sheen and suggests archival stock.
2. **Ink Bleed & Stamp Distortion:**
   * Rubber stamps use a CSS masking technique (`mask-image` with noise or SVG filter) to render weathered, uneven ink distribution.
   * Stamps are rotated slightly between `-2.5deg` and `+3.2deg` to simulate hand-stamped immigration inspection.
3. **Receipt Perforations:** Section dividers can utilize SVG dashed perforation teeth for downloadable transit slips and Form C-102 stubs.
4. **No Cartoon Skeuomorphism:** Avoid heavy drop shadows or faux leather binders. Maintain clean modern whitespace, strict grid discipline, and crisp borders.

---

### 4.4 Insignia & Vector Motifs

The website prominently incorporates restored historical emblems:
* **The Tourist Burma Peacock-Stupa Crest:** Dual motif featuring the Burmese dancing peacock (*Daung*) enveloped by the spire of Shwedagon Pagoda.
* **The Union of Burma Seal:** 14-toothed cogwheel and rice ears (representing workers and peasants under the BSPP constitution of 1974).
* **Consular Cachets:** Oval and rectangular border rules containing registration numbers, port names (*RANGOON AIRPORT - MINGALADON*), and validity dates.

---

## 5. Key Interactive Components & Interface Blueprints

### 5.1 The Archival Document & Photograph Viewer

An inspection tool for examining declassified cables, brochures, and photographs.

```
+------------------------------------------------------------------------------------+
|  ARCHIVE VIEWER: [DOC-TB-1978-BROCHURE-P1]                        [ Zoom ] [ Esc ] |
+------------------------------------------------------------------------------------+
|                                                  | METADATA DRAWER                 |
|   +------------------------------------------+   | --------------------------------|
|   |                                          |   | Document Title:                 |
|   |          WELCOME TO SOCIALIST BURMA      |   | Official Travel Brochure (1982) |
|   |         "The Golden Land of Golden       |   |                                 |
|   |                Hospitality"              |   | Issuing Entity:                 |
|   |                                          |   | Trade Corporation No. 20        |
|   |   [ ILLUSTRATION: SHWEDAGON PAGODA ]     |   |                                 |
|   |                                          |   | Physical Medium:                |
|   |   - RANGOON: City of Pagodas             |   | Two-tone Letterpress on news-   |
|   |   - PAGAN: Ten Million Stupas            |   | print, Central Press Rangoon.   |
|   |   - MANDALAY: Heart of Culture           |   |                                 |
|   |   - INLE: Water Dwellers of Shan         |   | Archival ID:                    |
|   |                                          |   | BSPP-TB-1982-LIT-04             |
|   +------------------------------------------+   |                                 |
|   [ < Prev Page ]     [ 1 / 4 ]     [ Next Page > ] | [ Toggle Typed Transcription ]  |
|                                                  | [ Download High-Res TIF (84MB) ]|
+------------------------------------------------------------------------------------+
```

#### Viewer Features
* **Deep-Zoom Pan & Magnifier:** Supports high-resolution inspection of paper fibers, stamp ink bleed, and signatures.
* **Dual-Pane Transcription:** Split-screen or toggle mode displaying the original scanned document alongside an accessible, screen-reader-compliant typed transcript.
* **Recto / Verso Flip:** Smooth 3D turn animation to examine reverse sides containing customs notes, pencil endorsements, and security stamps.

---

### 5.2 Form C-102 Currency & Black Market Simulator

An educational simulation demonstrating the economic friction experienced by travelers and the parallel market under BSPP price controls.

```
+------------------------------------------------------------------------------------+
|  CURRENCY CONTROL FORM C-102: ECONOMIC PARADOX EXPLORER                            |
+------------------------------------------------------------------------------------+
|                                                                                    |
|  Select Year: [ 1978 v ]   Declare Hard Currency: [ $ 100.00 USD ]                 |
|                                                                                    |
|  +-------------------------------------+   +-------------------------------------+ |
|  | OFFICIAL STATE BANK CONVERSION      |   | STREET / "BROWN ECONOMY" EQUIVALENT | |
|  | (Tourist Burma Sule Pagoda Counter) |   | (Bogyoke Market / Tea Shop Broker)  | |
|  +-------------------------------------+   +-------------------------------------+ |
|  | Exchange Rate:  6.85 Kyats per $1   |   | Exchange Rate:  32.00 Kyats per $1  | |
|  | Total Received: 685.00 Kyats        |   | Total Received: 3,200.00 Kyats      | |
|  |                                     |   |                                     | |
|  | Purchasing Power:                   |   | Purchasing Power:                   | |
|  | * 1 night at Strand Hotel           |   | * 14 days of domestic travel       | |
|  | * 2 state railway meals             |   | * 4 handwoven silk Longyis          | |
|  | * 1 guided taxi tour of Rangoon     |   | * 20 lacquered Bagan bowls          | |
|  +-------------------------------------+   +-------------------------------------+ |
|                                                                                    |
|  CONTRABAND ARBITRAGE CALCULATOR:                                                  |
|  "The 555 & Johnnie Walker Standard"                                               |
|                                                                                    |
|  [ 1 Carton State Express 555 ] Purchased in Bangkok for $4.50 USD                  |
|  = Resale in Rangoon: 250 Kyats (Equivalent to ~36 days of average civil servant pay)|
+------------------------------------------------------------------------------------+
```

#### Educational Mechanics
* **Temporal Slider (1962–1988):** Updates historical inflation data, demonetization dates (e.g., the sudden 1985 and 1987 demonetizations of 25, 35, and 75 Kyat notes), and currency swings.
* **Historical Commentary Callouts:** Explains *why* tourists engaged in black-market swaps despite severe penalties, and how it sustained local service workers during goods shortages.

---

### 5.3 The "Big Four" Circuit Logistics Map

An interactive cartographic view charting the 7-day transit bottleneck.

```
+------------------------------------------------------------------------------------+
|  THE "BIG FOUR" CIRCUIT LOGISTICS & TIMELINE MAP                                   |
+------------------------------------------------------------------------------------+
|                                                                                    |
|        [ MANDALAY ] (Day 2-3)                                                      |
|           * Mahamuni Pagoda & Mandalay Hill                                        |
|           * Connection: 16-hr Sleeper Rail from Rangoon                            |
|             \                                                                      |
|              \ Irrawaddy River Steamer / Bus                                       |
|               \                                                                    |
|    [ PAGAN (BAGAN) ] (Day 4) ----------> [ INLE LAKE ] (Day 5-6)                   |
|       * 10,000 Ancient Stupas               * Leg-rowing Fishermen                 |
|       * Dust tracks & Horse Carts           * Phaung Daw Oo Pagoda                 |
|                                             /                                      |
|                                            / Burma Airways Corp (Fokker F27)       |
|                                           /                                        |
|        [ RANGOON (YANGON) ] <------------'                                         |
|           * Day 1: Entry & Sule Check-in                                           |
|           * Day 7: Final Currency Reconciliation & Deportation                     |
|                                                                                    |
|  [ PLAY 7-DAY TRANSIT REENACTMENT ]   Logistics Filter: [ All | Rail | Air | Bus ] |
+------------------------------------------------------------------------------------+
```

#### Map Details
* **Cartographic Style:** Vintage 1970s topographical survey map styling with sepia contour lines, period Burmese railway symbols, and airport markers.
* **Checkpoint Interactivity:** Clicking any node surfaces:
  * Approved Tourist Burma hotels (The Strand, Inle Lake Rest House, Thiripyitsaya Bagan).
  * State transportation hurdles (fuel rationing delays, locomotive breakdowns).
  * Archival photographs from that specific locale.

---

### 5.4 The Central Press Ephemera Carousel

A tactile display carousel showcasing ephemera printed by the state:
* **Hotel Luggage Tags:** The Strand Hotel, Inya Lake Hotel, Thamada Hotel.
* **Union of Burma Railways Boarding Passes:** First-class upper sleeper reservations.
* **Burma Airways Corporation (BAC) Flight Folders:** Vintage Fokker Friendship passenger envelopes.
* **Immigration Landing Cards:** Form TB-E-101 with bilingual Burmese/English admonitions.

---

## 6. Accessibility, Inclusivity & Archival Standards

### 6.1 Contrast & Color Accessibility (WCAG 2.1 AA/AAA)
* The primary text (`#1C1B1A`) on aged paper (`#F4EFE6`) achieves a contrast ratio of **13.8:1**, exceeding WCAG AAA requirements (7:1).
* Muted captions (`#544E45`) on paper achieve **5.2:1**, exceeding WCAG AA requirements (4.5:1).
* Stamp colors (`#8B1E1E`, `#5E3370`, `#1B4F72`) are paired only with light paper backgrounds to ensure minimum 4.5:1 legibility.

### 6.2 Display Preferences & "Clean Mode"
Historic paper textures and aged tinting, while evocative, may present reading fatigue for users with cognitive or visual impairments. The site includes a prominent **"Reading Mode Toggle"**:
* **Archival Experience (Default):** Warm parchment, faint grain texture, typewriter accents, and vintage stamps.
* **Modern Clean Mode:** Flat neutral background (`#FFFFFF`), high-contrast modern typography (`Inter`), and stripped decorative skew/stamps for effortless readability.

### 6.3 Archival Metadata Standards
All digital assets adhere to **Dublin Core** and **Schema.org** semantic conventions for academic utility:

```json
{
  "@context": "https://schema.org",
  "@type": "ArchiveComponent",
  "name": "Tourist Burma Official Travel Brochure (1982)",
  "identifier": "BSPP-TB-1982-LIT-04",
  "holdingArchive": "Burma Archives Department — Historical Documentation Unit",
  "dateCreated": "1982",
  "temporalCoverage": "1962/1988",
  "spatialCoverage": "Yangon, Myanmar",
  "publisher": {
    "@type": "Organization",
    "name": "Trade Corporation No. 20 (Hotels & Tourism)"
  },
  "inLanguage": ["en", "my"],
  "material": "Printed newsprint letterpress"
}
```

---

## 7. Technical Architecture & Performance Specifications

### 7.1 Recommended Architecture Stack
* **Framework:** **Astro** or **Next.js (Static Site Generation / SSG)**. Ideal for content-heavy, high-speed digital humanities archives with zero client-side hydration overhead for static text.
* **Styling:** **Tailwind CSS** configured with custom tokens for archival paper, ink, and typography.
* **Interactive Maps:** **MapLibre GL** or **Leaflet.js** with custom raster tile styles reflecting 1970s cartographic engraving.
* **Deep Zoom Imagery:** **OpenSeadragon** or **Panzoom** for IIIF (International Image Interoperability Framework) compatible archival scans.
* **Motion & Transitions:** **Framer Motion** or lightweight CSS scroll-driven animations with strict respect for `prefers-reduced-motion`.

### 7.2 Asset Optimization & Performance Targets
* **Image Formats:** All archival document scans provided in next-gen **AVIF** and **WebP** formats with responsive `srcset` resolutions.
* **Initial Page Weight:** Under **1.2 MB** for primary narrative routes.
* **Lighthouse Performance Score:** 95+ on Desktop and Mobile.
* **Offline Archival Capability:** Service Worker caching allowing researchers in low-connectivity regions (including local scholars in Myanmar) to browse transcripts offline.

---

## 8. Implementation Reference: CSS Tokens & Tailwind Configuration

To immediately bootstrap the design system, use the following configuration files:

### 8.1 CSS Custom Properties (`theme.css`)

```css
:root {
  /* Paper & Material Backgrounds */
  --color-paper-base: #F4EFE6;
  --color-paper-muted: #E8DFC8;
  --color-paper-border: #D6C8AC;
  --color-paper-dark: #2B2623;

  /* Inks & Typography */
  --color-ink-primary: #1C1B1A;
  --color-ink-secondary: #544E45;
  --color-ink-faded: #8C8477;

  /* State & Consular Accents */
  --color-seal-crimson: #8B1E1E;
  --color-seal-crimson-hover: #A82824;
  --color-stamp-violet: #5E3370;
  --color-stamp-cyan: #1B4F72;
  --color-state-olive: #2E3A2F;
  --color-pagoda-gold: #C59B27;
  --color-teak-deep: #3E2723;

  /* Typography Families */
  --font-display: "Playfair Display", Georgia, serif;
  --font-body: "Lora", "Merriweather", serif;
  --font-mono: "Courier Prime", "IBM Plex Mono", monospace;
  --font-burmese: "Pyidaungsu", "Noto Sans Myanmar", sans-serif;

  /* Elevation & Shadows */
  --shadow-paper-flat: 0 1px 3px rgba(0, 0, 0, 0.08), 0 1px 2px rgba(0, 0, 0, 0.04);
  --shadow-dossier: 0 4px 6px -1px rgba(62, 39, 35, 0.1), 0 2px 4px -1px rgba(62, 39, 35, 0.06);
  --shadow-lifted: 0 10px 15px -3px rgba(62, 39, 35, 0.15), 0 4px 6px -2px rgba(62, 39, 35, 0.08);
}

/* High-Contrast / Clean Modern Mode Override */
body[data-theme="clean"] {
  --color-paper-base: #FFFFFF;
  --color-paper-muted: #F8F9FA;
  --color-paper-border: #E5E7EB;
  --color-ink-primary: #111827;
  --color-ink-secondary: #4B5563;
  --font-display: system-ui, -apple-system, sans-serif;
  --font-body: system-ui, -apple-system, sans-serif;
  --font-mono: ui-monospace, monospace;
}
```

### 8.2 Tailwind CSS Configuration (`tailwind.config.js`)

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{astro,html,js,jsx,md,mdx,ts,tsx}"],
  theme: {
    extend: {
      colors: {
        paper: {
          base: "var(--color-paper-base)",
          muted: "var(--color-paper-muted)",
          border: "var(--color-paper-border)",
          dark: "var(--color-paper-dark)",
        },
        ink: {
          primary: "var(--color-ink-primary)",
          secondary: "var(--color-ink-secondary)",
          faded: "var(--color-ink-faded)",
        },
        seal: {
          crimson: "var(--color-seal-crimson)",
          hover: "var(--color-seal-crimson-hover)",
        },
        stamp: {
          violet: "var(--color-stamp-violet)",
          cyan: "var(--color-stamp-cyan)",
        },
        state: {
          olive: "var(--color-state-olive)",
          gold: "var(--color-pagoda-gold)",
          teak: "var(--color-teak-deep)",
        },
      },
      fontFamily: {
        display: ["var(--font-display)"],
        body: ["var(--font-body)"],
        mono: ["var(--font-mono)"],
        burmese: ["var(--font-burmese)"],
      },
      boxShadow: {
        dossier: "var(--shadow-dossier)",
        lifted: "var(--shadow-lifted)",
      },
    },
  },
  plugins: [],
};
```

---

## 9. Conclusion & Implementation Roadmap

| Phase | Milestone | Core Deliverables |
| :--- | :--- | :--- |
| **Phase 1** | *Digital Architecture & Layout Foundations* | Implement typography, paper palettes, responsive layout grid, and header dossier chrome. |
| **Phase 2** | *Primary Narrative: The 168-Hour Walkthrough* | Build the 6-chapter scroll experience and interactive temporal scrubber (Day 1 to Day 7). |
| **Phase 3** | *Interactive Features* | Implement Form C-102 Currency Calculator, the "Big Four" interactive transit map, and Strand Hotel photo comparison. |
| **Phase 4** | *Vault & Document Inspection* | Build high-res deep-zoom viewer, transcription sync, and Dublin Core archival search catalog. |
| **Phase 5** | *Accessibility, Bilingual Audit & Launch* | Screen reader optimization, Burmese script validation, WCAG 2.1 AA audit, and static hosting deployment. |

---
**Approved for Exhibition System Development**  
*Tourist Burma Heritage Project — Digital Humanities Working Group*
