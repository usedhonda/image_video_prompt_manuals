# Layout Styles Keywords

## Grid Systems

| Keyword | Description | JSON Value |
|---------|-------------|------------|
| 12-column | Standard grid | `"columns": 12` |
| 6-column | Simple layout | `"columns": 6` |
| Strict alignment | Pixel-perfect | `"alignment": "strict"` |
| Flexible | Organic feel | `"alignment": "flexible"` |

---

## Spacing & Whitespace

| Keyword (EN) | Keyword (JP) | Effect |
|--------------|--------------|--------|
| Negative space | 余白 / ネガティブスペース | Empty canvas areas |
| Ma (間) | 間 | Japanese intentional emptiness |
| Breathing room | 余裕 | Generous padding |
| Tight | タイト | Minimal gaps |

### Padding Values

| Level | Pixels | Use Case |
|-------|--------|----------|
| Minimal | 20px | Dense information |
| Standard | 40px | Balanced |
| Generous | 60px+ | Premium feel |

---

## Navigation Positions

| Position | JSON Value | Best For |
|----------|------------|----------|
| Top-left | `"position": "top-left"` | Western reading flow |
| Top-right | `"position": "top-right"` | Japanese layouts |
| Bottom-left | `"position": "bottom-left"` | Footer style |
| Hidden | `"position": "none"` | Full-bleed slides |

---

## Split Layouts

| Type | Ratio | Description |
|------|-------|-------------|
| Even split | 50:50 | Balanced comparison |
| Asymmetric | 40:60 | Text + visual |
| Golden ratio | 38:62 | Classic proportion |
| Heavy visual | 30:70 | Image dominant |

---

## Alignment Keywords

| Keyword | Effect | JSON Example |
|---------|--------|--------------|
| center | Middle of canvas | `"position": "center"` |
| left-aligned | Western standard | `"align": "left"` |
| scattered | Random placement | `"placement": "scatter"` |
| stacked | Vertical stack | `"layout": "stack"` |

---

## Divider Styles

| Style | Weight | Use Case |
|-------|--------|----------|
| Hairline | 0.5px | Subtle separation |
| Thin | 1px | Standard |
| Medium | 2px | Emphasis |
| Bold | 4px+ | Strong division |

---

## Canvas Empty Ratio

| Ratio | Feel | Recommended For |
|-------|------|-----------------|
| 20% | Dense | Information-heavy |
| 30% | Balanced | Standard decks |
| 40% | Airy | Premium/minimal |
| 50%+ | Ultra-minimal | Luxury brands |

---

## JSON Examples

### Standard Layout
```json
"layout_rules": {
  "grid": {
    "columns": 12,
    "gutter": "20px",
    "alignment": "strict"
  },
  "whitespace": {
    "minimum_padding": "40px",
    "canvas_empty_ratio": 0.3
  }
}
```

### Premium Minimal
```json
"layout_rules": {
  "grid": {
    "columns": 12,
    "gutter": "24px",
    "alignment": "strict"
  },
  "whitespace": {
    "minimum_padding": "60px",
    "canvas_empty_ratio": 0.4,
    "concept": "Ma (間)"
  }
}
```
