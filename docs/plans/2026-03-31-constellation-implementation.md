# Constellation Profile — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Replace the current basic GitHub profile with a constellation-themed design that subtly communicates "I build complex systems" through an animated network graph and evidence-packed content.

**Architecture:** Custom SVG hero (880×300) with SMIL-animated constellation (8 nodes, connecting lines, traveling signal dots) on the right, identity + metrics on the left. Clean markdown README below with career narrative, featured projects, tech stack, and principles.

**Tech Stack:** SVG + SMIL animations, GitHub-flavored Markdown, shields.io badges

---

### Task 1: Create hero.svg — The Constellation

**Files:**
- Create: `hero.svg` (overwrite existing)

**Step 1: Write the complete hero SVG**

Replace `hero.svg` with the following complete content:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 300" width="880" height="300">
  <defs>
    <linearGradient id="nodeGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#38bdf8"/>
      <stop offset="100%" stop-color="#818cf8"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="2.5" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <!-- Background -->
  <rect width="880" height="300" fill="#0d1117"/>

  <!-- === LEFT ZONE: Identity === -->

  <!-- Name -->
  <text x="48" y="95" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif" font-size="40" font-weight="600" fill="#f0f0f0" opacity="0">
    Chintan Goyal
    <animate attributeName="opacity" from="0" to="1" dur="0.8s" fill="freeze"/>
  </text>

  <!-- Subtitle -->
  <text x="50" y="125" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif" font-size="16" fill="#8b949e" opacity="0">
    Data &amp; AI Infrastructure
    <animate attributeName="opacity" from="0" to="1" dur="0.8s" begin="0.2s" fill="freeze"/>
  </text>

  <!-- Metric pills -->
  <g opacity="0">
    <animate attributeName="opacity" from="0" to="1" dur="0.6s" begin="0.5s" fill="freeze"/>

    <!-- ~550 PB -->
    <rect x="48" y="155" width="78" height="26" rx="13" fill="rgba(56,189,248,0.08)" stroke="rgba(56,189,248,0.25)" stroke-width="1"/>
    <text x="87" y="172" text-anchor="middle" font-family="system-ui, -apple-system, sans-serif" font-size="11" fill="#8b949e">~550 PB</text>

    <!-- ~15M users -->
    <rect x="136" y="155" width="92" height="26" rx="13" fill="rgba(56,189,248,0.08)" stroke="rgba(56,189,248,0.25)" stroke-width="1"/>
    <text x="182" y="172" text-anchor="middle" font-family="system-ui, -apple-system, sans-serif" font-size="11" fill="#8b949e">~15M users</text>

    <!-- p95 ~30s -->
    <rect x="238" y="155" width="82" height="26" rx="13" fill="rgba(56,189,248,0.08)" stroke="rgba(56,189,248,0.25)" stroke-width="1"/>
    <text x="279" y="172" text-anchor="middle" font-family="system-ui, -apple-system, sans-serif" font-size="11" fill="#8b949e">p95 ~30s</text>

    <!-- ~$10M saved -->
    <rect x="330" y="155" width="98" height="26" rx="13" fill="rgba(56,189,248,0.08)" stroke="rgba(56,189,248,0.25)" stroke-width="1"/>
    <text x="379" y="172" text-anchor="middle" font-family="system-ui, -apple-system, sans-serif" font-size="11" fill="#8b949e">~$10M saved</text>
  </g>

  <!-- Brief descriptor -->
  <text x="50" y="215" font-family="system-ui, -apple-system, sans-serif" font-size="12" fill="#484f58" opacity="0">
    multi-cloud · telecom · fintech · analytics
    <animate attributeName="opacity" from="0" to="0.8" dur="0.6s" begin="0.7s" fill="freeze"/>
  </text>

  <!-- === RIGHT ZONE: Constellation === -->

  <!-- Connection lines -->
  <g stroke="rgba(255,255,255,0.06)" stroke-width="1" fill="none">
    <line x1="590" y1="65" x2="700" y2="40"/>
    <line x1="590" y1="65" x2="640" y2="145"/>
    <line x1="700" y1="40" x2="800" y2="70"/>
    <line x1="700" y1="40" x2="750" y2="130"/>
    <line x1="800" y1="70" x2="750" y2="130"/>
    <line x1="800" y1="70" x2="830" y2="170"/>
    <line x1="640" y1="145" x2="750" y2="130"/>
    <line x1="640" y1="145" x2="570" y2="230"/>
    <line x1="640" y1="145" x2="690" y2="220"/>
    <line x1="750" y1="130" x2="830" y2="170"/>
    <line x1="750" y1="130" x2="690" y2="220"/>
    <line x1="570" y1="230" x2="690" y2="220"/>
    <line x1="690" y1="220" x2="790" y2="255"/>
    <line x1="830" y1="170" x2="790" y2="255"/>
  </g>

  <!-- Nodes with independent pulse rhythms -->
  <g filter="url(#glow)">
    <circle cx="590" cy="65" r="7" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.4;0.9;0.4" dur="3s" repeatCount="indefinite"/>
    </circle>
    <circle cx="700" cy="40" r="5" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.4;0.85;0.4" dur="4s" repeatCount="indefinite"/>
    </circle>
    <circle cx="800" cy="70" r="8" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.35;0.95;0.35" dur="2.5s" repeatCount="indefinite"/>
    </circle>
    <circle cx="640" cy="145" r="9" fill="url(#nodeGrad)" opacity="0.6">
      <animate attributeName="opacity" values="0.5;1;0.5" dur="3.5s" repeatCount="indefinite"/>
    </circle>
    <circle cx="750" cy="130" r="6" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.4;0.9;0.4" dur="2.8s" repeatCount="indefinite"/>
    </circle>
    <circle cx="830" cy="170" r="7" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.35;0.85;0.35" dur="4.2s" repeatCount="indefinite"/>
    </circle>
    <circle cx="570" cy="230" r="5" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.4;0.8;0.4" dur="3.2s" repeatCount="indefinite"/>
    </circle>
    <circle cx="690" cy="220" r="7" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.45;0.9;0.45" dur="2.6s" repeatCount="indefinite"/>
    </circle>
    <circle cx="790" cy="255" r="4" fill="url(#nodeGrad)" opacity="0.5">
      <animate attributeName="opacity" values="0.4;0.8;0.4" dur="3.8s" repeatCount="indefinite"/>
    </circle>
  </g>

  <!-- Signal dot A: flows through the main path -->
  <circle r="2.5" fill="#38bdf8" opacity="0">
    <animateMotion dur="8s" repeatCount="indefinite"
      path="M590,65 L640,145 L750,130 L830,170 L790,255"/>
    <animate attributeName="opacity" values="0;0.9;0.9;0.9;0" dur="8s" repeatCount="indefinite"/>
  </circle>

  <!-- Signal dot B: secondary path, offset start -->
  <circle r="2" fill="#818cf8" opacity="0">
    <animateMotion dur="10s" repeatCount="indefinite" begin="3s"
      path="M700,40 L590,65 L640,145 L570,230 L690,220"/>
    <animate attributeName="opacity" values="0;0.7;0.7;0.7;0" dur="10s" repeatCount="indefinite" begin="3s"/>
  </circle>
</svg>
```

**Step 2: Preview the SVG locally**

Run: `open hero.svg` (macOS) to verify the constellation renders correctly.

Check:
- Name and subtitle are readable on the left
- Constellation nodes are visible on the right
- Pulse animations are running (each node at different rhythm)
- Signal dots travel along their paths
- Metric pills are visible below the subtitle
- Overall mood: calm, alive, systems-like

**Step 3: Commit hero.svg**

```bash
git add hero.svg
git commit -m "feat: constellation hero SVG with pulsing network graph

8 interconnected nodes with independent SMIL pulse rhythms,
2 traveling signal dots, fade-in text and metric pills.

Co-authored-by: Copilot <223556219+Copilot@users.noreply.github.com>"
```

---

### Task 2: Create README.md

**Files:**
- Modify: `README.md` (overwrite existing)

**Step 1: Write the complete README**

Replace `README.md` with:

```markdown
<img src="./hero.svg" width="100%" alt="Chintan Goyal — Data & AI Infrastructure"/>

I design data platforms and ML infrastructure at scale — boring, reliable systems that earn their complexity. 9+ years across telecom, fintech, and analytics; most recently at ISP scale (~15M customers, ~100M devices).

---

### What I've shipped

Started on a ~500 PB Hadoop cluster at Infosys, tuning Spark jobs until they ran ~70% faster. Built India's COVID data platform for the Prime Minister's Office (NASSCOM Corona Warrior, 2020). Designed trade-fail automation at Morgan Stanley that saved ~120 hours/week and ~$10M in cost avoidance. Now at Plume Design — multi-cloud data infra serving ~15M customers across a ~550 PB footprint.

![Data Scale](https://img.shields.io/badge/data_footprint-~550_PB-38bdf8?style=flat-square)
![Customers](https://img.shields.io/badge/customers-~15M-38bdf8?style=flat-square)
![Latency](https://img.shields.io/badge/p95_latency-~30s-38bdf8?style=flat-square)
![Cost Savings](https://img.shields.io/badge/cost_avoidance-~$10M-38bdf8?style=flat-square)
![Awards](https://img.shields.io/badge/awards-6-38bdf8?style=flat-square)

---

### Now building

**[Project Lumos](https://github.com/goyal-chintan/project-lumos)** — open-source metadata automation. Config-driven, catalog-agnostic framework with 6+ source handlers. Automates metadata hygiene without manual effort.

**[FocusFlow](https://github.com/goyal-chintan/focus-flow)** — native macOS menu bar focus timer with on-device AI coaching, session analytics, and distraction blocking. Built in Swift.

**[ai-agent-skills](https://github.com/goyal-chintan/ai-agent-skills)** — curated library of 34 reusable skills for AI coding assistants across planning, debugging, development, and review workflows.

---

### Systems I work with

**Cloud** — AWS · GCP · Databricks
**Compute** — Spark · Scala · Python · SQL
**Storage** — S3 · BigQuery · Snowflake · Delta · Iceberg
**Orchestration** — Airflow · Step Functions · Lambda
**Observe** — OpenTelemetry · Grafana · OpsGenie
**Frontend** — Next.js · TypeScript · Swift

---

Portability over lock-in · Performance with cost discipline · Trust before hype

---

[![Say hi](https://img.shields.io/badge/say_hi-mail.chintan.goyal@gmail.com-8b949e?style=flat-square)](mailto:mail.chintan.goyal@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-chintan--goyal-8b949e?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/chintan-goyal/)
```

**Step 2: Preview README locally**

Run: `cd /Users/chintan/Personal/repos/goyal-chintan && grip README.md` (if grip installed) or open in VS Code preview.

Check:
- Hero SVG renders at full width
- Intro paragraph reads naturally
- Career narrative is 4 sentences, evidence-packed
- Impact badges render with teal color
- Three projects are clearly described
- Tech stack is scannable
- Principles line acts as a signature
- CTA badges render at bottom

**Step 3: Commit README.md**

```bash
git add README.md
git commit -m "feat: constellation profile README with career narrative and impact badges

Evidence-driven content: career arc, ~550 PB / ~15M customers / ~$10M
metrics, 3 featured projects, clean tech stack, principles signature.

Co-authored-by: Copilot <223556219+Copilot@users.noreply.github.com>"
```

---

### Task 3: Clean up unused assets

**Files:**
- Delete: `banner.png`
- Delete: `banner_wide.png`
- Delete: `profile_header.png`

**Step 1: Remove old files**

```bash
git rm banner.png banner_wide.png profile_header.png
```

**Step 2: Commit cleanup**

```bash
git commit -m "chore: remove unused legacy banner assets (~550 KB)

Co-authored-by: Copilot <223556219+Copilot@users.noreply.github.com>"
```

---

### Task 4: Push and verify on GitHub

**Step 1: Push to origin**

```bash
git push origin publish-profile:main
```

**Step 2: Verify on GitHub**

Open `https://github.com/goyal-chintan` in browser and verify:
- Hero constellation renders with animated nodes
- Signal dots travel along paths
- Metric pills are visible
- README content is correct
- Shields.io badges render
- Links work (projects, email, LinkedIn)

**Step 3: Visual verification**

Use Playwright to screenshot the live profile for review.

---

### Task 5: Iterate based on live render

GitHub's SVG rendering may differ from local preview. If needed:
- Adjust node opacity/size if too faint on GitHub
- Adjust metric pill contrast
- Tweak animation durations
- Fix any font rendering differences

Commit fixes as: `fix: adjust constellation for GitHub SVG rendering`
