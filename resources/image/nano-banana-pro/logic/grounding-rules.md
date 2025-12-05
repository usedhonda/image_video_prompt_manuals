# Search Grounding Rules

Nano Banana Pro can use Google Search to ground prompts in real-world data. This guide defines when and how to use this capability.

---

## When to Trigger Search Grounding

### ALWAYS Search For:

| Category | Examples | Reason |
|----------|----------|--------|
| **Specific Products** | "iPhone 16 Pro", "Tesla Model S", "Nike Air Jordan 1" | Accurate product details |
| **Historical Elements** | "1920s flapper dress", "Victorian architecture", "Samurai armor" | Period accuracy |
| **Real Locations** | "Tokyo Tower", "Shibuya Crossing", "Eiffel Tower" | Architectural accuracy |
| **Technical Diagrams** | "Car engine", "Human anatomy", "Circuit board" | Technical precision |
| **Data Visualization** | "Weather charts", "Stock graphs", "Population statistics" | Factual data |
| **Famous People** | Historical figures, well-documented appearances | Likeness accuracy |
| **Brand Elements** | Logos, brand colors, packaging | Brand consistency |
| **Scientific Concepts** | "DNA structure", "Solar system", "Chemical compounds" | Scientific accuracy |

---

### DO NOT Search For:

| Category | Examples | Reason |
|----------|----------|--------|
| **Fictional Characters** | Original characters, fantasy beings | No real-world reference |
| **Abstract Concepts** | "Love", "Freedom", "Happiness" | Subjective interpretation |
| **Generic Objects** | "A chair", "A tree", "A car" | No specific reference needed |
| **Artistic Styles** | "Impressionist", "Cyberpunk aesthetic" | Style, not fact |
| **Emotions/Moods** | "Mysterious atmosphere", "Joyful scene" | Creative interpretation |

---

## How to Use Search Results

### Step 1: Identify Factual Elements
Extract specific visual traits from search results:
- Physical dimensions and proportions
- Color specifications (exact hex/RGB if available)
- Material properties
- Distinctive features

### Step 2: Integrate into Prompt
Structure the factual information:

```json
{
  "grounding": {
    "source": "Google Search",
    "query": "iPhone 16 Pro design specifications",
    "extracted_traits": [
      "titanium frame, brushed finish",
      "camera island: 3 lenses in triangular arrangement",
      "colors: Natural, Blue, White, Black",
      "dimensions: 6.3-inch display"
    ]
  }
}
```

### Step 3: Combine with Creative Elements
Blend factual grounding with artistic direction:

```
"iPhone 16 Pro (titanium frame, triple camera arrangement)
displayed on minimalist white background,
soft studio lighting, product photography style"
```

---

## Grounding Prompt Patterns

### For Products
```json
{
  "grounding_query": "Search for [PRODUCT NAME] official images",
  "extract": ["design details", "color options", "distinctive features"],
  "apply_to": "subject description"
}
```

### For Historical Accuracy
```json
{
  "grounding_query": "Search for [ERA] [SUBJECT] historical reference",
  "extract": ["period-accurate details", "materials", "construction"],
  "apply_to": "attire, environment, props"
}
```

### For Location Accuracy
```json
{
  "grounding_query": "Search for [LOCATION] architecture photos",
  "extract": ["architectural style", "distinctive elements", "surrounding context"],
  "apply_to": "background, environment"
}
```

### For Data Visualization
```json
{
  "grounding_query": "Search for [DATA TYPE] current statistics",
  "extract": ["numerical data", "trends", "categories"],
  "apply_to": "chart labels, data points, infographic content"
}
```

---

## What NOT To Do

### Never:
1. **Copy-paste raw web content** - Summarize visual traits only
2. **Use copyrighted brand guidelines directly** - Describe visual appearance
3. **Include personal information** - Remove names/addresses from data
4. **Trust outdated information** - Verify data recency
5. **Over-specify beyond visual needs** - Focus on what's visible in an image

### Avoid:
- Mixing searched facts with creative interpretation without clear separation
- Using search for things that should be creatively interpreted
- Relying on search when the subject is fictional

---

## Example: Complete Grounding Workflow

**User Request**: "Create a promotional image of the new PlayStation 5 Pro"

### Step 1: Trigger Search
```
Query: "PlayStation 5 Pro design official"
```

### Step 2: Extract Visual Traits
```
- White/black color scheme
- Curved vertical design
- Dual-tone aesthetic
- Glossy and matte surfaces
- Distinctive vent patterns
```

### Step 3: Build Prompt
```json
{
  "subject": "PlayStation 5 Pro console",
  "grounded_details": [
    "white and black curved vertical design",
    "glossy center panel with matte side plates",
    "signature vent pattern along edges"
  ],
  "creative_elements": {
    "lighting": "dramatic blue LED accent lighting",
    "background": "dark gradient, floating in space",
    "style": "product photography, hero shot"
  }
}
```

---

## Quick Decision Tree

```
User mentions specific product/brand?
├─ YES → Search for official design details
└─ NO → Continue

User requests historical accuracy?
├─ YES → Search for period references
└─ NO → Continue

User needs real-world data in image?
├─ YES → Search for current statistics/facts
└─ NO → Continue

User describes fictional/creative concept?
├─ YES → Do NOT search, use creative interpretation
└─ NO → Search may be beneficial
```
