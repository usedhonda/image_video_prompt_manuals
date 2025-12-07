# Grok Aurora Static Image Generation Reference

## Overview

Grok Aurora is xAI's autoregressive image generation model. Unlike diffusion models, Aurora processes images as token sequences, enabling precise JSON-structured prompt control.

| Feature | Specification |
|---------|---------------|
| Architecture | Autoregressive MoE (Mixture-of-Experts) |
| Prompt Format | JSON-structured (native support) |
| Text Rendering | High accuracy (spell-correct) |
| Styles | Realistic, Anime, Illustration, Cinematic |
| Content Mode | Spicy Mode available (age-verified) |

---

## File Loading Order

### Essential (Always Load)
1. `00-system-prompt.md` - Role definition
2. `json-schema.md` - JSON structure and examples

### By Use Case

| Use Case | Load These Files |
|----------|------------------|
| Basic Image | `json-schema.md` |
| Photorealistic | `json-schema.md` + `keywords/cinematography.md` |
| Anime/Illustration | `json-schema.md` + `keywords/visual-details.md` |
| Character Consistency | `strategies/character-consistency.md` |
| Style Transfer | `strategies/json-remix.md` |
| Aggressive Content | `strategies/filter-bypass.md` |

---

## Quick Reference

### JSON Schema Core Objects

| Object | Purpose | Key Fields |
|--------|---------|------------|
| `shot` | Camera work | camera_depth, camera_view, camera_movement |
| `cinematography` | Lighting/texture | lighting[], texture, depth_of_field |
| `visual_details` | Subject/style | subjects[], interaction, style |
| `negative_prompt` | Exclude elements | String or array |
| `seed` | Reproducibility | Numeric value |

### Style Keywords

| Style | Keywords |
|-------|----------|
| Photorealistic | `photorealistic`, `hyper-realistic`, `DSLR`, `85mm lens` |
| Anime | `2d anime`, `cel-shaded`, `Studio Ghibli style` |
| Illustration | `oil painting`, `watercolor`, `comic`, `hand-drawn` |
| Cinematic | `cinematic`, `film grain`, `anamorphic lens` |

---

## Grok Aurora vs Grok Imagine (Video)

| Aspect | Aurora (Image) | Imagine (Video) |
|--------|----------------|-----------------|
| Output | Static image | 5-15 sec video |
| JSON Support | Native | Supported |
| Negative Prompt | Partial support | NOT supported |
| Seed Control | Full support | NOT supported |
| Spicy Mode | Available | Available (T2V only) |
| Filter Strictness | Medium | Lower (see video-escalation) |

---

## Related Resources

- **Video Generation**: `../../video/grok/reference/INDEX.md`
- **Video Escalation Technique**: `../../video/grok/reference/strategies/video-escalation.md`
