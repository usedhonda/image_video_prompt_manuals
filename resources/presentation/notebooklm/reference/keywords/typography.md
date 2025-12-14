# Typography & Color Keywords

## Font Categories

### English Sans-Serif (Headings)

| Font | Style | Use Case |
|------|-------|----------|
| Helvetica Now | Modern classic | Corporate, minimal |
| Inter | Clean digital | Tech, startup |
| Futura | Geometric | Bold statements |
| Montserrat | Contemporary | Marketing |
| SF Pro | Apple aesthetic | Product, app |

### English Serif (Editorial)

| Font | Style | Use Case |
|------|-------|----------|
| Georgia | Readable | Body text |
| Times New Roman | Classic | Formal |
| Playfair Display | Elegant | Luxury |
| Garamond | Traditional | Publishing |

### Japanese Gothic (ゴシック体)

| Font | Style | Use Case |
|------|-------|----------|
| Noto Sans JP | Universal | All-purpose |
| Hiragino Sans | macOS default | Clean |
| YuGothic | Windows default | Standard |
| M+ | Modern | Tech |

### Japanese Mincho (明朝体)

| Font | Style | Use Case |
|------|-------|----------|
| Noto Serif JP | Universal | Editorial |
| Hiragino Mincho | Elegant | Premium |
| YuMincho | Traditional | Formal |

---

## Font Weight Keywords

| Weight | Number | Use Case |
|--------|--------|----------|
| Thin | 100 | Delicate accents |
| Light | 300 | Airy feel |
| Regular | 400 | Body text |
| Medium | 500 | Slight emphasis |
| Bold | 700 | Headlines |
| Black | 900 | Maximum impact |

---

## Text Transform

| Keyword | Effect | JSON Value |
|---------|--------|------------|
| uppercase | ALL CAPS | `"case": "uppercase"` |
| lowercase | all small | `"case": "lowercase"` |
| capitalize | First Letter | `"case": "capitalize"` |
| none | As Written | `"case": "none"` |

---

## Line Height (行間)

| Value | Feel | Use Case |
|-------|------|----------|
| 1.2 | Tight | Headlines |
| 1.5 | Standard | Body text |
| 1.8 | Generous | Japanese text |
| 2.0+ | Airy | Editorial, poetry |

---

## Color Palettes by Style

### Architectural Minimal
```json
"color_palette": {
  "background": {"primary": "#E9E9E9", "secondary": "#FFFFFF"},
  "text": {"primary": "#000000", "secondary": "#333333"},
  "accents": {"highlight": "#FF3333"}
}
```

### Editorial Warm
```json
"color_palette": {
  "background": {"primary": "#F5F0E8", "secondary": "#FFFFFF"},
  "text": {"primary": "#2C2C2C", "secondary": "#5A5A5A"},
  "accents": {"highlight": "#C4A77D"}
}
```

### Tech Neon
```json
"color_palette": {
  "background": {"primary": "#1A1A1A", "dark_mode": "#000000"},
  "text": {"primary": "#FFFFFF", "secondary": "#CCCCCC"},
  "accents": {"highlight": "#00FF88", "secondary": "#FF00FF"}
}
```

### Sports Dynamic
```json
"color_palette": {
  "background": {"primary": "#000000"},
  "text": {"primary": "#FFFFFF"},
  "accents": {"highlight": "#BFFF00", "secondary": "#FF6B00"}
}
```

### Japonism Traditional
```json
"color_palette": {
  "background": {"primary": "#F5F1E6"},
  "text": {"primary": "#1A1A1A", "secondary": "#4A4A4A"},
  "accents": {"gold": "#B8860B", "vermillion": "#E34234", "indigo": "#264653"}
}
```

---

## Color Keywords (JP → EN)

| Japanese | English | Hex Example |
|----------|---------|-------------|
| 墨色 | Ink black | #1A1A1A |
| 生成り | Unbleached | #F5F1E6 |
| 錆金 | Rust gold | #B8860B |
| 緋色 | Vermillion | #E34234 |
| 藍色 | Indigo | #264653 |
| 若草 | Young grass | #90B44B |

---

## Typography JSON Examples

### Bold Headlines + Readable Body
```json
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
```

### Editorial Elegance
```json
"typography": {
  "headings": {
    "font_family": "Playfair Display",
    "weight": "Regular",
    "case": "capitalize"
  },
  "body": {
    "font_family": "Georgia",
    "weight": "Regular",
    "size": "16pt",
    "line_height": 1.6
  }
}
```

### Japanese Minimal
```json
"typography": {
  "headings": {
    "font_family": "Hiragino Sans",
    "weight": "Bold",
    "size": "24pt"
  },
  "body": {
    "font_family": "Noto Sans JP",
    "weight": "Regular",
    "size": "14pt",
    "line_height": 1.8
  }
}
```
