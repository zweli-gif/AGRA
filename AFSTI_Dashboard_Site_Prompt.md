# AFSTI Project Dashboard — Build Prompt
## A creative & technical brief for an AI coding tool (Cursor / v0 / Lovable / Bolt)

---

## 1. WHAT YOU ARE BUILDING

An **internal project dashboard** for the Africa Food Systems and Trade Initiative (AFSTI) — a $1.46M consultancy led by a Baobab Impact × Dalberg Kenya joint venture for AGRA (Alliance for a Green Revolution in Africa). The site is used by the ~8-person project team (consultants, analysts, project leads) to navigate, present, and pressure-test the analytical work product across corridors, value chains, investment cases, stakeholders, and political economy dynamics.

Think of it as a **McKinsey engagement "war room" in a browser** — not a marketing site, not a public portal.

---

## 2. THE PROJECT IN 60 SECONDS

**Problem:** Africa imports >$100B of food annually despite having 60% of the world's uncultivated arable land. Intra-African agricultural trade is blocked by political economy barriers, infrastructure gaps, policy unpredictability, and fragmented value chains.

**What AFSTI does:** Develops 9–12 bankable investment cases that link surplus production basins to deficit demand sinks across 4 priority trade corridors, with a 5–20 year horizon. The work covers deep value chain analytics, political economy assessment, stakeholder mapping, and a financing architecture to mobilise DFI and private capital.

**Four corridors:**
| Corridor | Key countries | Primary value chains |
|---|---|---|
| **Lobito & Upper Rift** | Tanzania, Zambia, Malawi, DRC, Angola | Maize, Soya, Poultry |
| **Limpopo–Southern Africa** | Zimbabwe, Mozambique, South Africa, Botswana | Wheat, Beef, Poultry, Feed |
| **Abidjan–Lagos** | Côte d'Ivoire, Nigeria, Ghana, Benin, Togo, Burkina Faso | Rice, Palm Oil |
| **Dakar–Lagos** | (Overlaps with Abidjan–Lagos in the west) | Rice, Maize |

**Six priority value chains:** Maize, Soya, Rice, Wheat, Poultry, Palm Oil

**Key deliverables by March 2026:**
- Baseline & Analytical Report (delivered Jan 30)
- 9–12 draft investment cases (target Mar 6)
- Validation workshop report (Mar 20)
- Final investment cases + high-level strategy/implementation plan (Mar 31)

---

## 3. DESIGN SYSTEM & AESTHETIC

### 3.1 Brand identity
This is **AGRA-adjacent** but not an AGRA product — it's an internal tool. Use:
- **Primary green:** `#1B5E20` (dark forest green) — headers, active states, positive signals
- **Secondary green:** `#2E7D32` / `#4CAF50` — accents, gradients
- **Amber/warning:** `#8B6914` — caution signals, political economy risks
- **Red/negative:** `#c0392b` — kill signals, structural constraints, bear cases
- **Background:** `#ffffff` with panels at `#f7f9f7`
- **Borders:** `#dde3dd`
- **Text:** `#1a1a1a` (primary), `#666666` (muted/secondary)

### 3.2 Design language — "McKinsey data room meets Bloomberg terminal"
The existing dashboards (see reference files) establish a clear pattern:
- **Dense, information-rich layouts** — no wasted space, no hero images
- **Pill-shaped tab navigation** — light gray border, green fill when active
- **Card-based content** — white cards with subtle shadow, 14px border-radius
- **RAG signal system** — Green/Amber/Red pills and signal bars throughout
- **Monospace for numbers** — all financial figures in monospace font
- **Compact typography** — body at 12–13px, labels at 10–11px, headers at 14–18px
- **System font stack** — `system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif`
- **Grid layouts** — `.g2` (2-col), `.g3` (3-col), `.g4` (4-col) with responsive collapse

### 3.3 Tone
Analytical, no-nonsense, hypothesis-driven. Every view should answer "so what?" Language is direct: "Bull case / Bear case", "Kill if…", "Binding constraint", "The honest assessment". No corporate fluff.

---

## 4. SITE ARCHITECTURE — 7 SECTIONS

### PAGE 1: HOME / COMMAND CENTER
**Purpose:** Single-screen project status overview — the first thing the team sees every morning.

**Content:**
- **Project timeline rail** — horizontal Gantt-style bar showing 4 phases (Diagnostic → Design → Implementation Planning → Acceleration) with "we are here" marker at current date
- **Deliverable tracker** — table with deliverable name, contractual due date, status (On Track / At Risk / Overdue / Complete), and completion %
- **Corridor × Value Chain matrix** — a 4×6 grid (corridors as rows, value chains as columns) with RAG status in each cell indicating analytical readiness. Clicking a cell navigates to the relevant value chain deep-dive
- **Key numbers strip** — 4–6 KPI cards: interviews completed (~25+), investment cases drafted (count), total corridor investment opportunity ($XXM), stakeholders engaged (74+)
- **Recent activity feed** — last 5–10 actions (e.g., "Field visit: Zambia complete", "Nigeria rice model updated", "SteerCo call #4 done")

### PAGE 2: CORRIDOR MAP (Interactive)
**Purpose:** Geographic visualization of the 4 corridors, production basins, demand sinks, and trade flows.

**Content:**
- **Map of Africa** (use a simplified SVG or Mapbox/Leaflet) showing:
  - 8 production basins highlighted (Senegal River, Niger/Volta, Nile River Delta, Nile/Gibe River, Lake Malawi/Lake Tanganyika, Lobito, Limpopo River, S. Mediterranean Coast)
  - 4 corridors as colored route lines connecting basins to demand sinks
  - Clickable country nodes with popup cards showing: RAG readiness (from PEA), key value chains, political economy summary (1-liner)
- **Corridor selector** — toggle between corridors or show all
- **Corridor summary cards** (below map) — one per corridor with:
  - Countries involved
  - Value chains in play
  - PEA readiness rating (from Sofala Partners assessment)
  - Total investment opportunity range
  - Key chokepoints (1–2 bullets)

**PEA readiness data (from Sofala Partners report):**
| Country | Production Capacity | Trade Posture | PE Incentives | Overall AFSTI Readiness |
|---|---|---|---|---|
| Tanzania | Amber–Green | Amber | Amber–Green | Amber–Green |
| Zambia | Amber–Green | Amber | Amber–Green | Amber–Green |
| Malawi | Amber–Green | Amber–Red | Amber | Amber |
| Nigeria | Amber–Green | Amber–Red | Amber–Red | Amber |
| Zimbabwe | Amber | Amber–Red | Amber | Amber |
| Côte d'Ivoire | Amber–Green | Amber | Amber–Green | Amber–Green |
| Ghana | Amber–Green | Amber | Amber | Amber |
| Burkina Faso | Amber–Red | Red | Red | Amber–Red |
| DRC | (Demand sink) | — | — | — |
| Angola | (Demand sink) | — | — | — |
| Mozambique | Amber | Amber | Amber | Amber |
| South Africa | Green | Green | Green–Amber | Green–Amber |

### PAGE 3: VALUE CHAIN DEEP DIVES
**Purpose:** The analytical heart of the site. Each value chain gets a tabbed single-page dashboard identical in structure to the attached HTML reference files.

**CRITICAL: You already have 4 complete reference HTML files. Replicate their exact structure and CSS patterns as pages within this app:**
- `vc_soya_zambia_short.html` — Zambia Soya (Lobito–Upper Rift)
- `vc_maize_tanzania_short.html` — Tanzania Maize (Lobito–Upper Rift)
- `vc_rice_nigeria_short.html` — Nigeria Rice (Abidjan–Lagos)
- `vc_wheat_zimbabwe_short.html` — Zimbabwe Wheat (Limpopo)

**Each value chain dashboard has 6 tabs:**
1. **Thesis** — Governing thought, signal bars (✓/✗/⚠), bull/bear case, 4 KPI cards
2. **Cost physics** — Price decomposition, cost waterfall, co-product economics
3. **Demand fit** — Target markets, import volumes, demand drivers, buyer profiles
4. **Ecosystem map** — Value chain node diagram (production → aggregation → processing → logistics → market), with binding constraints flagged
5. **Five projects** — Sequenced investment projects with size, type, timeline, dependencies
6. **Players & tests** — Named operators (not stakeholders), site-visit questions, kill criteria

**Additional value chains to stub out (content TBD — show placeholder cards):**
- Poultry (Limpopo) — Malawi/Zambia → Mozambique, South Africa
- Palm Oil (Abidjan–Lagos) — Côte d'Ivoire → regional
- Beef/Livestock (Limpopo) — Zimbabwe, Mozambique, South Africa

**Navigation:** A value chain selector (dropdown or sidebar) lets users switch between chains. Each chain shows its corridor tag.

### PAGE 4: INVESTMENT CASES
**Purpose:** Portfolio view of all 9–12 investment cases being developed.

**Content:**
- **Portfolio summary table:**
  | # | Investment Case | Corridor | Value Chain | Investment Size | Type | Status | Confidence |
  |---|---|---|---|---|---|---|---|
  | 1 | Aggregation platform + WRS (Tanzania) | Lobito–Upper Rift | Maize | $15–25M | Private + DFI | Draft | Medium |
  | 2 | Aggregation hubs (Zambia) | Lobito–Upper Rift | Soya | $15–25M | Private + DFI | Draft | High |
  | 3 | Crusher debottleneck (Zambia) | Lobito–Upper Rift | Soya | $10–20M | Private | Draft | High |
  | 4 | Meal anchor offtake (Malawi/DRC) | Lobito–Upper Rift | Soya | $5–10M | Private | Draft | Medium |
  | 5 | Trade finance facility | Cross-corridor | Multi | $25–30M | DFI + banks | Draft | Medium |
  | 6 | Irrigated rice clusters (Nigeria) | Abidjan–Lagos | Rice | TBD | Blended | Draft | Medium |
  | 7 | Milling hub scale-up (Nigeria) | Abidjan–Lagos | Rice | TBD | Private/DFI | Draft | Medium |
  | 8 | Irrigation expansion (Zimbabwe) | Limpopo | Wheat | TBD | Public | Scoping | Low |
  | 9 | Feed + poultry integration | Limpopo | Poultry | TBD | Private/DFI | Scoping | Low |

- **Filters:** By corridor, value chain, status, confidence level
- **Click-through:** Each row expands or links to the investment case template (8-section structure):
  1. Investment Overview
  2. Market Opportunity
  3. Competitive Advantage
  4. Investment Highlights (source/use of funds, returns)
  5. Operational Considerations
  6. Enabling Environment
  7. Impact
  8. Risks & Mitigation

- **Cross-linkages panel:** Show which investment cases are interdependent (e.g., "Zambia soya meal → feeds Limpopo poultry case"; "Tanzania maize → also feeds poultry")

### PAGE 5: STAKEHOLDER ENGAGEMENT TRACKER
**Purpose:** CRM-lite tracker for 74+ stakeholders across the engagement pipeline.

**Content:**
- **Pipeline funnel visualization:**
  - Stage 0: Contact Missing
  - Stage 1: Invitation Pending
  - Stage 2: Outreach Email Sent
  - Stage 3: Email Responded (Scheduling)
  - Stage 4: Scheduled
  - Stage 5: Interview Complete
  - Stage 6: Follow-up / Field Visit

- **Stakeholder table** (filterable, sortable):
  | Name | Organization | Type | Corridor | Value Chain | Stage | Last Contact | Priority |
  
  **Stakeholder types:** Government, DFI/Donor, Private Sector, Regional Body, Think Tank/Research, Continental Organization

- **Engagement by corridor chart** — stacked bar showing interview counts per corridor
- **Upcoming engagements** — next 2 weeks of scheduled interviews/visits

- **Field visit schedule cards:**
  - Zambia: Feb 17–21 (ETG, Alliance Ginneries, Mount Meru, Ministry of Agriculture, Zambia National Farmers Union)
  - Tanzania: Feb 17–21 (NMB, AGCOT, ALAF Poultry, AMDT, Ministry of Agriculture)
  - Zimbabwe: Feb 23–26 (Ministry of Lands, ARDA, Bakhresa/Blue Ribbon, Innscor, National Food Holdings)
  - Nigeria: Feb 23–Mar 2 (Thrive Agri, AFEX, Lagos Rice Mill, Rice Mills of Nigeria, Olam Agri, RIFAN)

### PAGE 6: POLITICAL ECONOMY INSIGHTS
**Purpose:** Synthesize the Sofala Partners PEA findings into a navigable, decision-useful format.

**Content:**
- **12 country cards** — each showing:
  - Flag + country name
  - RAG readiness scores (4 dimensions: political context, economic/fiscal, food system, trade posture)
  - 1-paragraph AFSTI readiness summary
  - Key risks (1–2 bullets)
  - Recommended engagement approach (1–2 bullets)

- **Cross-cutting insights panel:**
  - "Staple crops = electoral insurance across all countries"
  - "Export bans are politically rational, not economically rational"
  - "Corridor chokepoints are rent extraction systems, not just infrastructure gaps"
  - "Sovereignty-first politics trumps regional integration in every country"
  - "Less politicized commodities (wheat, soya, beans) are safer bets than sensitive staples (maize, rice)"

- **Corridor synthesis view** — toggle between 4 corridor summaries with comparative tables (replicating the Sofala Partners corridor assessment format)

### PAGE 7: 2050 PROJECTIONS & SCENARIOS
**Purpose:** Forward-looking analysis showing how demand, supply, climate, and geopolitics reshape the opportunity.

**Content:**
- **Demand vs Supply projections by value chain** — bar/line charts showing:
  - SSA demand growth multiplier by 2050 (Maize: 1.8×, Soya: 2–3×, Rice: 2×+, Wheat: 2×+, Poultry: 4×, Palm Oil: 3×)
  - SSA supply growth multiplier (Maize: 1.6×, Soya: lagging, Rice: depends on yield, Wheat: structurally constrained)
  - Resulting gap = investment opportunity

- **Climate impact overlay** — which corridors/countries face yield headwinds vs tailwinds

- **Geopolitical scenario cards** (4 scenarios):
  1. Trade fragmentation (tariffs, export bans, quotas)
  2. Fertilizer supply insecurity
  3. Shipping & freight disruptions
  4. Energy market instability
  Each card: description, probability assessment, implications for corridor investments

- **"Implications for investment cases" matrix** — which scenarios strengthen/weaken which investment cases

---

## 5. TECHNICAL REQUIREMENTS

### 5.1 Stack recommendation
- **Framework:** Next.js 14+ (App Router) or Remix — server components for data, client for interactivity
- **Styling:** Tailwind CSS with the custom color tokens defined above, OR vanilla CSS matching the reference files' variable system
- **Charts:** Recharts or Chart.js for data viz, or D3 for the corridor map
- **Map:** Leaflet with OpenStreetMap tiles, or a custom SVG map of Africa
- **Data:** Static JSON files for now (no backend needed — this is internal). Structure data as:
  ```
  /data/corridors.json
  /data/value-chains/[slug].json
  /data/investment-cases.json
  /data/stakeholders.json
  /data/pea-countries.json
  /data/projections-2050.json
  ```
- **Deployment:** Vercel (team already uses it)

### 5.2 Responsive behavior
- **Primary use:** Desktop (1280px+) — this is a work tool, not a mobile app
- **Tablet:** Collapse grids from 4-col → 2-col, tables scroll horizontally
- **Mobile:** Functional but not optimized — single column, stacked cards

### 5.3 Navigation
- **Persistent left sidebar** (collapsible) with 7 section icons + labels
- **Breadcrumb trail** at top: Home > Corridors > Lobito–Upper Rift > Soya > Cost Physics
- **Global search** — search across value chains, stakeholders, investment cases
- **Corridor color coding** — each corridor has a subtle color accent that carries through all related pages

### 5.4 Interactivity priorities
1. Corridor × VC matrix cells are clickable → navigate to deep dive
2. Value chain tabs switch content without page reload (client-side)
3. Stakeholder table is filterable and sortable
4. Investment case rows expand inline or link to detail page
5. Map is pannable/zoomable with clickable country nodes
6. 2050 charts have hover tooltips with data values

---

## 6. REFERENCE FILES (attached)

These 4 HTML files are your **design bible**. They show the exact CSS patterns, component vocabulary, and information density expected:

1. **`vc_soya_zambia_short.html`** — The gold standard. Strongest analytical case. 6 tabs, full data.
2. **`vc_maize_tanzania_short.html`** — Same structure, different data. Shows how the template adapts.
3. **`vc_rice_nigeria_short.html`** — Import substitution framing (not export). Different thesis structure.
4. **`vc_wheat_zimbabwe_short.html`** — Limpopo corridor. Shows cross-corridor dependencies.

**What to extract from these files:**
- The complete CSS design system (copy the `:root` variables and class library verbatim)
- The component patterns: `.c` (card), `.k` (KPI box), `.sig` (signal bar), `.t` (table), `.bar` (horizontal bar chart), `.p` (pill/badge), `.kill` (abandon criteria), `.nd` (node), `.fl` (flag)
- The tab navigation pattern (`.tb` pills + `.sec` sections)
- The RAG color system (green/amber/red across all components)
- The typography scale and spacing rhythm

---

## 7. DATA TO POPULATE

Populate with real data where provided in this brief and in the reference files. For sections where data is marked "TBD", use realistic placeholder content that matches the analytical style (not lorem ipsum — use plausible agricultural trade data).

**Key real data points available:**
- Zambia soya: 475kt production, 1M MT crush capacity, 48% utilisation, $58–90M total investment
- Tanzania maize: 7.0 Mt production on 4.2M ha, <2% exported, target markets DRC/Kenya/Malawi
- Nigeria rice: $800M+/yr import bill, <20% probability of becoming net exporter
- Zimbabwe wheat: Cross-border to Mozambique, Zambia, Botswana, SA
- Poultry (Limpopo): Southern Africa demand projected 5M tons by 2050
- Palm oil: SSA demand 3× by 2050, but SE Asia consolidating dominance → weak investment case

---

## 8. WHAT "DONE" LOOKS LIKE

- [ ] All 7 pages navigable with sidebar + breadcrumbs
- [ ] 4 value chain dashboards rendered with real data from reference HTML files
- [ ] 3 additional value chain stubs with placeholder content
- [ ] Corridor map with clickable countries and RAG overlays
- [ ] Investment case portfolio table with expand/filter
- [ ] Stakeholder pipeline funnel + filterable table
- [ ] PEA country cards with RAG scoring
- [ ] 2050 demand/supply charts for 6 value chains
- [ ] Consistent design language matching reference files exactly
- [ ] Deployed to Vercel and shareable via URL

---

## 9. NON-GOALS (for now)

- No authentication / login (internal tool, shared via URL)
- No backend / database (static JSON is fine)
- No real-time data feeds
- No CMS / content editing capability
- No public-facing marketing content
- No mobile-first design (desktop-first is fine)

---

*Brief prepared by the AFSTI project team — Baobab Impact × Dalberg Kenya for AGRA*
*February 2026*
