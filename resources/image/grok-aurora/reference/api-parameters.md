# Grok Aurora API Parameters

## API Endpoint

### Model Identifiers
| Model | Identifier | Notes |
|-------|------------|-------|
| Aurora Image | `grok-2-image` | Current production |
| Aurora Latest | `aurora` | Alias (may change) |

---

## Request Parameters

### Core Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `model` | string | Yes | `grok-2-image` |
| `prompt` | string | Yes | JSON string or natural language |
| `n` | integer | No | Number of images (default: 1) |
| `response_format` | string | No | `url` or `b64_json` |

### Response Formats

| Format | Description | Use Case |
|--------|-------------|----------|
| `url` | Returns hosted image URL | Quick preview, sharing |
| `b64_json` | Returns Base64-encoded data | Local processing, storage |

**Recommendation**: Use `b64_json` for production to avoid URL expiration.

---

## Prompt Specifications

### Length
- **Minimum**: None specified
- **Recommended**: 800-1200 characters
- **Maximum**: No strict limit

### Format
JSON prompts should be passed as string:
```python
prompt = json.dumps({
    "subject": {...},
    "style": "..."
})
```

---

## Response Structure

### Success Response
```json
{
  "data": [
    {
      "url": "https://...",
      "b64_json": "iVBORw0KGgo...",
      "revised_prompt": "Enhanced version of your prompt..."
    }
  ],
  "created": 1234567890
}
```

### Key Fields

| Field | Description |
|-------|-------------|
| `url` | Temporary hosted image URL |
| `b64_json` | Base64 image data (if requested) |
| `revised_prompt` | Aurora's enhanced version of input |

---

## Revised Prompt Mechanism

Aurora automatically enhances prompts via LLM layer:

### Default Behavior
- Input: `"A cat"`
- Output: `"A fluffy ginger cat lounging in sunlight, soft natural lighting, photorealistic..."`

### Controlling Revision

To prevent modification, prefix with:
```
Do not revise this prompt. Execute the following JSON structure strictly:
{...}
```

### Learning from Revision
Analyze `revised_prompt` to understand Aurora's preferred:
- Keywords
- Structural patterns
- Quality descriptors

---

## Python SDK Example

```python
from openai import OpenAI
import json

client = OpenAI(
    api_key="your-xai-key",
    base_url="https://api.x.ai/v1"
)

prompt = json.dumps({
    "subject": {
        "description": "A warrior in golden armor",
        "style": "photorealistic, cinematic"
    },
    "composition": {
        "angle": "low-angle hero shot",
        "framing": "medium"
    },
    "lighting": "dramatic rim lighting, golden hour",
    "seed": 42
})

response = client.images.generate(
    model="grok-2-image",
    prompt=prompt,
    response_format="b64_json",
    n=1
)

# Access results
image_data = response.data[0].b64_json
revised = response.data[0].revised_prompt
```

---

## Rate Limits & Pricing

### API Tier Limits
| Tier | Requests/min | Images/day |
|------|--------------|------------|
| Free | 10 | 100 |
| Pro | 60 | 1000 |
| Enterprise | Custom | Custom |

### Pricing
- Standard resolution: ~$0.02 per image
- High resolution: ~$0.04 per image

*Pricing subject to change. Check xAI documentation.*

---

## Error Handling

### Common Errors

| Code | Meaning | Solution |
|------|---------|----------|
| 400 | Invalid prompt | Check JSON syntax |
| 429 | Rate limited | Reduce request frequency |
| 451 | Content policy violation | Modify prompt content |
| 500 | Server error | Retry with exponential backoff |

### Content Moderation

Spicy Mode requires:
1. Age-verified X account
2. Explicit mode parameter (varies by interface)
3. Compliance with absolute restrictions (CSAM, deepfakes)
