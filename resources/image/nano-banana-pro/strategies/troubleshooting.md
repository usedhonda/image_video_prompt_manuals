# Troubleshooting Guide

Common issues and solutions for Nano Banana Pro image generation.

---

## Quick Reference: Negative Prompt Presets

### Universal Negatives (Always Include)
```json
"negative_constraints": [
  "low quality",
  "blurry",
  "watermark",
  "signature",
  "jpeg artifacts"
]
```

### Portrait Negatives
```json
"negative_constraints": [
  "deformed face",
  "extra fingers",
  "missing limbs",
  "distorted hands",
  "asymmetrical eyes",
  "unnatural skin texture",
  "plastic skin",
  "mannequin-like"
]
```

### Text Negatives
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

### Product Photography Negatives
```json
"negative_constraints": [
  "reflections of photographer",
  "uneven lighting",
  "harsh shadows",
  "color cast",
  "dust spots",
  "fingerprints"
]
```

### Anime/Illustration Negatives
```json
"negative_constraints": [
  "bad anatomy",
  "wrong proportions",
  "extra limbs",
  "fused fingers",
  "poorly drawn hands",
  "poorly drawn face"
]
```

---

## Common Issues & Solutions

### Issue: Plastic/Artificial Skin
**Symptoms**: Skin looks like plastic, too smooth, mannequin-like

**Solution**:
```
Add to prompt: "natural skin texture, subtle pores, micro-contrast, realistic skin"
Add to negative: "plastic skin, overly smooth, mannequin-like, airbrushed"
```

### Issue: Garbled/Unreadable Text
**Symptoms**: Text is misspelled, gibberish, or distorted

**Solution**:
1. Keep text to 6 words or fewer
2. Use simple sans-serif fonts
3. Specify high contrast background
4. Add text-specific negatives

```
Add to prompt: "clear legible text, bold sans-serif, high contrast"
Add to negative: "misspelling, gibberish, text artifacts, illegible"
```

### Issue: Deformed Hands/Fingers
**Symptoms**: Extra fingers, fused fingers, wrong proportions

**Solution**:
```
Add to prompt: "anatomically correct hands, five fingers, natural hand pose"
Add to negative: "extra fingers, deformed hands, fused fingers, missing fingers"
```

### Issue: Mushy/Blurry Background
**Symptoms**: Background lacks detail, looks like watercolor

**Solution**:
```
Add to prompt: "sharp background, high micro-contrast, crisp textures, defined details"
Add to negative: "blurry background, soft focus background, motion blur"
```

### Issue: Inconsistent Lighting
**Symptoms**: Multiple light sources that don't make sense

**Solution**:
```
Add to prompt: "single key light from [direction], consistent lighting, motivated shadows"
Add to negative: "multiple conflicting light sources, inconsistent shadows"
```

### Issue: Face Distortion
**Symptoms**: Asymmetrical features, merged faces, uncanny valley

**Solution**:
```
Add to prompt: "symmetrical face, clear facial features, natural proportions"
Add to negative: "face distortion, asymmetrical eyes, merged faces, uncanny"
```

### Issue: Color Banding
**Symptoms**: Visible bands in gradients, posterization

**Solution**:
```
Add to prompt: "smooth gradients, high color depth, subtle tonal transitions"
Add to negative: "color banding, posterization, dithering artifacts"
```

---

## Style-Specific Solutions

### Photorealistic
```json
{
  "style_fixes": [
    "subtle film grain for authenticity",
    "natural lens vignette",
    "slight chromatic aberration on edges"
  ],
  "avoid": [
    "too perfect, too clean",
    "uncanny valley smoothness"
  ]
}
```

### Anime/Illustration
```json
{
  "style_fixes": [
    "consistent line weight",
    "clear character outlines",
    "flat color regions where appropriate"
  ],
  "avoid": [
    "mixing realistic and anime elements",
    "inconsistent art style"
  ]
}
```

### Product Photography
```json
{
  "style_fixes": [
    "clean studio background",
    "controlled reflections",
    "accurate material rendering"
  ],
  "avoid": [
    "visible studio equipment",
    "unintended reflections"
  ]
}
```

---

## Person Generation Safety Guidelines

### Best Practices
1. **Use generic descriptors** for fictional characters
2. **Avoid specific real person names** unless historical/educational
3. **Don't generate** minors in inappropriate contexts
4. **Don't combine** real people with fictional scenarios

### Safe Patterns
```
✓ "A young professional woman in business attire"
✓ "An elderly man with a warm smile"
✓ "Historical figure [name] in period-accurate setting"

✗ "Generate [celebrity name] doing [specific action]"
✗ "Create a photo of [real person] that looks real"
```

### When to Use Identity Anchors
```json
{
  "character": {
    "type": "fictional",
    "identity_anchors": [
      "distinctive red hair",
      "scar above left eyebrow",
      "always wears silver necklace"
    ]
  }
}
```

---

## Debugging Workflow

### Step 1: Identify the Problem
- What specifically is wrong?
- Is it consistent across generations?
- Does it happen with simpler prompts?

### Step 2: Isolate the Cause
- Remove elements one by one
- Test with minimal prompt
- Check for conflicting style instructions

### Step 3: Apply Targeted Fix
- Add specific positive descriptors
- Add relevant negative constraints
- Adjust technical parameters

### Step 4: Verify & Iterate
- Generate 2-3 variations
- Compare results
- Fine-tune if needed

---

## Quick Fix Cheatsheet

| Problem | Quick Fix |
|---------|-----------|
| Plastic skin | Add "natural skin texture, pores" |
| Bad hands | Add "anatomically correct hands, five fingers" |
| Blurry text | Reduce to 3-4 words, add "legible, bold" |
| Weird lighting | Specify single light source direction |
| Flat colors | Add "subtle gradients, tonal variation" |
| Too busy | Add "clean composition, negative space" |
| Wrong style | Remove conflicting style keywords |
| Artifacts | Add "high quality, clean render" to negatives |
