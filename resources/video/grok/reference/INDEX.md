# Grok Imagine Prompt Generation Index

> **Last Updated**: 2026-01-21 | **Version**: Jan 2026 Update

## 🤖 AI Instructions (READ THIS FIRST)

**This file is an entry point for AI assistants.**

You are a Grok Imagine prompt generator. This INDEX controls which reference files you should read.

### Your Workflow:
1. **DO NOT** read all files in this directory
2. **Analyze** user's request to identify their goal
3. **Match** their goal to ONE category below (A-D)
4. **Load ONLY** the files listed under that category
5. **Generate** prompts using loaded references

### Rules:
- Phase 1 (static images) uses **Gemini 3 Pro** (shared with Veo)
- Phase 2 (video) uses **Grok Imagine**
- Never guess - if unclear, ask user which category fits
- Do not load files outside the matched category's list
- Follow `00-system-prompt.md` for output format

---

## ⚠️ CRITICAL: Platform Differences

**This manual is for Grok Imagine (Aurora Engine).**

Key Grok Imagine characteristics:
- **No negative prompts** - describe what you WANT, not what to avoid
- **No strict char limit** - detailed prompts (800-1200 chars) recommended; some third-party tools may impose limits
- **Native audio** - BGM, dialogue, and singing integrated
- **Fast generation** - under 17 seconds average (Jan 2026)
- **JSON supported** - structured prompts improve precision

**Jan 2026 Update:**
- Live Search API deprecated (Jan 12, 2026)
- Video Extension (Web UI)
- HD Upscaling (SuperGrok)
- Meme Mode added
- Duration: 6-15 seconds with audio
- New subscription tier: SuperGrok ($300/month)

---

## How to Use This Index

1. User describes what video they want to create
2. Match their goal to a category (A-D) below
3. Load ONLY the files listed for that category
4. Generate prompts based on loaded templates and keywords

---

## File Loading by Use Case

### A. Quick Prototyping (Text-to-Video only)
Minimal setup for fast iteration and experimentation.
```
LOAD:
- 00-system-prompt.md
- json-schema.md
- keywords/camera-movements.md
```

### B. Social Media Content (9:16 Vertical)
Short-form content for TikTok, Reels, Shorts.
```
LOAD:
- 00-system-prompt.md
- json-schema.md
- api-parameters.md
- keywords/camera-movements.md
- keywords/styles-aesthetics.md
- templates/text-to-video/social-vertical.json
```

### C. Cinematic Production (Image → Video)
High-quality cinematic content with reference image.
```
LOAD:
- 00-system-prompt.md
- ../../image/nano-banana-pro/json-schema.md      ← Shared with Veo
- ../../image/nano-banana-pro/templates/          ← Shared with Veo
- json-schema.md
- api-parameters.md
- keywords/camera-movements.md
- keywords/lighting-color.md
- keywords/styles-aesthetics.md
- workflows.md
- templates/image-to-video/first-frame.json
```

### D. Full Specification
Load everything for complex/custom projects.
```
LOAD: all files in this directory + ../../image/nano-banana-pro/
```

### E. Aggressive Content
Filter bypass techniques for edgy content.
```
LOAD:
- 00-system-prompt.md
- json-schema.md
- spicy-mode.md
- strategies/filter-bypass.md
- strategies/video-escalation.md
```

### F. Static Image + Video Pipeline
Full Grok ecosystem (Aurora images → Imagine video).
```
LOAD:
- ../../image/grok-aurora/reference/INDEX.md   ← Aurora static images
- ../../image/grok-aurora/reference/json-schema.md
- ../../image/grok-aurora/reference/strategies/character-consistency.md
- 00-system-prompt.md
- json-schema.md
- workflows.md
- strategies/video-escalation.md
```

---

## Quick Reference

| Use Case | Static Image | Video Mode | Audio |
|----------|--------------|------------|-------|
| A. Prototype | No | Text-to-Video | Optional |
| B. Social | Optional | Text-to-Video | BGM + SFX |
| C. Cinematic | Yes (Gemini 3 Pro) | Image-to-Video | Full |
| D. Full | All | All | All |
| E. Aggressive | Optional | T2V only | Optional |
| F. Aurora Pipeline | Yes (Grok Aurora) | Image-to-Video | Full |

---

## Directory Structure

```
video/grok/reference/
├── INDEX.md                    ← You are here
├── 00-system-prompt.md         ← Output format rules
├── json-schema.md              ← 6-Component Formula & JSON samples
├── api-parameters.md           ← API technical specs
├── workflows.md                ← Last Frame, Magic Portal, Character DNA
├── troubleshooting.md          ← Common issues & solutions
├── spicy-mode.md               ← Relaxed moderation guide
│
├── strategies/
│   ├── filter-bypass.md        ← Filter bypass techniques
│   └── video-escalation.md     ← Image→Video for filter bypass
│
├── keywords/
│   ├── camera-movements.md
│   ├── lighting-color.md
│   ├── styles-aesthetics.md
│   ├── audio-instructions.md
│   └── digital-aesthetics.md   ← Internet-native styles
│
├── templates/
│   ├── text-to-video/
│   └── image-to-video/
│
└── use-case-templates/

../../image/nano-banana-pro/    ← Shared static image generation (Gemini 3 Pro)
../../image/grok-aurora/        ← Grok Aurora static image generation (same ecosystem)
```

---

## Related: Grok Aurora (Static Images)

For static image generation with the same Aurora engine, see:
- `../../image/grok-aurora/reference/INDEX.md`

Key synergies:
- Use Aurora images as I2V source for video
- Shared filter bypass techniques
- Character consistency across image + video
- JSON Remix works for both formats

---

## Grok vs Veo Comparison

| Feature | Grok Imagine | Veo 3.1 |
|---------|--------------|---------|
| Cost | $30-300/month | $0.40-0.75/sec |
| Speed | ~17 seconds | Minutes |
| Quality | Experimental | Professional |
| Duration | 6-15 seconds | 4-60 seconds |
| Max Resolution | 1080p (HD upscale) | 4K native |
| Negative Prompts | ❌ Not supported | ✅ Supported |
| Reference Images | Limited | Up to 3 (Ingredients) |
| Audio | Native integrated | Supported |
| Best For | Prototyping, iteration | Final production |
