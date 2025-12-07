# JSON Remix Method

Technique for maintaining style/composition while modifying specific elements.

---

## Overview

JSON Remix enables precise control over image variations by:
1. Analyzing a reference image into JSON structure
2. Extracting visual parameters as data
3. Remixing by modifying specific fields

---

## Three-Phase Workflow

### Phase 1: Analysis

Upload reference image to Grok Chat and request JSON extraction:

**Prompt:**
```
Analyze this image and generate a comprehensive JSON profile containing:
- Visual composition (camera angle, framing, depth of field)
- Lighting setup (sources, direction, quality, color temperature)
- Color palette (dominant, accent, mood)
- Subject details (pose, expression, attire, features)
- Environment (setting, props, atmosphere)
- Style (artistic movement, texture, rendering quality)

Output as valid JSON only.
```

### Phase 2: Extraction

Grok returns structured data:

```json
{
  "shot": {
    "camera_depth": "Medium Close-up",
    "camera_view": "Eye-level, slightly left",
    "depth_of_field": "f/2.8, soft background bokeh"
  },
  "cinematography": {
    "lighting": [
      { "type": "Natural window light", "position": "upper left", "quality": "soft" },
      { "type": "Bounce fill", "position": "right", "intensity": "subtle" }
    ],
    "color_temperature": "5600K daylight",
    "texture": "Clean digital, minimal grain"
  },
  "color_palette": {
    "dominant": ["warm beige", "soft cream"],
    "accent": ["deep burgundy", "gold"],
    "mood": "warm, intimate, nostalgic"
  },
  "subject": {
    "type": "woman",
    "age": "late 20s",
    "features": "brown wavy hair, green eyes, light freckles",
    "expression": "contemplative, soft smile",
    "pose": "seated, chin resting on hand",
    "attire": "cream knit sweater, gold necklace"
  },
  "environment": {
    "setting": "cafe interior, morning",
    "props": ["coffee cup", "book", "wooden table"],
    "atmosphere": "cozy, quiet, sunlit"
  },
  "style": {
    "aesthetic": "lifestyle photography",
    "reference": "editorial, magazine quality"
  }
}
```

### Phase 3: Remix

Modify specific fields while keeping others:

**Change: Cafe → Library at Night**
```json
{
  // Keep original shot, cinematography unchanged
  "shot": { ... },

  // Modify lighting for night scene
  "cinematography": {
    "lighting": [
      { "type": "Warm lamp light", "position": "left", "quality": "soft" },
      { "type": "Ambient window moonlight", "position": "right", "color": "cool blue" }
    ],
    "color_temperature": "3200K tungsten",
    "texture": "Film grain, Kodak Portra 800"
  },

  // Shift color palette
  "color_palette": {
    "dominant": ["warm amber", "dark wood tones"],
    "accent": ["deep green", "brass"],
    "mood": "intimate, studious, evening"
  },

  // Keep subject identical
  "subject": { ... },

  // Change environment only
  "environment": {
    "setting": "vintage library, late evening",
    "props": ["leather-bound books", "reading lamp", "antique desk"],
    "atmosphere": "quiet, scholarly, warm lamplight"
  },

  "style": { ... }
}
```

---

## Use Cases

### 1. Time of Day Shift
```json
// Original
"environment": { "setting": "beach, midday" }
"cinematography": { "lighting": ["harsh overhead sun"] }

// Remix: Sunset
"environment": { "setting": "beach, sunset" }
"cinematography": { "lighting": ["golden hour backlight", "warm rim light"] }
```

### 2. Style Transfer
```json
// Original: Photorealistic
"style": { "aesthetic": "photorealistic, DSLR quality" }

// Remix: Anime
"style": {
  "aesthetic": "anime illustration, cel-shaded",
  "reference": "Studio Ghibli style"
}
```

### 3. Season Change
```json
// Original
"environment": { "setting": "park, spring", "props": ["cherry blossoms"] }
"color_palette": { "dominant": ["pink", "soft green"] }

// Remix: Autumn
"environment": { "setting": "park, autumn", "props": ["fallen leaves", "fog"] }
"color_palette": { "dominant": ["orange", "deep red", "brown"] }
```

### 4. Outfit Variation
```json
// Keep everything, change only attire
"subject": {
  ...
  "attire": "evening gown, diamond jewelry"  // was: casual sweater
}
```

---

## Character Consistency Application

For maintaining same character across scenes:

### Step 1: Create Character Profile
```json
"character_profile": {
  "id": "protagonist_maya",
  "physical": {
    "age": "25",
    "ethnicity": "East Asian",
    "height": "medium",
    "build": "athletic"
  },
  "features": {
    "hair": "black, shoulder-length, slight wave",
    "eyes": "dark brown, almond-shaped",
    "skin": "warm undertone, clear",
    "distinguishing": "small mole below left eye"
  }
}
```

### Step 2: Lock Character, Vary Scene
```json
{
  // LOCKED - Never change
  "character_profile": { ... },

  // VARIABLE - Change per scene
  "scene": {
    "setting": "corporate office",
    "lighting": "fluorescent overhead",
    "attire": "business suit"
  }
}
```

---

## Advanced: VLM-Assisted Remix

### Using Grok's Vision for Consistency

1. Generate Scene A with character
2. Upload Scene A to Grok Chat
3. Request: "Extract character features only as JSON"
4. Use extracted features in Scene B prompt

```
Given this image, extract ONLY the character's physical features as JSON:
- Face shape, proportions
- Hair color, style, texture
- Eye color, shape
- Skin tone, texture
- Any distinguishing marks

Do not include pose, expression, or clothing.
```

---

## Remix Workflow Diagram

```
[Reference Image]
       ↓
[Grok Chat: JSON Extraction]
       ↓
[JSON Profile Generated]
       ↓
[Identify Fields to Modify]
       ↓
[Keep: camera, lighting ratios, character]
[Change: environment, time, outfit]
       ↓
[Modified JSON to Aurora]
       ↓
[Consistent Variation Generated]
```

---

## Tips

1. **Preserve Ratios**: Keep lighting intensity ratios even when changing sources
2. **Lock Camera**: Camera position is hardest to match - keep identical
3. **Character First**: Extract character profile separately for maximum consistency
4. **Incremental Changes**: Change one major element at a time for predictable results
5. **Seed Stability**: Use same seed for minor variations, new seed for major changes
