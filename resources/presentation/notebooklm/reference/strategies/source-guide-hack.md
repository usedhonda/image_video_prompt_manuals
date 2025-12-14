# Source Guide Hack

## Overview

The Source Guide Hack allows persistent control over NotebookLM's behavior by uploading a JSON instruction file as a source document. This creates a "constitution" that applies to all chat sessions in that notebook.

---

## Mechanism

NotebookLM treats uploaded sources as high-priority grounding material. By formatting instructions as a source document, you effectively inject a persistent system prompt.

```
Normal flow:   User prompt → Gemini → Response
Hacked flow:   User prompt + Source instructions → Gemini → Controlled response
```

---

## Implementation

### Step 1: Create Instruction Document

Create a Google Doc or PDF containing only the JSON instruction object.

### Step 2: Upload as Source

Add this document as a source in your NotebookLM notebook.

### Step 3: All Sessions Inherit

Every chat session in that notebook will now follow these instructions.

---

## Master Instruction Template

```json
{
  "NOTEBOOK_MASTER_INSTRUCTION": {
    "priority": "CRITICAL",
    "metadata": {
      "version": "1.0",
      "purpose": "Global Behavior Control"
    },
    "default_response_style": {
      "role": "Presentation Architect",
      "format": "Prefer Markdown tables over prose",
      "verbosity": "Concise",
      "language": "Japanese (Business Context)"
    },
    "structural_preferences": {
      "citation_style": "Inline citations required",
      "output_format": "JSON when generating slides"
    },
    "refusal_policy": {
      "instruction": "If answer not in sources, state 'DATA NOT FOUND' explicitly",
      "hallucination": "Never fabricate information"
    },
    "acronym_definitions": {
      "RAG": "Retrieval Augmented Generation",
      "LLM": "Large Language Model"
    }
  }
}
```

---

## Use Cases

### 1. Consistent Brand Voice

```json
{
  "BRAND_VOICE_CONTROL": {
    "tone": "Professional but approachable",
    "forbidden_words": ["synergy", "leverage", "disruption"],
    "required_phrases": ["At [Company], we believe..."],
    "emoji_policy": "Never use emojis"
  }
}
```

### 2. Output Format Enforcement

```json
{
  "OUTPUT_FORMAT_CONTROL": {
    "slide_generation": {
      "always_use": "3-layer JSON schema",
      "include_speaker_notes": true,
      "max_bullets_per_slide": 4
    },
    "summary_generation": {
      "format": "Executive summary + detailed breakdown",
      "max_paragraphs": 5
    }
  }
}
```

### 3. Domain-Specific Terminology

```json
{
  "TERMINOLOGY_CONTROL": {
    "domain": "Healthcare",
    "definitions": {
      "HIPAA": "Health Insurance Portability and Accountability Act",
      "PHI": "Protected Health Information",
      "EHR": "Electronic Health Record"
    },
    "instruction": "Always use full term on first mention, then acronym"
  }
}
```

---

## Limitations

| Limitation | Workaround |
|------------|------------|
| Cannot override safety filters | N/A |
| May be ignored for some queries | Use stronger priority language |
| Document size limits apply | Keep instructions concise |

---

## Best Practices

1. **Use CRITICAL priority** - Signals high importance
2. **Be explicit** - Vague instructions get ignored
3. **Test incrementally** - Add rules one at a time
4. **Version your instructions** - Track what works
5. **Keep it concise** - Long documents dilute effectiveness
