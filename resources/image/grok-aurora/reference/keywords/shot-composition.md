# Shot Composition Keywords

## Camera Depth (Subject Distance)

| Keyword | Description | Use Case |
|---------|-------------|----------|
| `Extreme Close-up` | Face detail, eyes only | Emotion, texture detail |
| `Close-up` | Face and shoulders | Portrait, expression |
| `Medium Close-up` | Chest up | Interview, dialogue |
| `Medium Shot` | Waist up | Conversation, action |
| `Cowboy Shot` | Mid-thigh up | Western style, holster visible |
| `Medium Full Shot` | Knees up | Character with context |
| `Full Shot` | Entire body | Character introduction |
| `Wide Shot` | Body with environment | Scene establishment |
| `Extreme Wide Shot` | Vast landscape with subject | Epic scale, isolation |

---

## Camera View (Angle)

| Keyword | Description | Psychological Effect |
|---------|-------------|---------------------|
| `Eye-level` | Camera at subject's eye height | Neutral, relatable |
| `Low-angle` | Camera below subject | Power, dominance, heroic |
| `High-angle` | Camera above subject | Vulnerability, weakness |
| `Dutch Tilt` | Tilted horizon | Unease, tension, dynamic |
| `Overhead` | Directly above | God's view, strategy |
| `Bird's-eye` | Very high aerial | Epic scope, patterns |
| `Worm's-eye` | Ground level looking up | Extreme power, monumentality |
| `Over-the-shoulder` | Behind character | POV, dialogue |
| `Point-of-view (POV)` | Character's exact view | Immersion |

---

## Camera Movement (Motion Suggestion)

Static images can suggest motion via blur, framing, or composition.

| Keyword | Effect | Best For |
|---------|--------|----------|
| `Static` | Frozen moment | Portraits, still life |
| `Pan` | Horizontal sweep | Landscapes, panoramas |
| `Tilt` | Vertical sweep | Tall subjects, architecture |
| `Dolly` | Forward/backward motion | Approaching, revealing |
| `Dolly Zoom` | Background distortion | Vertigo effect, unease |
| `Tracking Shot` | Following subject | Movement, pursuit |
| `Crane` | Sweeping vertical | Establishing, grandeur |
| `Handheld` | Slight shake | Documentary, realism |
| `Steadicam` | Smooth movement | Professional, cinematic |

---

## Motion Level

| Keyword | Description | Visual Cues |
|---------|-------------|-------------|
| `Frozen` | Zero motion | Crisp, sharp |
| `Low` | Subtle movement | Slight blur on edges |
| `Medium` | Visible motion | Motion blur trails |
| `High` | Dynamic action | Significant blur, energy lines |
| `Extreme` | Speed/impact | Heavy blur, impact effects |

---

## Framing Types

| Keyword | Description |
|---------|-------------|
| `Tight framing` | Subject fills frame, claustrophobic |
| `Loose framing` | Subject with breathing room |
| `Balanced` | Subject centered, symmetrical |
| `Rule of thirds` | Subject at intersection points |
| `Golden ratio` | Spiral composition |
| `Leading lines` | Lines directing to subject |
| `Frame within frame` | Doorway, window framing |

---

## Combined Examples

### Heroic Portrait
```json
"shot": {
  "camera_depth": "Medium Shot",
  "camera_view": "Low-angle",
  "camera_movement": "Static",
  "motion_level": "Frozen"
}
```

### Action Chase
```json
"shot": {
  "camera_depth": "Wide Shot",
  "camera_view": "Dutch Tilt",
  "camera_movement": "Tracking Shot",
  "motion_level": "High"
}
```

### Intimate Emotion
```json
"shot": {
  "camera_depth": "Extreme Close-up",
  "camera_view": "Eye-level",
  "camera_movement": "Static",
  "motion_level": "Frozen"
}
```

### Epic Landscape
```json
"shot": {
  "camera_depth": "Extreme Wide Shot",
  "camera_view": "Bird's-eye",
  "camera_movement": "Crane",
  "motion_level": "Low"
}
```
