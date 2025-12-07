# Visual Details Keywords

## Subjects Array Structure

### Single Subject
```json
"visual_details": {
  "subjects": [
    {
      "id": "main",
      "type": "woman",
      "age": "20s",
      "features": "long silver hair, blue eyes, freckles",
      "attire": "cyberpunk jacket, neon accents",
      "pose": "standing confidently",
      "expression": "determined smirk"
    }
  ]
}
```

### Multiple Subjects
```json
"visual_details": {
  "subjects": [
    { "id": "char1", "type": "woman", "attire": "red dress", "position": "foreground left" },
    { "id": "char2", "type": "man", "attire": "tuxedo", "position": "foreground right" },
    { "id": "char3", "type": "child", "attire": "school uniform", "position": "background center" }
  ],
  "interaction": "char1 and char2 dancing while char3 watches from doorway"
}
```

---

## Style Keywords

### Photorealism Spectrum

| Keyword | Description |
|---------|-------------|
| `photorealistic` | Indistinguishable from photo |
| `hyper-realistic` | Enhanced reality detail |
| `cinematic` | Movie still quality |
| `editorial` | Magazine photography |
| `documentary` | Raw, authentic feel |
| `fashion photography` | Glamour, styled |
| `portrait photography` | Face-focused |
| `street photography` | Candid, urban |

### Illustration Spectrum

| Keyword | Description |
|---------|-------------|
| `2d anime` | Traditional anime style |
| `cel-shaded` | Flat colors, distinct lines |
| `hand-drawn` | Visible artistic strokes |
| `digital painting` | Painterly digital art |
| `concept art` | Pre-production style |
| `comic book` | Bold lines, halftone |
| `manga` | Black and white, screentone |
| `watercolor` | Soft, transparent washes |
| `oil painting` | Thick, textured strokes |

### Reference Styles

| Keyword | Characteristics |
|---------|----------------|
| `Studio Ghibli` | Soft, pastoral, detailed backgrounds |
| `Makoto Shinkai` | Dramatic lighting, photo-real backgrounds |
| `Ufotable` | Dynamic action, particle effects |
| `MAPPA` | Dark, stylized, expressive |
| `Pixar` | 3D, expressive, bright |
| `Artgerm` | Digital beauty, clean lines |
| `Greg Rutkowski` | Fantasy, detailed, painterly |
| `Wes Anderson` | Symmetric, pastel, quirky |

---

## Attire & Clothing Keywords

### Casual
- `streetwear`, `hoodie`, `jeans`, `sneakers`
- `athletic wear`, `yoga pants`, `sports bra`
- `loungewear`, `oversized sweater`

### Formal
- `business suit`, `evening gown`, `tuxedo`
- `cocktail dress`, `blazer`, `tie`

### Fantasy
- `armor`, `chainmail`, `leather armor`
- `wizard robes`, `cloak`, `hood`
- `royal regalia`, `crown`, `cape`

### Sci-Fi
- `exosuit`, `power armor`, `cyberpunk gear`
- `spacesuit`, `holographic accessories`
- `neon accents`, `LED trim`

### Minimal (Spicy Mode)
- `bikini`, `swimwear`, `lingerie`
- `athletic wear`, `sports bra and shorts`
- `sheer fabric`, `mesh`, `lace`
- See `strategies/filter-bypass.md` for advanced techniques

---

## Expression Keywords

### Positive
- `smiling`, `laughing`, `joyful`, `excited`
- `serene`, `content`, `peaceful`, `relaxed`
- `confident`, `determined`, `proud`

### Negative
- `angry`, `furious`, `enraged`
- `sad`, `melancholy`, `tearful`
- `fearful`, `terrified`, `anxious`
- `disgusted`, `contemptuous`

### Subtle
- `micro-expression` - Barely perceptible emotion
- `neutral` - No strong emotion
- `pensive` - Lost in thought
- `wistful` - Longing, nostalgic

---

## Pose Keywords

### Standing
- `power pose`, `hero stance`, `contrapposto`
- `hands on hips`, `arms crossed`, `relaxed stance`

### Sitting
- `cross-legged`, `lounging`, `perched`
- `formal seated`, `casual lean`

### Action
- `running`, `jumping`, `fighting`
- `dancing`, `reaching`, `falling`
- `dynamic pose`, `action freeze-frame`

### Reclining
- `lying down`, `supine`, `prone`
- `side-lying`, `curled up`

---

## Interaction Keywords

Describe relationships between multiple subjects:

```json
"interaction": "char1 is protecting char2 from unseen threat"
"interaction": "char1 and char2 sharing intimate whisper"
"interaction": "char1 teaching char2 to play piano"
"interaction": "all subjects running toward camera"
```

### Relationship Types
- **Romantic**: `embracing`, `kissing`, `holding hands`
- **Conflict**: `fighting`, `confronting`, `facing off`
- **Collaborative**: `working together`, `helping`, `teaching`
- **Social**: `conversing`, `celebrating`, `mourning`

---

## Quality Enhancement

### Skin Texture (Avoid Uncanny Valley)
```json
"skin_texture": ["visible pores", "subtle asymmetry", "natural blemishes"]
```

### Realism Markers
- `catch light in eyes`
- `subsurface scattering on skin`
- `fine hair detail`
- `fabric texture and wrinkles`
- `environmental reflections`

### Imperfection Keywords
- `slightly windswept hair`
- `smudged lipstick`
- `natural skin texture`
- `visible freckles`
- `micro-expressions`
