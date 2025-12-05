# Video Workflow (Veo 3.1 Integration)

Nano Banana Pro images serve as inputs for video generation AI (Veo 3.1, Kling, Seedance, etc.).

---

## Basic Workflow

```
[Nano Banana Pro]    →    [Video AI]    →    [Edit]
   Image Generation       Video Creation     Finishing
   - Composition          - Veo 3.1
   - Product swap         - Kling 2.1
   - Character gen        - Seedance
```

---

## Frame Types for Veo 3.1

### First Frame
**Purpose**: Starting point for video animation

**Optimization**:
- `clear subject isolation` - Easy to track through motion
- `motion-ready pose` - Natural starting point for action
- `directional lighting` - Consistent throughout motion
- `defined edges` - Clean separation from background
- `negative space` - Room for subject movement

**Example Prompt**:
```
Portrait of a woman looking at camera,
slight smile beginning to form,
clear subject isolation, defined edges,
soft directional lighting from left,
negative space on right side for motion
```

---

### Ingredient (Character/Object Reference)
**Purpose**: Maintain consistency across video frames

**Optimization**:
- `distinctive features` - Unique identifiers that persist
- `consistent lighting` - Works in various scenes
- `neutral background` - Easy extraction
- `multiple angles` - Reference variety for 3D understanding

**Example Prompt**:
```
Character reference sheet:
- Front view, side view, 3/4 view
- Neutral gray background
- Even studio lighting
- Full body visible
- Distinctive features: red jacket, silver necklace
```

---

### Last Frame
**Purpose**: Ending point for video animation

**Optimization**:
- `arrival pose` - Natural ending position
- `settled composition` - Completed action feel
- `matching lighting` - Consistent with first frame

**Example Prompt**:
```
Same woman as first frame,
now with full smile,
slight head tilt to right,
settled relaxed pose,
matching directional lighting from left
```

---

## Video-Ready Prompt Examples

### Product Photography (Smoothie)
```
Close-up of a green smoothie swirling,
vibrant colors,
studio lighting,
healthy ingredients visible
```

### Product Swap
```
Replace [product A] in this image with [product B]
```

### Person Action (Drinking)
```
A woman drinking her beverage deliciously.
The angle at which she tilts the glass is 30 degrees.
Not too much.
```

**Tips**: Specify glass tilt angle (20-40°) to prevent unnatural liquid physics.

---

## Motion Prompts for Video AI

| Scene | Prompt Keywords |
|-------|-----------------|
| Stirring | `stirring`, `circular motion`, `liquid swirl` |
| Smiling at camera | `smiling at camera`, `eye contact`, `warm expression` |
| Drinking | Angle specification required (see above) |
| Walking | `walking forward`, `natural gait`, `approaching camera` |
| Turning | `turning head`, `looking over shoulder`, `pivot` |

---

## veo_optimization Schema

When generating images for Veo 3.1, include this section:

```json
{
  "veo_optimization": {
    "role": "first_frame | ingredient | last_frame",
    "motion_hint": "Description of intended motion",
    "framing_notes": "How space is allocated for movement",
    "consistency_notes": "Elements that must remain constant"
  }
}
```

### Role Definitions

| Role | When to Use | Key Requirements |
|------|-------------|------------------|
| `first_frame` | Video start | Motion-ready pose, negative space |
| `ingredient` | Character/object reference | Multiple angles, neutral background |
| `last_frame` | Video end | Arrival pose, settled composition |

---

## Template Recommendations

| Veo Use | Recommended Template | Notes |
|---------|---------------------|-------|
| First Frame | `scene-background.json` | Add motion space |
| Ingredient (Character) | `character-sheet.json` | Include multiple views |
| Ingredient (Product) | `product-shot.json` | Neutral background |
| Last Frame | Modify first frame template | Match lighting |

---

## Common Issues & Solutions

### Issue: Character changes between frames
**Solution**: Use character-sheet template with explicit identity anchors

### Issue: Lighting inconsistency
**Solution**: Specify exact lighting setup in both first and last frame

### Issue: Unnatural motion blur in video
**Solution**: Generate crisp, high-resolution source images

### Issue: Background elements drift
**Solution**: Use simple, geometric backgrounds for better tracking
