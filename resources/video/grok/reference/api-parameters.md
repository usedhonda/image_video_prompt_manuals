# Grok Imagine API Parameters

## API Overview

Grok Imagine provides video generation through REST API endpoints. This document covers the available parameters and their usage.

> ⚠️ **DEPRECATION NOTICE (Jan 12, 2026)**: Live Search API has been deprecated. Use native web search capabilities instead.

---

## Performance

- **Average Generation Time**: Under 17 seconds (T2V)
- **Quality Modes**: 720p (fast) / 1080p (quality)
- **Audio Generation**: Native integrated (6-15 seconds with audio)

---

## Endpoints

### Text-to-Video
```
POST /api/v1/video/generate
```

### Image-to-Video
```
POST /grok-imagine/image-to-video
```

### Status Check
```
GET /api/v1/video/status?taskId=YOUR_TASK_ID
```

---

## Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `prompt` | string | Yes | Text description of desired video (800-1200 chars recommended) |
| `duration` | string | No | Video length: `"6"` to `"15"` seconds (audio-enabled) |
| `quality` | string | No | Resolution: `"720p"` or `"1080p"` |
| `aspectRatio` | string | No | Frame ratio (see below) |
| `imageUrl` | string | No | Source image URL for Image-to-Video |
| `mode` | string | No | Creative mode (see below) |
| `extend` | boolean | No | Enable video extension (Web UI only) |
| `upscale_hd` | boolean | No | Enable HD upscaling (Web UI only) |

---

## Aspect Ratios

| Value | Use Case |
|-------|----------|
| `"16:9"` | Widescreen (YouTube, desktop) |
| `"9:16"` | Vertical (TikTok, Reels, Stories) |
| `"1:1"` | Square (Instagram feed) |
| `"4:3"` | Classic TV ratio |
| `"3:4"` | Portrait |

---

## Creative Modes

| Mode | Description |
|------|-------------|
| `normal` | Polished, safe results (default) |
| `fun` | Playful effects added |
| `spicy` | Adult/provocative content (restricted) |

**Note**: Spicy mode may be downgraded to Normal when using external image URLs.

---

## Example Request (cURL)

```bash
curl -X POST https://api.grokimagine.ai/v1/video/generate \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "Epic sunrise over mountains, camera fly-over shot with dramatic light rays, cinematic color grading",
    "duration": "5",
    "quality": "720p",
    "aspectRatio": "16:9"
  }'
```

---

## Example Request (Python)

```python
import requests

API_KEY = "YOUR_API_KEY"
headers = {
    "Authorization": f"Bearer {API_KEY}",
    "Content-Type": "application/json"
}

data = {
    "prompt": "Slow zoom-in on product with elegant lighting",
    "duration": "5",
    "quality": "1080p",
    "aspectRatio": "16:9"
}

response = requests.post(
    "https://api.grokimagine.ai/v1/video/generate",
    headers=headers,
    json=data
)

result = response.json()
print(result)
```

---

## Response Format

### Initial Response
```json
{
  "success": true,
  "data": {
    "taskId": "ee603959-debb-48d1-98c4-a6d1c717eba6",
    "status": "pending",
    "creditsUsed": 10
  }
}
```

### Status Values

| Status | Description |
|--------|-------------|
| `pending` | Queued for processing |
| `processing` | Generation in progress |
| `completed` | Video ready |
| `failed` | Generation failed |

---

## Image-to-Video Example (Python)

```python
import requests

API_KEY = "YOUR_API_KEY"
headers = {"Authorization": f"Bearer {API_KEY}"}

data = {
    "image_urls": ["https://example.com/product.jpg"],
    "prompt": "Slow zoom-in with text: 'New Arrival'",
    "mode": "normal",
    "aspect_ratio": "9:16"
}

response = requests.post(
    "https://api.kie.ai/grok-imagine/image-to-video",
    headers=headers,
    json=data
)

result = response.json()
print(result)
```

---

## Subscription Tiers (Jan 2026)

| Tier | Price | Daily Limit | Features |
|------|-------|-------------|----------|
| **Free** | $0 | 10/day | Basic T2V, 720p |
| **Heavy** | $30/month | 100/day | T2V + I2V, 1080p |
| **SuperGrok** | $300/month | 500/day | All features, priority queue, HD upscaling |

## Rate Limits & Credits

- API calls require authentication via Bearer token
- Credit consumption varies by quality and duration
- Higher quality (1080p) uses more credits
- SuperGrok subscribers get priority queue access
- Check provider documentation for specific limits

---

## Error Codes

| Code | Description |
|------|-------------|
| 400 | Invalid request parameters |
| 401 | Authentication failed |
| 429 | Rate limit exceeded |
| 500 | Server error |

---

## Best Practices

1. **Start with 720p** for testing, upgrade to 1080p for final
2. **Use 6-second duration** for quick iterations (minimum with audio)
3. **Poll status endpoint** every 2-3 seconds until complete
4. **Handle async nature** - video generation averages <17 seconds
5. **Cache taskIds** to avoid duplicate requests
6. **Use HD upscaling** for final delivery (SuperGrok only)

---

## Video Extension (Web UI Only)

Extend existing videos by generating continuation clips:

```json
{
  "source_video_id": "existing-task-id",
  "extend": true,
  "prompt": "Continue the scene with..."
}
```

**Note**: Currently available in Web UI only, not in API.

---

## HD Upscaling (Web UI Only)

Enhance video quality post-generation:

```json
{
  "source_video_id": "existing-task-id",
  "upscale_hd": true
}
```

**Note**: Requires SuperGrok subscription. Web UI only.
