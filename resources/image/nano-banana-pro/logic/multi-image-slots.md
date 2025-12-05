# Multi-Image Slots Guide

Nano Banana Pro supports up to **14 reference images**. This guide defines how to allocate slots for optimal results.

---

## Slot Allocation Strategy

### Slots 1-3: Structure & Composition
**Purpose**: Define the physical layout, depth, and spatial relationships.

| Slot | Best Use | Example |
|------|----------|---------|
| 1 | Primary composition reference | Wireframe, layout sketch |
| 2 | Depth map / perspective guide | 3D depth visualization |
| 3 | Spatial structure backup | Alternative composition |

**Keywords to pair**:
- `match composition from reference`
- `follow depth structure`
- `maintain spatial layout`

---

### Slots 4-8: Style & Aesthetics
**Purpose**: Define the visual style, color palette, and texture.

| Slot | Best Use | Example |
|------|----------|---------|
| 4 | Primary style reference | Art piece, photo with desired look |
| 5 | Color palette reference | Color swatch, mood board |
| 6 | Texture reference | Surface detail, material |
| 7 | Lighting reference | Photo with desired lighting |
| 8 | Atmosphere reference | Weather, time of day |

**Keywords to pair**:
- `apply style from reference`
- `match color palette`
- `use texture from reference`
- `replicate lighting setup`

---

### Slots 9-14: Consistency & Identity
**Purpose**: Maintain character/object consistency across generations.

| Slot | Best Use | Example |
|------|----------|---------|
| 9 | Character face reference | Front-facing portrait |
| 10 | Character body reference | Full body shot |
| 11 | Character outfit reference | Clothing detail |
| 12 | Character pose reference | Specific pose |
| 13 | Object/product reference | Item to include |
| 14 | Secondary character/object | Additional element |

**Keywords to pair**:
- `same character as reference`
- `maintain identity from reference`
- `keep consistent features`
- `match outfit exactly`

---

## Mixing Strategies

### Strategy 1: Character Focus (5 images max recommended)
Best for: Character portraits, illustrations

```
Slot 1: Face reference (front)
Slot 2: Face reference (3/4 view)
Slot 3: Style reference
Slot 4: Color palette
Slot 5: Lighting reference
```

**Note**: More than 5 character references can cause feature blending issues.

---

### Strategy 2: Scene Composition (8-10 images)
Best for: Complex scenes, environments

```
Slots 1-2: Composition/layout
Slots 3-5: Style and atmosphere
Slots 6-8: Key objects/elements
Slots 9-10: Character references (if needed)
```

---

### Strategy 3: Product Photography (6-8 images)
Best for: E-commerce, product shots

```
Slot 1: Product reference (hero shot)
Slot 2: Product reference (detail)
Slot 3: Lighting reference
Slot 4: Background/environment
Slot 5: Style reference
Slot 6-8: Additional angles or variations
```

---

### Strategy 4: Style Transfer (3-5 images)
Best for: Applying artistic style to new content

```
Slot 1: Style reference (primary)
Slot 2: Style reference (secondary)
Slot 3: Color palette reference
Slot 4-5: Subject matter (what to stylize)
```

---

## Common Pitfalls

### Too Many Character References
**Problem**: Using 10+ character reference images causes face/body blending
**Solution**: Limit character references to 5, describe distinctive features in text

### Conflicting Style References
**Problem**: Mixing incompatible styles (e.g., anime + photorealistic)
**Solution**: Ensure all style slots share compatible aesthetics

### Ignoring Slot Priority
**Problem**: Random slot assignment leads to unpredictable results
**Solution**: Always place most important references in lower slot numbers

### Missing Text Description
**Problem**: Relying only on images without text guidance
**Solution**: Always include text prompt describing how to use each reference

---

## Reference Image Prompt Pattern

When using multiple images, structure your prompt:

```json
{
  "image_references": {
    "composition": "Use layout from image 1",
    "style": "Apply artistic style from image 4",
    "character": "Same person as shown in image 9, maintaining facial features",
    "lighting": "Match lighting setup from image 7"
  }
}
```

---

## Quick Reference Table

| Use Case | Recommended Slots | Max Images |
|----------|-------------------|------------|
| Simple portrait | 1-3 | 3-4 |
| Character sheet | 1-5 | 5 |
| Product photo | 1-6 | 6-8 |
| Complex scene | 1-10 | 8-10 |
| Full production | 1-14 | 10-14 |
