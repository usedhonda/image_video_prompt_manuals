# Cinematography Keywords

## Lighting Types

### Three-Point Lighting
| Light | Position | Purpose |
|-------|----------|---------|
| Key Light | 45° to subject | Primary illumination |
| Fill Light | Opposite key | Soften shadows |
| Rim/Back Light | Behind subject | Separation from background |

### Lighting Styles

| Keyword | Description | Mood |
|---------|-------------|------|
| `Rembrandt Lighting` | Triangle of light on cheek | Dramatic, artistic |
| `Butterfly Lighting` | Light from above center | Glamour, beauty |
| `Split Lighting` | Half face lit, half dark | Mystery, duality |
| `Loop Lighting` | Small shadow beside nose | Natural, flattering |
| `Broad Lighting` | Lit side toward camera | Wider face appearance |
| `Short Lighting` | Shadow side toward camera | Slimming, dramatic |

### Lighting Quality

| Keyword | Description |
|---------|-------------|
| `Hard Light` | Sharp shadows, defined edges |
| `Soft Light` | Diffused, gradual shadows |
| `High Key` | Bright, minimal shadows |
| `Low Key` | Dark, strong shadows |
| `Chiaroscuro` | Extreme light/dark contrast |
| `Volumetric Lighting` | Visible light beams, god rays |
| `Neon Noir` | Colored neon, cyberpunk aesthetic |
| `Practical Lighting` | Light sources visible in scene |

### Natural Lighting

| Keyword | Description |
|---------|-------------|
| `Golden Hour` | Warm, low sun |
| `Blue Hour` | Cool, pre-dawn/post-sunset |
| `Overcast` | Soft, even illumination |
| `Dappled Light` | Filtered through leaves |
| `Backlit` | Subject silhouetted |
| `Rim Light` | Edge lighting from behind |

---

## Lighting Array (Advanced)

```json
"lighting": [
  { "type": "Key Light", "position": "45° right", "intensity": "high", "color": "warm 5500K" },
  { "type": "Fill Light", "position": "left", "intensity": "low", "color": "cool 6500K" },
  { "type": "Rim Light", "position": "behind", "intensity": "medium", "color": "white" },
  { "type": "Practical", "source": "neon sign", "color": "pink" }
]
```

---

## Texture & Film Grain

| Keyword | Effect | Use Case |
|---------|--------|----------|
| `Film Grain` | Analog film texture | Cinematic, nostalgic |
| `ISO 800` | Moderate noise | Low light, natural |
| `ISO 3200` | High noise | Night, documentary |
| `Analog Photography` | Overall film characteristics | Vintage feel |
| `Clean Digital` | No noise | Modern, commercial |
| `Kodak Portra 400` | Warm skin tones | Portraits |
| `Fuji Velvia 50` | Saturated colors | Landscapes |
| `Kodak Vision3 500T` | Tungsten balanced | Cinematic night |

---

## Depth of Field

| Keyword | Aperture | Effect |
|---------|----------|--------|
| `Extreme Bokeh` | f/1.2 - f/1.4 | Creamy blur, dreamy |
| `Shallow DOF` | f/1.8 - f/2.8 | Subject isolation |
| `Moderate DOF` | f/4 - f/5.6 | Balanced focus |
| `Deep Focus` | f/11 - f/16 | Everything sharp |
| `Hyperfocal` | f/22+ | Maximum sharpness |

### Bokeh Descriptors
- `Creamy bokeh` - Smooth, rounded blur
- `Swirly bokeh` - Helios lens effect
- `Busy bokeh` - Distracting, harsh
- `Bubble bokeh` - Distinct circular highlights

---

## Camera Metadata Injection

### Camera Bodies
| Keyword | Characteristics |
|---------|----------------|
| `Leica SL2` | High contrast, sharpness |
| `Canon 5D Mark IV` | Natural colors, balanced |
| `Sony A7R IV` | High resolution, detail |
| `Hasselblad X2D` | Medium format, shallow DOF |
| `ARRI Alexa` | Cinematic, film-like |
| `RED Komodo` | High dynamic range |

### Lenses
| Keyword | Characteristics |
|---------|----------------|
| `50mm f/1.2 Noctilux` | Extreme bokeh, dreamy |
| `85mm f/1.4 Art` | Portrait, compression |
| `24mm f/1.4` | Wide, environmental |
| `100mm Macro` | Detail, close-up |
| `Anamorphic` | Cinematic flares, oval bokeh |
| `Vintage glass` | Imperfections, character |

---

## Combined Examples

### Cinematic Portrait
```json
"cinematography": {
  "lighting": [
    { "type": "Rembrandt", "intensity": "high" },
    { "type": "Rim Light", "color": "cool blue" }
  ],
  "texture": "Film Grain, Kodak Vision3 500T",
  "depth_of_field": "f/1.8 shallow, creamy bokeh",
  "camera_metadata": "ARRI Alexa, Cooke S4 50mm"
}
```

### Neon Noir Scene
```json
"cinematography": {
  "lighting": [
    { "type": "Neon", "color": "pink", "position": "left" },
    { "type": "Neon", "color": "cyan", "position": "right" },
    { "type": "Practical", "source": "rain-wet reflections" }
  ],
  "texture": "High contrast, crushed blacks",
  "depth_of_field": "f/2.8, urban bokeh with light streaks"
}
```

### Golden Hour Portrait
```json
"cinematography": {
  "lighting": ["Golden hour backlight", "Rim lighting from setting sun"],
  "texture": "Warm grain, Kodak Portra 400",
  "depth_of_field": "f/1.4, lens flare from sun"
}
```
