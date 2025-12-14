# NotebookLM Slide Generation Reference Index

## Router Instructions for AI

**IMPORTANT**: Do not load all files at once. Use this index to select only the files needed for the current task.

---

## File Loading Decision Tree

```
Step 1: ALWAYS load these first
├── 00-system-prompt.md
└── json-schema.md

Step 2: What type of request?
│
├─ Specific design style needed?
│   └─ Load: templates/styles/[style-name].json
│
├─ Corporate/business presentation?
│   └─ Load: templates/decks/corporate-strategy.json
│
├─ Minimalist/portfolio style?
│   └─ Load: templates/decks/minimal-portfolio.json
│
├─ Need specific slide layout types?
│   └─ Load: slide-catalog.md
│
├─ Typography/font selection?
│   └─ Load: keywords/typography.md
│
├─ Layout/grid questions?
│   └─ Load: keywords/layout-styles.md
│
├─ Want persistent notebook control?
│   └─ Load: strategies/source-guide-hack.md
│
├─ Audio Overview customization?
│   └─ Load: strategies/audio-overview.md
│
└─ Deep Research output structuring?
    └─ Load: strategies/deep-research.md
```

---

## Directory Structure

```
notebooklm/
├── INDEX.md                     ← You are here (Router)
├── 00-system-prompt.md          ← Always load first
├── json-schema.md               ← 3-layer structure definition
├── slide-catalog.md             ← 18 slide type definitions
│
├── keywords/
│   ├── layout-styles.md         # Grid, spacing, alignment
│   └── typography.md            # Fonts, colors, sizing
│
├── strategies/
│   ├── source-guide-hack.md     # Persistent control via source
│   ├── audio-overview.md        # Podcast persona injection
│   └── deep-research.md         # Structured report output
│
└── templates/
    ├── styles/                  # 10 design style presets
    │   ├── modern-editorial.json
    │   ├── japonism-textile.json
    │   ├── tech-art-neon.json
    │   ├── studio-mockup.json
    │   └── sports-athletic.json
    └── decks/                   # Complete deck templates
        ├── corporate-strategy.json
        └── minimal-portfolio.json
```

---

## Quick Reference: File Purpose

### Core (Always load json-schema.md)

| File | Load When |
|------|-----------|
| `json-schema.md` | **ALWAYS** - Defines 3-layer prompt structure |
| `slide-catalog.md` | Need specific slide layout types |

### Keywords (Load based on design needs)

| File | Load When |
|------|-----------|
| `keywords/layout-styles.md` | Grid systems, spacing, alignment |
| `keywords/typography.md` | Font families, color palettes |

### Strategies (Load based on workflow)

| File | Load When |
|------|-----------|
| `strategies/source-guide-hack.md` | Persistent notebook-wide control |
| `strategies/audio-overview.md` | Customizing podcast generation |
| `strategies/deep-research.md` | Structured research reports |

### Style Templates (Load based on aesthetic)

| Template | Style | Best For |
|----------|-------|----------|
| `modern-editorial.json` | Kinfolk magazine style | Lifestyle, editorial |
| `japonism-textile.json` | Japanese traditional | Cultural, artistic |
| `tech-art-neon.json` | Constructivism, neon | Tech, startup |
| `studio-mockup.json` | Apple-style mockups | Product, app |
| `sports-athletic.json` | Dynamic, energetic | Sports, fitness |

### Deck Templates (Load for complete presentations)

| Template | Use Case |
|----------|----------|
| `corporate-strategy.json` | Business strategy, investor deck |
| `minimal-portfolio.json` | Portfolio, case study |

---

## 3-Layer Structure Overview

| Layer | Japanese | Controls | Example |
|-------|----------|----------|---------|
| Layer 1 | 全体デザイン設定 | Tone, palette, typography | "Architectural", "#E9E9E9" |
| Layer 2 | 共通レイアウトルール | Navigation, grid, whitespace | "top-left", "12-column" |
| Layer 3 | カタログ定義 | Slide type variations | "scatter_title", "asymmetric_split" |

---

## Platform Limitations

| Constraint | Value |
|------------|-------|
| Output format | PDF only (no pptx) |
| Daily generation limit | 15 slides (AI Pro plan) |
| Context window | 2M tokens (Gemini 1.5 Pro) |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| v1.0 | 2025-12 | Initial release with 3-layer architecture |
