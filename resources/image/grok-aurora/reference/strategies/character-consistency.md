# Character Consistency Strategy

Techniques for maintaining identical character appearance across multiple images.

---

## Overview

AI image generation struggles with character consistency because each generation is independent. This guide provides methods to enforce visual coherence.

---

## Method 1: Anchor Image Workflow

### Step 1: Create Character Sheet

Generate a reference image with multiple views:

```json
{
  "subject": {
    "description": "Character reference sheet showing same woman from front view, 3/4 view, and side profile. Consistent features across all views.",
    "style": "clean character design sheet, white background, studio lighting"
  },
  "character": {
    "features": "25 year old woman, long black hair, green eyes, heart-shaped face, small nose",
    "attire": "simple white t-shirt to show body proportions",
    "expression": "neutral"
  },
  "layout": "horizontal triptych with front/3-4/side views"
}
```

### Step 2: Save as Anchor
Store this image as the definitive reference for all future generations.

### Step 3: Use as Reference
When generating new scenes, upload anchor image and request consistency:

```
Using the attached character reference, generate a new scene where this exact same person is:
[new scene description]

Maintain all facial features, hair, and proportions exactly.
```

---

## Method 2: Detailed Character Profile

### Create Comprehensive JSON Profile

```json
{
  "character_id": "maya_chen",
  "physical_attributes": {
    "age": "25",
    "gender": "female",
    "ethnicity": "Chinese-American",
    "height": "165cm",
    "build": "athletic, slim"
  },
  "face": {
    "shape": "heart-shaped, defined jawline",
    "proportions": "symmetrical, high cheekbones",
    "skin": {
      "tone": "warm ivory",
      "texture": "clear with light freckles across nose"
    }
  },
  "eyes": {
    "shape": "almond, slightly upturned corners",
    "color": "dark brown, almost black",
    "size": "medium-large",
    "lashes": "naturally long, dark",
    "brows": "straight, well-defined, natural thickness"
  },
  "nose": {
    "type": "small, slightly upturned",
    "bridge": "medium height"
  },
  "lips": {
    "shape": "full, bow-shaped",
    "color": "natural pink"
  },
  "hair": {
    "color": "black with subtle brown highlights in sunlight",
    "length": "mid-back",
    "texture": "straight with slight wave at ends",
    "typical_style": "loose or low ponytail"
  },
  "distinguishing_marks": [
    "small mole below left eye",
    "light scar on right eyebrow"
  ]
}
```

### Embed in Every Prompt

```json
{
  "character": { /* paste full profile */ },
  "scene": {
    "setting": "rainy Tokyo street at night",
    "action": "walking with umbrella",
    "attire": "black leather jacket, jeans"
  }
}
```

---

## Method 3: VLM Extraction

### Using Grok's Vision Language Model

1. **Generate Initial Image**
   - Create first scene with character

2. **Extract Features**
   Upload image to Grok Chat:
   ```
   Analyze this person's face and body with extreme detail. Output a JSON profile containing:
   - Precise facial proportions and bone structure
   - Exact eye color, shape, and spacing
   - Nose shape and size relative to face
   - Lip shape and fullness
   - Hair color gradient from roots to tips
   - Skin undertone and any marks
   - Body proportions and build

   Be extremely specific. This will be used to recreate this exact person.
   ```

3. **Use Extracted Profile**
   Apply the AI-generated profile to new scenes.

---

## Method 4: Multimodal Editing

### Partial Image Replacement

When a generated image has wrong face:

1. **Generate New Scene**
   - Create scene with approximate character

2. **Face Replacement**
   - Upload to Grok Edit function
   - Select face region
   - Prompt: "Replace this face with the face from [anchor image]. Match lighting and angle automatically."

3. **Aurora Auto-Adjustment**
   - Aurora's multimodal understanding adjusts:
     - Lighting direction
     - Color temperature
     - Shadow angles
     - Expression to match pose

---

## Method 5: Seed-Based Variation

### Using Seeds for Consistency

```json
{
  "character_seed": 42,  // Same seed for character generation
  "scene_variation": {
    "base_prompt": "Maya Chen in...",
    "scene_a": { "setting": "office", "seed": 100 },
    "scene_b": { "setting": "beach", "seed": 200 },
    "scene_c": { "setting": "concert", "seed": 300 }
  }
}
```

**Note**: Seed alone is insufficient - combine with detailed profiles.

---

## Best Practices

### 1. Feature Hierarchy

Most important to maintain (top priority):
1. Face shape and proportions
2. Eye color and shape
3. Hair color and texture
4. Distinguishing marks

Less critical:
- Exact skin texture
- Hair style (can vary)
- Body pose

### 2. Lighting Compensation

Different scenes have different lighting. Include adjustment notes:

```json
{
  "character": { ... },
  "lighting_compensation": {
    "note": "Adjust skin tone for warm/cool lighting",
    "reference_tone": "neutral 5500K baseline",
    "current_scene": "warm tungsten 3200K - add warmth to skin"
  }
}
```

### 3. Expression Consistency

Define expression range:

```json
"expression_range": {
  "neutral": "slight smile, relaxed eyes",
  "happy": "wide smile showing teeth, eye crinkles",
  "serious": "slight frown, focused eyes, set jaw"
}
```

### 4. Avoid Conflicting Details

Don't let scene elements override character:

```json
// BAD - scene may override character
"scene": "woman with blonde hair walking"

// GOOD - character profile takes precedence
"character": { "hair": "black, mid-back length" },
"scene": "walking in park"
```

---

## Troubleshooting

### Feature Drift
**Problem**: Character changes slightly each generation
**Solution**: Add "exact match" instruction:
```json
"instruction": "Character must match reference exactly. Do not interpret or modify any physical features."
```

### Style Interference
**Problem**: Different art styles change character appearance
**Solution**: Lock realistic proportions:
```json
"character_constraints": {
  "proportions": "realistic human anatomy regardless of art style",
  "features": "maintain exact facial structure even in stylized rendering"
}
```

### Lighting Color Cast
**Problem**: Colored lighting changes apparent skin/hair color
**Solution**: Describe base colors explicitly:
```json
"hair": "appears warm brown in neutral light, true color is cool black"
"skin": "warm ivory base, may appear golden in warm light"
```

---

## Workflow Summary

```
[Create Character Profile]
         ↓
[Generate Anchor Image (Multi-View)]
         ↓
[Extract VLM Profile from Anchor]
         ↓
[Merge Manual + VLM Profiles]
         ↓
[For Each New Scene]
    ├── Include Full Character Profile
    ├── Upload Anchor as Reference
    ├── Specify Scene Changes Only
    └── Verify Output → Edit if Needed
         ↓
[Consistent Character Across Scenes]
```
