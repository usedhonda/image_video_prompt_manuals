# Quality-Boosting Techniques

Advanced techniques for higher quality output.

---

## Ingredients Method (Nano Banana → Veo)

Multi-angle character generation for video consistency.

| Step | Action | Output |
|------|--------|--------|
| 1 | Generate character sheet (3 angles: Front, Side, 45°) | Reference images |
| 2 | Feed "Front" view into Veo image-to-video | First frame |
| 3 | Prompt: "Camera orbits subject" | Veo infers 3D volume |

**Schema for Step 1:**
```json
{
  "composition_hack": "Hard Split Screen",
  "layout": {
    "type": "horizontal_split",
    "ratio": "33:34:33"
  },
  "panels": ["front view", "45° angle", "side profile"],
  "subject": {
    "identity": "...",
    "persistent_features": ["..."]
  }
}
```

---

## Search-to-Render Loop

Use grounding for technical accuracy.

| Step | Action |
|------|--------|
| 1 | Define grounding_query with specific search |
| 2 | Request rendering based on search results |

**Example:**
```json
{
  "logic_chain": {
    "grounding_query": "1967 Mustang engine wiring diagram"
  },
  "prompt": "Photorealistic engine with glowing wires highlighting spark plug connections",
  "accuracy": "Match exact layout from search results"
}
```

**Use Cases:**
- Historical accuracy (period-correct clothing, architecture)
- Technical diagrams (machinery, circuits)
- Brand accuracy (real product details)

---

## Physics-Aware Rendering

Use logic_chain to plan physics before rendering.

| Material | physics_engine Value |
|----------|---------------------|
| Glass | "Light refracts, caustics on surface below" |
| Liquid | "SSS in milk, surface tension at edges" |
| Metal | "Sharp specular highlights, environment reflection" |
| Fabric | "Soft diffuse, subtle subsurface on thin areas" |
| Food | "SSS in fruit flesh, moisture on surface" |

**Example:**
```json
{
  "logic_chain": {
    "physics_engine": "Honey has high viscosity, SSS with amber color, caustics from backlight",
    "spatial_blocking": "Honey dipper foreground, jar midground, warm bokeh background"
  }
}
```

---

## Text Legibility Optimization

| Priority | When to Use | Settings |
|----------|-------------|----------|
| High | Hero text, titles | Bold sans-serif, high contrast BG |
| Medium | Labels, signs | Clear font, readable size |
| Low | Background dressing | Can be partially obscured |

**Best Practices:**
- Keep under 6 words
- Use `text_module.integration_method` for natural embedding
- Specify exact font when possible

---

## Quick Reference

| Technique | Best For | Key Schema Field |
|-----------|----------|------------------|
| Ingredients Method | Character video | Split View + veo_optimization |
| Search-to-Render | Real-world accuracy | logic_chain.grounding_query |
| Physics-Aware | Food, product, liquid | logic_chain.physics_engine |
| Text Optimization | Readable text in image | text_module |
