# Grok Imagine Prompt Generation Index

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
- **380 character max** - use all available characters
- **Native audio** - BGM, dialogue, and singing integrated
- **Fast generation** - under 30 seconds typically
- **JSON supported** - structured prompts improve precision

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
- phase2-grok/json-schema.md
- phase2-grok/keywords/camera-movements.md
```

### B. Social Media Content (9:16 Vertical)
Short-form content for TikTok, Reels, Shorts.
```
LOAD:
- 00-system-prompt.md
- phase2-grok/json-schema.md
- phase2-grok/api-parameters.md
- phase2-grok/keywords/camera-movements.md
- phase2-grok/keywords/styles-aesthetics.md
- templates/text-to-video/social-vertical.json
```

### C. Cinematic Production (Image → Video)
High-quality cinematic content with reference image.
```
LOAD:
- 00-system-prompt.md
- ../common/phase1-nano-banana/json-schema.md      ← Shared with Veo
- ../common/phase1-nano-banana/templates/          ← Shared with Veo
- phase2-grok/json-schema.md
- phase2-grok/api-parameters.md
- phase2-grok/keywords/camera-movements.md
- phase2-grok/keywords/lighting-color.md
- phase2-grok/keywords/styles-aesthetics.md
- templates/image-to-video/first-frame.json
```

### D. Full Specification
Load everything for complex/custom projects.
```
LOAD: all files in this directory + ../common/phase1-nano-banana/
```

---

## Quick Reference

| Use Case | Static Image | Video Mode | Audio |
|----------|--------------|------------|-------|
| A. Prototype | No | Text-to-Video | Optional |
| B. Social | Optional | Text-to-Video | BGM + SFX |
| C. Cinematic | Yes (Gemini 3 Pro) | Image-to-Video | Full |
| D. Full | All | All | All |

---

## Directory Structure

```
grok/reference/
├── INDEX.md                    ← You are here
├── 00-system-prompt.md         ← Output format rules
│
├── phase2-grok/                ← Grok Imagine video generation
│   ├── json-schema.md
│   ├── api-parameters.md
│   └── keywords/
│       ├── camera-movements.md
│       ├── lighting-color.md
│       ├── styles-aesthetics.md
│       └── audio-instructions.md
│
├── templates/
│   ├── text-to-video/
│   │   ├── basic.json
│   │   └── cinematic.json
│   └── image-to-video/
│       └── first-frame.json
│
└── use-case-templates/         ← Ready-to-use examples
    ├── social-media/
    ├── product/
    └── storytelling/

../common/phase1-nano-banana/   ← Shared static image generation (Gemini 3 Pro)
```

---

## Grok vs Veo Comparison

| Feature | Grok Imagine | Veo 3.1 |
|---------|--------------|---------|
| Cost | $30/month (500/day) | $0.40-0.75/sec |
| Speed | ~30 seconds | Minutes |
| Quality | Experimental | Professional |
| Duration | 5-15 seconds | 4-8 seconds |
| Negative Prompts | ❌ Not supported | ✅ Supported |
| Reference Images | Limited | Up to 3 (Ingredients) |
| Audio | Native integrated | Supported |
| Best For | Prototyping, iteration | Final production |
