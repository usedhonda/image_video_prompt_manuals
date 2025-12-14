# NotebookLM 3-Layer JSON Schema

## Overview

NotebookLM slide generation can be controlled via a 3-layer JSON architecture:

| Layer | Japanese | Purpose |
|-------|----------|---------|
| Layer 1 | 全体デザイン設定 | Global design tokens |
| Layer 2 | 共通レイアウトルール | Layout constraints |
| Layer 3 | カタログ定義 | Slide type variations |

---

## Master Schema

```json
{
  "design_system": {
    "meta": {
      "name": "String",
      "tone": "String",
      "description": "String"
    },
    "color_palette": {
      "background": {
        "primary": "#HEXCODE",
        "secondary": "#HEXCODE",
        "dark_mode": "#HEXCODE"
      },
      "text": {
        "primary": "#HEXCODE",
        "secondary": "#HEXCODE",
        "muted": "#HEXCODE"
      },
      "accents": {
        "highlight": "#HEXCODE",
        "structural_lines": "#HEXCODE"
      }
    },
    "typography": {
      "headings": {
        "font_family": "String",
        "weight": "Bold|Regular|Light",
        "case": "uppercase|lowercase|capitalize",
        "kerning": "String"
      },
      "body": {
        "font_family": "String",
        "weight": "Regular|Light",
        "size": "String",
        "line_height": "Number"
      }
    }
  },
  "layout_rules": {
    "navigation": {
      "position": "top-left|top-right|bottom-left|bottom-right",
      "format": "String",
      "font_size": "String"
    },
    "grid": {
      "columns": 12,
      "gutter": "String",
      "alignment": "strict|flexible"
    },
    "whitespace": {
      "minimum_padding": "String",
      "canvas_empty_ratio": "Number",
      "concept": "String"
    }
  },
  "slide_catalog": [
    {
      "id": "String",
      "name": "String",
      "description": "String",
      "elements": ["Array of element types"],
      "background_override": "#HEXCODE (optional)",
      "text_override": "#HEXCODE (optional)"
    }
  ]
}
```

---

## Layer 1: Design System (全体デザイン設定)

### Tone Values

| Tone | Description | Use Case |
|------|-------------|----------|
| `Architectural` | Minimalist, structural | Portfolio, corporate |
| `Editorial` | Magazine-style, airy | Lifestyle, culture |
| `Energetic` | Dynamic, bold | Sports, startup |
| `Traditional` | Classic, refined | Luxury, heritage |
| `Technical` | Precise, grid-based | Tech, engineering |

### Color Palette Pattern

```json
"color_palette": {
  "background": {
    "primary": "#E9E9E9",
    "secondary": "#FFFFFF",
    "dark_mode": "#1A1A1A"
  },
  "text": {
    "primary": "#000000",
    "secondary": "#333333",
    "muted": "#888888"
  },
  "accents": {
    "highlight": "#FF3333",
    "structural_lines": "#000000"
  }
}
```

### Typography Pattern

| Element | Recommended Fonts | Notes |
|---------|-------------------|-------|
| English Headings | Helvetica Now, Inter, Futura | Sans-serif, bold |
| Japanese Headings | Noto Sans JP, Hiragino | Gothic, medium+ |
| English Body | Georgia, Times | Serif for editorial |
| Japanese Body | Noto Sans JP, YuGothic | Size 14pt, line-height 1.8 |

---

## Layer 2: Layout Rules (共通レイアウトルール)

### Navigation

```json
"navigation": {
  "position": "top-left",
  "format": "{section_number}. {section_title}",
  "font_size": "10pt",
  "instruction": "Display section number and title on all slides"
}
```

### Grid System

```json
"grid": {
  "columns": 12,
  "gutter": "20px",
  "alignment": "strict",
  "instruction": "All elements must align to grid intersections"
}
```

### Whitespace (Negative Space / 余白)

```json
"whitespace": {
  "minimum_padding": "60px",
  "canvas_empty_ratio": 0.4,
  "concept": "Ma (間) - intentional emptiness",
  "instruction": "Leave at least 40% of canvas empty for premium feel"
}
```

---

## Layer 3: Slide Catalog (カタログ定義)

See `slide-catalog.md` for complete 18-type definitions.

### Example Slide Types

```json
"slide_catalog": [
  {
    "id": "scatter_title",
    "name": "タイトル・タイポグラフィ",
    "description": "Scattered layout with award badges and keywords as stamps",
    "elements": ["award_badges", "keywords", "central_title"]
  },
  {
    "id": "asymmetric_split",
    "name": "テキスト＋データ強調",
    "description": "Asymmetric split with narrative text left, giant metric right",
    "elements": ["text_block", "giant_metric", "vertical_line"]
  },
  {
    "id": "cinematic_center",
    "name": "中央配置（ダークモード）",
    "description": "Cinematic dark background with centered key visual",
    "background_override": "#000000",
    "text_override": "#FFFFFF"
  }
]
```

---

## Complete Example

```json
{
  "design_system": {
    "meta": {
      "name": "Kyoto_Minimal_v2",
      "tone": "Architectural",
      "description": "Japanese minimalism with negative space emphasis"
    },
    "color_palette": {
      "background": {
        "primary": "#E9E9E9",
        "secondary": "#FFFFFF",
        "dark_mode": "#1A1A1A"
      },
      "text": {
        "primary": "#000000",
        "secondary": "#333333",
        "muted": "#888888"
      },
      "accents": {
        "highlight": "#FF3333",
        "structural_lines": "#000000"
      }
    },
    "typography": {
      "headings": {
        "font_family": "Helvetica Now Display",
        "weight": "Bold",
        "case": "uppercase",
        "kerning": "tight (-2%)"
      },
      "body": {
        "font_family": "Noto Sans JP",
        "weight": "Regular",
        "size": "14pt",
        "line_height": 1.8
      }
    }
  },
  "layout_rules": {
    "navigation": {
      "position": "top-left",
      "format": "{section_number}. {section_title}",
      "font_size": "10pt"
    },
    "grid": {
      "columns": 12,
      "gutter": "20px",
      "alignment": "strict"
    },
    "whitespace": {
      "minimum_padding": "60px",
      "canvas_empty_ratio": 0.4,
      "concept": "Ma (間)"
    }
  },
  "slide_catalog": [
    {
      "id": "scatter_title",
      "name": "タイトル・タイポグラフィ",
      "description": "Scattered layout with award badges",
      "elements": ["award_badges", "keywords", "central_title"]
    },
    {
      "id": "asymmetric_split",
      "name": "テキスト＋データ強調",
      "description": "Asymmetric split layout",
      "elements": ["text_block", "giant_metric", "vertical_line"]
    }
  ]
}
```

---

## Usage Notes

### JSON vs YAML
- **JSON**: Recommended for API integration, strict parsing
- **YAML**: Better for manual editing in NotebookLM UI (fewer tokens)

### Token Efficiency
JSON has higher syntax overhead than YAML. For manual paste into NotebookLM:
- Remove unnecessary whitespace
- Use short key names where possible
- Omit optional fields if using defaults
