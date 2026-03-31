# GitHub Profile Redesign — "The Constellation"

## Problem

The current profile (v3) is content-authentic but visually forgettable — clean markdown that looks like every other dark-mode engineer profile. Previous v2 was over-decorated (39 animations, floating orbs, glass cards) and felt "artificial and vibe coded." We need the sweet spot: visually distinctive, subtly communicates "I build complex systems," while staying true to Chintan's calm, evidence-driven voice.

## Design Direction

**Visual metaphor:** A constellation — interconnected nodes with subtle pulse, implying connected distributed systems under observation.

**What it communicates:** "This person thinks in systems" — without saying it. The different pulse rhythms suggest distributed components. A traveling signal dot suggests data flow. It's not a diagram — it's a mood.

## Hero SVG — "The Constellation"

### Layout (880 × 300px)

- **Left zone (~60%):** Name (`Chintan Goyal`, ~40px, white, clean sans-serif weight 600), subtitle (`Data & AI Infrastructure`, ~16px, muted gray). Below: 4 impact metrics as small spaced pills.
- **Right zone (~40%):** The constellation — 7-9 nodes scattered in an organic cluster. Nodes are small circles (6-10px radius), connected by thin lines (1px, low opacity). Each node subtly pulses at a different rhythm (2-5s SMIL cycles, staggered). No labels on nodes.

### Color Palette

- Background: `#0d1117` (GitHub's dark mode background — seamless blend)
- Nodes: cool teal-to-indigo gradient (`#38bdf8` → `#818cf8`)
- Connecting lines: faint white (`rgba(255,255,255,0.08)`)
- Metric pills: subtle teal borders
- Text: white (`#f0f0f0`) for name, muted (`#8b949e`) for subtitle

### Animations (SMIL, 5-6 total)

1. Each node pulses opacity (0.4 → 1.0 → 0.4) at its own rhythm — feels alive, like a monitoring dashboard
2. One "signal" dot travels along a connection line every ~8 seconds — subtle data-in-motion
3. Name text fades in on load (0 → 1 opacity over 1s)

### Constraints

- SMIL animations only (CSS @keyframes don't reliably work on GitHub)
- No `<script>`, `<foreignObject>`, or event handlers
- SVG loaded via `<img src="./hero.svg">` through GitHub's CDN
- Must look good at default width (~880px) and scale down gracefully

## README Body

### Structure

```
[Hero SVG]

Intro (2-3 sentences)

---

### What I've shipped
Career arc narrative (4 sentences: Infosys → Fractal → Morgan Stanley → Plume)
Impact badges: [~550 PB] [~15M customers] [p95 ~30s] [~$10M saved] [6 awards]

---

### Now building
- Project Lumos — metadata automation (with stars badge)
- FocusFlow — macOS focus timer (with stars badge)
- ai-agent-skills — AI assistant skill library (with stars badge)

---

### Systems I work with
Cloud: AWS · GCP · Databricks
Compute: Spark · Scala · Python · SQL
Storage: S3 · BigQuery · Snowflake · Delta · Iceberg
Orchestration: Airflow · Step Functions · Lambda
Observe: OpenTelemetry · Grafana · OpsGenie
Frontend: Next.js · TypeScript · Swift

---

Portability over lock-in · Performance with cost discipline · Trust before hype

---

[Say hi] [LinkedIn]
```

### Content Details

**Intro:**
> I design data platforms and ML infrastructure at scale — boring, reliable systems that earn their complexity. 9+ years across telecom, fintech, and analytics; most recently at ISP scale (~15M customers, ~100M devices).

**Career narrative ("What I've shipped"):**
> Started on a ~500 PB Hadoop cluster at Infosys, tuning Spark jobs until they ran ~70% faster. Built India's COVID data platform for the PM's Office (NASSCOM Corona Warrior, 2020). Designed trade-fail automation at Morgan Stanley that saved ~120 hours/week and ~$10M in cost avoidance. Now at Plume Design — multi-cloud data infra serving ~15M customers across a ~550 PB footprint.

**Impact badges (shields.io, indigo accent #6366f1):**
- ~550 PB data footprint
- ~15M customers
- p95 ~30s latency
- ~$10M cost avoidance
- 6 industry awards

**Featured projects:**
- Project Lumos — config-driven metadata automation, catalog-agnostic, 6+ source handlers
- FocusFlow — native macOS menu bar focus timer, on-device AI coaching, Swift
- ai-agent-skills — 34 reusable skills for AI coding assistants (Codex, Claude Code, Copilot)

**Tech stack:** Single flowing block grouped by domain. No table, no icons. Clean text with `·` separators.

**Principles:** One line, `·` separated. Acts as a signature.

**CTAs:** Two badges only — email and LinkedIn. No portfolio link (the profile IS the portfolio).

## Design Principles

1. **Every element earns its place** — no decoration for decoration's sake
2. **Constellation is the only "designed" element** — everything else is clean markdown
3. **Evidence over claims** — numbers and badges, not adjectives
4. **Breathing whitespace** — sections separated by `---`, no cramming
5. **Authentic voice** — calm, direct, rigorous. No marketing-speak.

## What We're NOT Doing

- No typing-svg animations
- No skillicons.dev grids
- No `<details>` collapsible sections
- No GitHub stats cards
- No contribution graphs
- No tables
- No emoji in headers
- No "Featured in" section (not verified)

## Files to Create/Modify

1. `hero.svg` — Complete rewrite with constellation design
2. `README.md` — Complete rewrite with new structure
3. Delete unused: `banner.png`, `banner_wide.png`, `profile_header.png`
