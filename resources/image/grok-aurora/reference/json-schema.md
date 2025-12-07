# Grok Aurora JSON Schema

## Core Schema Structure

```json
{
  "subject": { ... },
  "composition": { ... },
  "lighting": "...",
  "environment": { ... },
  "negative_prompt": "...",
  "seed": 12345
}
```

---

## Standard Schema (Recommended)

### Basic Structure
```json
{
  "subject": {
    "description": "Two samurai clash in an ancient moonlit garden under cherry blossoms",
    "style": "anime illustration, high detail, rich color palette"
  },
  "composition": {
    "angle": "low-angle wide shot",
    "framing": "wide"
  },
  "lighting": "soft pink ambient (cherry blossoms glow) + sharp moonlight backlighting",
  "environment": {
    "setting": "ancient Japanese garden at night with sakura trees",
    "props": ["katana swords", "flowing martial arts robes", "petals drifting"]
  },
  "negative_prompt": "modern clothing, blurred, low resolution, text overlay",
  "seed": 12345
}
```

---

## Extended Schema (Complex Scenes)

### Shot Object
```json
"shot": {
  "camera_depth": "Cowboy Shot",
  "camera_view": "Low-angle",
  "camera_movement": "Dolly Zoom",
  "motion_level": "High"
}
```

| Parameter | Description | Values |
|-----------|-------------|--------|
| camera_depth | Subject distance | `Extreme Close-up`, `Close-up`, `Medium Shot`, `Cowboy Shot`, `Full Shot`, `Wide Shot`, `Extreme Wide Shot` |
| camera_view | Camera angle | `Eye-level`, `Low-angle`, `High-angle`, `Dutch Tilt`, `Overhead`, `Bird's-eye`, `Worm's-eye` |
| camera_movement | Motion type | `Static`, `Dolly Zoom`, `Tracking Shot`, `Pan`, `Tilt` |
| motion_level | Movement intensity | `Frozen`, `Low`, `Medium`, `High` |

### Cinematography Object
```json
"cinematography": {
  "lighting": [
    { "type": "Key Light", "position": "45° right", "intensity": "high", "color": "warm" },
    { "type": "Fill Light", "position": "left", "intensity": "low", "color": "cool" },
    { "type": "Rim Light", "position": "behind", "intensity": "medium" }
  ],
  "texture": "Film Grain, ISO 800",
  "depth_of_field": "f/1.8 shallow bokeh"
}
```

| Parameter | Description | Values |
|-----------|-------------|--------|
| lighting | Light sources array | Key, Fill, Rim, Practical, Ambient |
| texture | Surface quality | `Film Grain`, `ISO 3200 Noise`, `Analog Photography`, `Clean digital` |
| depth_of_field | Focus range | `f/1.2 extreme bokeh`, `f/2.8 moderate`, `f/16 deep focus` |

### Visual Details Object
```json
"visual_details": {
  "subjects": [
    { "id": "char1", "type": "woman", "attire": "cyberpunk armor", "features": "silver hair, blue eyes" },
    { "id": "char2", "type": "robot", "attire": "rusty metal plating" }
  ],
  "interaction": "char1 is repairing char2",
  "style": "neo-noir, neon lighting, rain-soaked streets"
}
```

---

## Negative Prompt

### Usage Notes
- Aurora's negative_prompt support is inconsistent
- May ignore or invert specified exclusions
- Prefer positive steering over negative exclusion

### Format Options
```json
// String format
"negative_prompt": "lowres, blurry, text, modern objects"

// Array format
"negative_prompt": ["lowres", "blurry", "text", "watermark"]
```

### Common Exclusions
| Category | Keywords |
|----------|----------|
| Quality | `lowres`, `blurry`, `jpeg artifacts`, `compression` |
| Unwanted | `text`, `watermark`, `logo`, `signature` |
| Style Control | `3d animation`, `photorealistic` (for anime) |
| Anatomical | `extra fingers`, `deformed`, `mutated` |

---

## Seed Control

```json
"seed": 12345
```

- Same seed + same prompt = same image
- Change seed for variations
- Essential for reproducible workflows

---

## Complete Example: Anime Action Scene

```json
{
  "title": "Epic Samurai Duel",
  "subject": {
    "description": "Two samurai warriors clash swords in an ancient moonlit temple garden. Cherry blossom petals swirl through the air as their blades meet, creating a shower of sparks. The older samurai wears traditional dark blue hakama while the younger one sports a crimson-trimmed white gi. Their faces show intense concentration and mutual respect.",
    "style": "anime illustration, high detail, rich color palette, dynamic action pose"
  },
  "composition": {
    "angle": "low-angle wide shot",
    "framing": "wide",
    "movement": "slow pan right capturing the arc of the sword swing"
  },
  "lighting": "soft pink ambient glow from cherry blossoms combined with sharp white moonlight creating dramatic backlighting and long shadows",
  "environment": {
    "setting": "ancient Japanese temple garden at night with sakura trees in full bloom",
    "props": ["katana swords with visible blade reflections", "flowing martial arts robes with wind movement", "scattered petals creating pink swirls"]
  },
  "negative_prompt": "modern clothing, blur, low resolution, text overlay, western architecture",
  "seed": 88776655
}
```

---

## Complete Example: Photorealistic Macro

```json
{
  "title": "Morning Dew Macro",
  "subject": {
    "description": "A perfectly spherical dewdrop clings to the tip of a vibrant emerald green leaf. Inside the droplet, the surrounding rainforest canopy is reflected upside-down in crystal clarity. Microscopic texture of the leaf surface visible beneath the droplet.",
    "style": "photorealistic macro photography, ultra-sharp focus"
  },
  "shot": {
    "camera_depth": "Extreme Close-up (macro)",
    "camera_view": "Eye-level, slightly low",
    "camera_movement": "Static",
    "motion_level": "Frozen"
  },
  "cinematography": {
    "lighting": ["warm morning sunlight from upper right", "soft ambient fill from surrounding foliage"],
    "texture": "Clean digital, minimal noise",
    "depth_of_field": "f/2.8, extremely shallow with creamy bokeh",
    "camera_metadata": "Canon EOS R5, 100mm Macro L lens"
  },
  "environment": {
    "setting": "tropical rainforest floor, early morning after rain",
    "props": ["fern fronds in background bokeh", "soft mist particles visible in light beams"]
  },
  "seed": 67890
}
```

---

## Style-Specific Templates

### Anime Style
```json
{
  "style": "2d anime, cel-shaded, hand-drawn illustration",
  "reference": "Studio Ghibli style",
  "negative_prompt": "3d style animation, photorealistic, CGI"
}
```

### Cinematic Realism
```json
{
  "style": "cinematic film still, anamorphic lens, 35mm film",
  "cinematography": {
    "texture": "Film Grain, Kodak Vision3 500T",
    "lighting": ["practical lighting", "motivated lighting sources"]
  }
}
```

### Fine Art
```json
{
  "style": "classical oil painting, museum quality",
  "reference": "Rembrandt lighting, Baroque composition",
  "texture": "visible brushstrokes, canvas texture"
}
```
