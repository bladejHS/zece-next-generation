# ZECE NEXT GENERATION — DESIGN SYSTEM MASTER
## Tactical Performance Platform | SRI Counter-Terrorism Brigade

### 1. IDENTITATE ȘI TON VIZUAL
- **Concept:** "Operational Readiness Dashboard". Estetică derivată din sistemele HUD tactice, echipamente militare reale și discipline operaționale.
- **Ton:** Serios, disciplinat, funcțional, premium. Fără gamificare, fără neon, fără elemente decorative inutile.
- **Public:** Operator SRI / Brigada Antitero. Aplicația este un instrument de lucru, nu un joc.
- **Limbă:** Română cu diacritice corecte. Terminologie precisă (fără traduceri forțate).

### 2. PALETĂ DE CULORI (TACTICAL DARK)
Culorile sunt desaturate, funcționale și optimizate pentru vizibilitate în condiții de lumină scăzută.

| Token                | Hex       | Utilizare                                      |
|----------------------|-----------|------------------------------------------------|
| --bg-base            | #0B0E14   | Fundal principal (aproape negru, nuanță rece)  |
| --bg-surface         | #151A23   | Carduri, panouri, secțiuni                     |
| --bg-elevated        | #1F2633   | Hover states, dropdowns, modale                |
| --border-subtle      | #2A3240   | Separatoare fine, grid-uri                     |
| --border-strong      | #3D4859   | Contururi active, focus rings                  |
| --text-primary       | #E8ECF4   | Text principal, titluri                        |
| --text-secondary     | #94A3B8   | Descrieri, metadate, labels                    |
| --text-muted         | #64748B   | Placeholder, text dezactivat                   |
| --accent-primary     | #C9A227   | Auriu tactic (insigne, rank, acțiuni critice)  |
| --accent-on-primary  | #0B0E14   | Text pe accent auriu                           |
| --status-success     | #4ADE80   | Obiective atinse, sincronizare reușită         |
| --status-warning     | #FBBF24   | Atenție, recuperare necesară                   |
| --status-danger      | #F87171   | Eroare, accidentare, date lipsă                |
| --status-info        | #60A5FA   | Informații neutre, link-uri                    |

**Reguli:**
- Contrast minim text: 4.5:1 (WCAG AA).
- Nu folosi alb pur (#FFFFFF) nicăieri; folosește #E8ECF4.
- Accentul auriu se folosește DOAR pentru acțiuni primare și indicatori de rang/importanță.
- Culorile de status au întotdeauna icon + text, niciodată doar culoare.

### 3. TIPOGRAFIE
Fonturile trebuie să fie tehnice, lizibile și să evoce documentația militară / HUD.

| Rol              | Font             | Greutate | Tracking  | Note                          |
|------------------|------------------|----------|-----------|-------------------------------|
| Display / Hero   | Oswald           | 600–700  | -0.02em   | Titluri mari, condensat       |
| Headings         | Inter            | 600      | -0.01em   | Secțiuni, carduri             |
| Body             | Inter            | 400      | 0         | Text cursiv, descrieri        |
| Data / Mono      | JetBrains Mono   | 400–500  | 0         | Timer, greutăți, repetări, cod|
| Labels / Caps    | Inter            | 600      | 0.05em    | UPPERCASE, mici, tracking larg|

**Scală tipografică (mobile-first):**
- xs: 12px / 16px line-height
- sm: 14px / 20px
- base: 16px / 24px
- lg: 18px / 28px
- xl: 24px / 32px
- 2xl: 32px / 40px
- 3xl: 40px / 48px

### 4. SPAȚIERE ȘI LAYOUT
Grid bazat pe multipli de 4px. Densitate medie spre compactă (dashboard operațional).

| Token          | Valoare | Utilizare                    |
|----------------|---------|------------------------------|
| --space-xs     | 4px     | Padding inline fin           |
| --space-sm     | 8px     | Gap între elemente grupate   |
| --space-md     | 16px    | Padding card, gap secțiuni   |
| --space-lg     | 24px    | Spațiu vertical între blocuri|
| --space-xl     | 32px    | Separare majoră              |
| --space-2xl    | 48px    | Hero / footer spacing        |

**Container:** max-width 1200px, centrat. Pe mobil: padding 16px lateral.
**Carduri:** border-radius 4px (colțuri ușor rotunjite, nu bulboase). Border 1px solid var(--border-subtle).

### 5. COMPONENTE UI CHEIE

#### Butoane
- **Primary:** bg var(--accent-primary), text var(--accent-on-primary), uppercase, tracking-wide, font-weight 600. Hover: brightness(1.1). Active: brightness(0.95).
- **Secondary:** transparent, border 1px var(--border-strong), text var(--text-primary). Hover: bg var(--bg-elevated).
- **Ghost:** transparent, text var(--text-secondary). Hover: text var(--text-primary), bg var(--bg-surface).
- **Danger:** bg transparent, border 1px var(--status-danger), text var(--status-danger).
- Toate butoanele: min-height 44px, padding 0 24px, border-radius 4px, cursor-pointer, transition 150ms ease.

#### Carduri
- Background: var(--bg-surface)
- Border: 1px solid var(--border-subtle)
- Padding: var(--space-md)
- Header: font Inter 600, uppercase, tracking-wide, color var(--text-secondary), margin-bottom var(--space-sm)
- Conținut: text var(--text-primary)

#### Input-uri & Formulare
- Background: var(--bg-base)
- Border: 1px solid var(--border-subtle)
- Focus: border-color var(--accent-primary), outline none, box-shadow 0 0 0 2px rgba(201,162,39,0.2)
- Label: var(--text-secondary), font-size sm, uppercase, tracking-wide, margin-bottom 4px
- Error: border-color var(--status-danger), mesaj sub input în var(--status-danger)

#### Navigație (Bottom Bar Mobil)
- Background: var(--bg-surface) cu border-top 1px var(--border-subtle)
- 5 iteme max: Dashboard, Antrenament, Alergare, Nutriție, Profil
- Icon + label. Activ: color var(--accent-primary). Inactiv: var(--text-muted).
- Safe-area-inset-bottom respectat.

### 6. EFECTE ȘI ANIMAȚII
- **Tranziții:** 150ms ease-in-out pentru hover/focus. 250ms pentru page transitions.
- **Loading:** Skeleton screens cu shimmer subtil (gradient linear pe var(--bg-elevated)).
- **No glow, no neon.** Fără text-shadow colorat, fără box-shadow difuz colorat.
- **Reduced motion:** Respectă prefers-reduced-motion. Dezactivează toate animațiile non-esențiale.

### 7. ACCESIBILITATE
- Contrast text: ≥4.5:1 normal, ≥3:1 large text.
- Touch targets: ≥44x44px.
- Focus visible: ring 2px var(--accent-primary) sau var(--border-strong).
- Aria-labels pe toate controalele icon-only.
- Heading hierarchy: h1→h6 fără skip.
- Color not sole indicator: status = icon + text + color.

### 8. IMAGINI ȘI ASSETS
- Logo: SVG, monocrom sau auriu pe fundal închis. Simbol geometric abstract (scut, cruce tactică stilizată, litera Z angulară).
- Favicon: 32x32, 192x192, 512x512 PNG + SVG.
- Imagini hero: fotografie originală operator (generată AI, non-oficială), ton cinematic, echipament tactic realist, fără însemne oficiale SRI.
- Toate imaginile: WebP/AVIF, lazy-load, width/height explicite.

### 9. ANTI-PATTERNS (NU FACE)
- ❌ Neon, glow, cyberpunk, glitch effects
- ❌ Gamificare (badges, streaks, levels, XP)
- ❌ Emoji ca iconuri
- ❌ Gradient-uri vibrante
- ❌ Colțuri foarte rotunjite (>8px)
- ❌ Fonturi decorative / script / handwritten
- ❌ Alb pur (#FFFFFF)
- ❌ Portocaliu / verde lime / violet ca culori primare
- ❌ RIR menționat oriunde
- ❌ Date fictive prezentate ca reale