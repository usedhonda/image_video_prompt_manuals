# Grok Imagine JSON Schema

## Overview

Grok Imagine (Aurora Engine) accepts both natural language prompts and structured JSON for video generation. JSON provides more precise control over complex scenes. The Aurora engine understands physics-like simulations and responds to detailed cinematographic instructions.

---

## The 6-Component Formula

The most robust prompt structure recommended by the community:

```
Prompt = [Subject] + [Action] + [Camera] + [Lighting] + [Environment] + [Audio]
```

| Component | Description | Best Practice |
|-----------|-------------|---------------|
| **Subject** | Who/what is in frame | Use layered adjectives: "crimson-scaled, battle-scarred elder dragon" not just "dragon" |
| **Action/Motion** | How subject moves | Include physics: "struggling against turbulence, wings slicing through wind" |
| **Camera Movement** | Viewpoint control | Use "Camera" as subject: "Camera pans left" to avoid ambiguity |
| **Visual Style** | Quality, medium, aesthetic | Equipment names work: "Arri Alexa", "35mm film", "VHS" |
| **Environment/Setting** | Place, time, duration | Light conditions (Golden Hour), weather, explicit duration ("10 seconds") |
| **Audio Direction** | Sound instructions | Use brackets: `[Audio: ambient sounds only]` for better recognition |

---

## API JSON Request Format

### Text-to-Video (T2V) Basic Structure

```json
{
  "model": "grok-imagine-v1",
  "prompt": "Cinematic shot: A cybernetic samurai walking through neon rain. 4k, highly detailed.",
  "aspect_ratio": "16:9",
  "mode": "normal",
  "duration": 10,
  "webhook_url": "https://api.yourdomain.com/callbacks/video"
}
```

**Parameters:**
- `model`: `grok-imagine-v1` or latest `grok-2-video`
- `prompt`: Video description, max 1000 chars recommended
- `aspect_ratio`: `"16:9"` (cinematic), `"9:16"` (mobile), `"1:1"` (square)
- `mode`: `"normal"` (balanced), `"fun"` (cartoon/extreme), `"spicy"` (relaxed moderation)
- `duration`: 5-15 seconds

### Image-to-Video (I2V) Basic Structure

```json
{
  "model": "grok-imagine-v1",
  "image_urls": ["https://s3.yourbucket.com/character_ref.jpg"],
  "prompt": "Camera slowly zooms in. The character smiles gently and blinks. Wind blows hair.",
  "mode": "normal",
  "aspect_ratio": "16:9"
}
```

**Note**: `mode: "spicy"` is often not supported or forced to `"normal"` in I2V mode.

---

## Structured Prompt JSON Template

For maximum control, pass structured instructions:

```json
{
  "task": "generate_video_prompt",
  "subject": {
    "type": "woman",
    "age": "20s",
    "clothing": "red dress",
    "appearance": "cybernetic eye"
  },
  "environment": {
    "location": "space station",
    "lighting": "strobe lights",
    "atmosphere": "emergency alert"
  },
  "camera": {
    "type": "handheld",
    "movement": "running forward",
    "focus": "shallow depth of field"
  },
  "audio": {
    "sfx": "alarm klaxon",
    "dialogue": "We need to leave now!"
  },
  "technical": {
    "style": "cinematic",
    "aspect_ratio": "16:9",
    "duration": "10s"
  }
}
```

---

## Practical JSON Samples (Copy & Paste Ready)

### Scenario A: Cinematic Action (Car Chase)

**Goal:** Movie-like intensity and speed.

```json
{
  "model": "grok-imagine-v1",
  "aspect_ratio": "16:9",
  "mode": "normal",
  "duration": 10,
  "prompt": "Subject: A matte black muscle car drifting around a sharp mountain corner. Action: Tires smoking heavily, debris flying, car suspension compressing. Camera: Low angle FPV drone shot chasing the car, fast motion blur, shaking slightly from speed. Lighting: High contrast sunset, lens flare hitting the windshield. Audio: V8 engine roaring at high RPM, tire screeching sounds, wind noise."
}
```

### Scenario B: Product Promotion (Luxury Watch)

**Goal:** Elegant light reflections, slow camera movement.

```json
{
  "model": "grok-imagine-v1",
  "aspect_ratio": "16:9",
  "mode": "normal",
  "duration": 8,
  "prompt": "Subject: A luxury gold wristwatch resting on black velvet. Action: The watch hands are ticking smoothly. Light glints off the sapphire glass. Camera: Macro lens, extreme close-up, slow smooth orbital movement around the watch face. Rack focus from the strap to the dial. Lighting: Studio 3-point lighting, rim light highlighting the gold edges, sparkling caustics. Audio: Satisfying mechanical ticking sound, soft ambient luxury synth swell."
}
```

### Scenario C: Atmospheric Horror

**Goal:** Unsettling lighting and environmental sound.

```json
{
  "model": "grok-imagine-v1",
  "aspect_ratio": "9:16",
  "mode": "spicy",
  "duration": 12,
  "prompt": "Subject: An abandoned hospital hallway. Action: A shadow quickly darts across the end of the hall. The overhead lights flicker violently and then explode. Camera: Handheld camera movement, breathing shake, slow cautious walk forward. Lighting: Strobe lighting effect, deep shadows (chiaroscuro), volumetric dust. Audio: Electrical buzzing, light bulb shattering, distant heavy footsteps, low frequency dread drone."
}
```

### Scenario D: Character Portrait (I2V)

**Goal:** Animate a still image naturally.

```json
{
  "model": "grok-imagine-v1",
  "image_urls": ["https://your-storage.com/character.jpg"],
  "mode": "normal",
  "prompt": "Action: The character turns their head slowly to look at the camera and smiles warmly. Hair flows gently in a breeze. Eyes blink naturally. Camera: Static shot with shallow depth of field (bokeh). Lighting: Preserve original lighting. Audio: Soft wind sound, distant birds chirping."
}
```

### Scenario E: Cyberpunk Cityscape (Full 6-Component)

```json
{
  "model": "grok-imagine-v1",
  "aspect_ratio": "16:9",
  "mode": "normal",
  "duration": 10,
  "prompt": "Subject: A bustling neo-Tokyo cityscape under heavy acidic rain. Action: Sleek flying vehicles weave rapidly between holographic billboards, leaving trails of blue ion thrusters. Steam rises from street vents. Camera: Wide aerial drone shot, slowly tracking forward and tilting down towards street level. Style: Blade Runner 2049 aesthetic, high contrast, neon noir, wet pavement reflections, volumetric fog, 8k resolution. Audio: Heavy rain ambience, distant police sirens, deep synth-bass hum of engines. Time: Nighttime, blue hour."
}
```

---

## Multi-Scene with Shot Switch

Use `Shot Switch.` to create cuts between scenes:

```json
{
  "prompt": "Wide establishing shot of mountain landscape. Shot Switch. Close-up of hiker's boots on rocky trail. Shot Switch. POV looking up at mountain peak."
}
```

**Important**: Set lens mode to "unfixed" (free camera) when using Shot Switch.

---

## The "Negative Prompt Paradox"

Grok does NOT support negative prompts. Writing "No music" or "Don't show hands" often causes those elements to appear (Pink Elephant Effect).

### Solutions:

1. **Positive Rephrasing:**
   - ❌ "No music" → ✅ "Silence, ambient sounds only", "Muted atmosphere"
   - ❌ "No glasses" → ✅ "Clear face, uncovered eyes"
   - ❌ "Not blurry" → ✅ "Sharp focus, high fidelity, crystal clear"

2. **Specific Audio Override:**
   - Use `"[insert] sounds only"` (e.g., "Gym sounds only") to suppress BGM

3. **Avoid List (Limited Effect):**
   - `[Avoid: text, watermark, blur]` at prompt end may help but is not native

---

## Key Constraints

| Parameter | Constraint |
|-----------|------------|
| Max prompt length | ~1000 characters (380 for basic, more for structured) |
| Negative prompts | NOT supported - use positive rephrasing |
| Style mixing | Avoid - commit to ONE primary style |
| Duration sweet spot | 5-6 seconds most stable |
| Camera movements | ONE primary movement per cut |
