# Typography Vocabulary

## Text Rendering Best Practices

Nano Banana Pro excels at text rendering, but requires specific guidance for optimal results.

### Golden Rules
1. **Keep text short** - Maximum 6 words per text element
2. **High contrast** - Text should stand out from background
3. **Simple fonts** - Sans-serif generally works best
4. **Clear placement** - Specify exact position

---

## Font Style Keywords

### Serif Fonts
| Keyword | Effect | Best For |
|---------|--------|----------|
| `serif font` | Classic, traditional | Luxury, editorial |
| `Times New Roman style` | Newspaper, formal | News, documents |
| `Georgia style` | Elegant, readable | Body text, articles |
| `Playfair Display style` | High contrast, elegant | Headlines, luxury |

### Sans-Serif Fonts
| Keyword | Effect | Best For |
|---------|--------|----------|
| `sans-serif font` | Modern, clean | Tech, UI, contemporary |
| `Helvetica style` | Neutral, corporate | Business, signage |
| `Futura style` | Geometric, modern | Fashion, art |
| `bold sans-serif` | Strong, impactful | Headlines, posters |

### Display & Decorative
| Keyword | Effect | Best For |
|---------|--------|----------|
| `hand-lettered` | Personal, organic | Artisan, craft |
| `script font` | Elegant, flowing | Invitations, luxury |
| `gothic blackletter` | Medieval, dramatic | Metal, horror |
| `stencil font` | Military, industrial | Urban, tactical |
| `pixel font` | Retro digital | Gaming, tech nostalgia |
| `neon sign lettering` | Glowing, urban | Nightlife, retro |

---

## Text Placement

### Position Keywords
| Keyword | Location |
|---------|----------|
| `center-middle` | Dead center of frame |
| `top-center` | Top edge, centered |
| `bottom-center` | Bottom edge, centered |
| `top-left` | Upper left corner |
| `top-right` | Upper right corner |
| `bottom-left` | Lower left corner |
| `bottom-right` | Lower right corner |
| `left-aligned` | Along left edge |
| `right-aligned` | Along right edge |

### Layout Keywords
| Keyword | Effect |
|---------|--------|
| `text overlay` | Text on top of image |
| `text in banner` | Text within a bar/ribbon |
| `floating text` | Text without background |
| `text in speech bubble` | Comic-style dialogue |
| `text in title card` | Cinematic title treatment |
| `watermark style` | Semi-transparent, corner |

---

## Text Material & Effects

### Surface Materials
| Keyword | Effect | Best For |
|---------|--------|----------|
| `embossed` | Raised from surface | Luxury, formal |
| `debossed` | Pressed into surface | Leather, paper |
| `engraved` | Carved into material | Metal, stone |
| `metallic` | Shiny, reflective | Awards, premium |
| `gold foil` | Luxury gold shine | Certificates, packaging |
| `chrome` | Mirror-like metal | Futuristic, tech |
| `glass` | Transparent, refractive | Modern, clean |

### Light Effects
| Keyword | Effect | Best For |
|---------|--------|----------|
| `neon` | Glowing tube light | Urban, nightlife |
| `LED` | Digital display glow | Tech, modern |
| `backlit` | Light behind text | Signs, dramatic |
| `glowing` | Soft light emission | Fantasy, magical |
| `holographic` | Rainbow iridescence | Futuristic |
| `shadow` | Drop shadow depth | Readability |

### Texture Effects
| Keyword | Effect | Best For |
|---------|--------|----------|
| `distressed` | Worn, weathered | Vintage, grunge |
| `grunge` | Dirty, textured | Rock, urban |
| `clean` | Crisp, sharp edges | Corporate, modern |
| `3D extruded` | Depth, dimension | Posters, signage |
| `outline only` | Hollow letters | Subtle, overlay |

---

## Text Size & Weight

### Size Keywords
| Keyword | Relative Size |
|---------|---------------|
| `large headline` | Dominant, primary |
| `subheadline` | Secondary emphasis |
| `body text` | Standard reading size |
| `caption` | Small, supporting |
| `fine print` | Very small |

### Weight Keywords
| Keyword | Effect |
|---------|--------|
| `bold` | Heavy, strong |
| `semibold` | Medium emphasis |
| `regular` | Normal weight |
| `light` | Thin, elegant |
| `ultra-bold` | Maximum impact |

---

## Common Text Use Cases

### Logo/Brand Text
```
"bold sans-serif, clean, center-middle, white text on dark background"
```

### Movie Poster Title
```
"large headline, metallic gold, embossed, top-center, dramatic lighting"
```

### Product Label
```
"serif font, elegant, gold foil on black, center-middle"
```

### Neon Sign
```
"neon sign lettering, glowing pink, slight flicker, night scene"
```

### Social Media Caption
```
"bold sans-serif, white with shadow, bottom-left, overlay on image"
```

---

## Negative Constraints for Text

Always include these in negative prompts when text is important:
```json
"negative_constraints": [
  "misspelling",
  "illegible text",
  "gibberish",
  "text artifacts",
  "blurry text",
  "distorted letters",
  "wrong spelling",
  "extra letters",
  "missing letters"
]
```

---

## Text Schema Example

```json
{
  "text_elements": [
    {
      "content": "HELLO",
      "font_style": "bold sans-serif",
      "placement": "center-middle",
      "material": "neon",
      "color": "pink",
      "size": "large headline"
    }
  ]
}
```
