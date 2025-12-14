# Audio Overview Control

## Overview

NotebookLM's Audio Overview feature generates podcast-style discussions from your sources. While you can't control the output via JSON directly, structured text in the "Customize" box significantly influences the generated audio.

---

## Default Behavior

Without customization, Audio Overview produces:
- Two friendly hosts
- Casual, accessible tone
- Generic opener ("Welcome back to our deep dive...")
- Standard AI pleasantries

---

## Persona Injection

Paste structured instructions into the Customize text box to override defaults.

### Dual Expert Debate Format

```json
{
  "host_1_persona": {
    "name": "Skeptic_Sarah",
    "role": "Devil's advocate / Critical analyst",
    "tone": "Skeptical, questioning, demands evidence",
    "catchphrases": ["But where's the data for that?", "That sounds like marketing speak."]
  },
  "host_2_persona": {
    "name": "Visionary_Vince",
    "role": "Technology optimist / Futurist",
    "tone": "Excited, speculative, big-picture thinking",
    "behavior": "Frequently interrupts with 'Imagine if...' scenarios"
  },
  "conversation_rules": {
    "structure": "Debate format. Sarah challenges every point Vince makes.",
    "pacing": "Fast, overlapping dialogue",
    "complexity_level": "PhD / Expert level - do not simplify concepts",
    "forbidden_phrases": ["Let's dive in", "In summary", "It's important to note"]
  },
  "target_audience": "Industry veterans only. No beginner explanations."
}
```

---

## Tone Presets

### Academic Deep Dive
```json
{
  "tone": "Academic, methodical",
  "hosts": "Two researchers reviewing a paper",
  "style": "Cite specific sections, debate methodology",
  "audience": "Graduate students and researchers"
}
```

### Casual Tech Podcast
```json
{
  "tone": "Casual, enthusiastic",
  "hosts": "Two tech friends catching up",
  "style": "Use analogies, pop culture references",
  "audience": "General tech-curious listeners"
}
```

### Executive Briefing
```json
{
  "tone": "Concise, strategic",
  "hosts": "Senior analyst briefing a CEO",
  "style": "Focus on business implications, skip technical details",
  "audience": "C-suite executives"
}
```

### Storytelling Mode
```json
{
  "tone": "Narrative, engaging",
  "hosts": "Documentary narrator style",
  "style": "Build tension, use dramatic pauses",
  "audience": "General audience seeking entertainment"
}
```

---

## Forbidden Phrases

Override generic AI phrases by explicitly forbidding them:

```json
{
  "forbidden_phrases": [
    "Let's dive in",
    "Without further ado",
    "In summary",
    "It's important to note",
    "At the end of the day",
    "Moving forward",
    "That being said"
  ]
}
```

---

## Pacing Control

| Pacing | Description | Use Case |
|--------|-------------|----------|
| Rapid | Quick exchanges, interruptions | Debate, news |
| Measured | Thoughtful pauses | Academic |
| Dynamic | Varies with content | Storytelling |
| Slow | Deliberate, explanatory | Education |

---

## Language & Complexity

```json
{
  "complexity_level": "Expert",
  "jargon_policy": "Use technical terms without explanation",
  "analogy_policy": "Avoid oversimplified analogies",
  "assumption": "Listeners have 10+ years domain experience"
}
```

---

## Structural Templates

### Opening Override
```json
{
  "opening": {
    "skip_pleasantries": true,
    "start_with": "A challenging question about the material",
    "hook_style": "Provocative statement"
  }
}
```

### Closing Override
```json
{
  "closing": {
    "skip_summary": true,
    "end_with": "Open question for listener reflection",
    "call_to_action": "None - let content speak"
  }
}
```

---

## Limitations

| Limitation | Notes |
|------------|-------|
| No direct audio parameter control | Text-based influence only |
| Persona may blend with defaults | Use strong, specific language |
| Length not controllable | Determined by source content |
| Voice selection not available | Fixed AI voices |

---

## Best Practices

1. **Be specific** - Vague personas get averaged out
2. **Use character names** - Helps maintain distinct voices
3. **Define catchphrases** - Creates recognizable patterns
4. **Forbid clichés** - Explicitly list unwanted phrases
5. **Set audience level** - Prevents unwanted simplification
