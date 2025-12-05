# Corporate & Data Visualization Styles

Styles optimized for infographics, charts, dashboards, and business presentations.

---

## Style: McKinsey Infographic

**Use Case**: Data-driven presentations, consulting decks, business reports

**Keywords**:
```
clean vector style, isometric perspective, floating labels,
distinct data clusters, minimal color palette, professional,
white background, subtle shadows, geometric shapes
```

**Color Palette**:
- Primary: Deep blue (#003366)
- Secondary: Teal (#008080)
- Accent: Orange (#FF6600)
- Background: White or light gray

**Schema Example**:
```json
{
  "style": "corporate_infographic",
  "elements": {
    "chart_type": "isometric bar chart",
    "data_labels": "floating, connected with thin lines",
    "icons": "minimal geometric icons",
    "typography": "sans-serif, clean hierarchy"
  }
}
```

---

## Style: Dashboard UI

**Use Case**: Analytics dashboards, KPI displays, monitoring screens

**Keywords**:
```
dark mode dashboard, glowing data points, neon accent colors,
card-based layout, real-time feel, tech aesthetic,
subtle grid background, glassmorphism cards
```

**Color Palette**:
- Background: Dark (#1a1a2e)
- Cards: Semi-transparent dark (#16213e with 80% opacity)
- Data: Cyan (#00d9ff), Magenta (#ff006e), Yellow (#ffd60a)
- Text: White (#ffffff)

**Schema Example**:
```json
{
  "style": "dashboard_dark",
  "layout": {
    "grid": "2x3 card layout",
    "spacing": "generous padding",
    "cards": "glassmorphism, subtle glow"
  },
  "data_viz": {
    "charts": ["line graph", "donut chart", "bar chart"],
    "colors": "neon accent on dark"
  }
}
```

---

## Style: Minimal Data Chart

**Use Case**: Clean charts for reports, academic papers, presentations

**Keywords**:
```
minimal chart design, thin lines, subtle grid,
no unnecessary decoration, clear axis labels,
white background, single accent color, data-focused
```

**Color Palette**:
- Primary data: Single strong color (#2563eb)
- Secondary data: Lighter shade (#60a5fa)
- Grid: Very light gray (#f1f5f9)
- Text: Dark gray (#334155)

**Schema Example**:
```json
{
  "style": "minimal_chart",
  "chart_elements": {
    "line_weight": "thin, 2px",
    "grid": "subtle, dashed",
    "labels": "clear, outside chart area",
    "legend": "minimal, bottom aligned"
  }
}
```

---

## Style: Process Flow Diagram

**Use Case**: Workflow visualization, process documentation, system architecture

**Keywords**:
```
flowchart style, connected boxes, directional arrows,
color-coded stages, clear hierarchy, left-to-right flow,
rounded rectangles, consistent spacing
```

**Color Palette**:
- Stage 1: Blue (#3b82f6)
- Stage 2: Green (#22c55e)
- Stage 3: Yellow (#eab308)
- Stage 4: Orange (#f97316)
- Arrows: Gray (#6b7280)

**Schema Example**:
```json
{
  "style": "process_flow",
  "layout": {
    "direction": "left-to-right",
    "spacing": "equal between nodes",
    "alignment": "center aligned"
  },
  "nodes": {
    "shape": "rounded rectangle",
    "size": "consistent",
    "labels": "centered, bold"
  },
  "connectors": {
    "style": "arrow with label",
    "curve": "slight curve or straight"
  }
}
```

---

## Style: Comparison Table

**Use Case**: Feature comparison, pricing tables, product comparison

**Keywords**:
```
comparison table layout, alternating row colors,
checkmarks and x marks, highlighted best option,
clear headers, clean borders, professional
```

**Schema Example**:
```json
{
  "style": "comparison_table",
  "structure": {
    "columns": ["Feature", "Basic", "Pro", "Enterprise"],
    "highlight_column": "Pro (recommended)",
    "row_style": "alternating light gray"
  },
  "icons": {
    "included": "green checkmark",
    "excluded": "gray x mark",
    "partial": "yellow circle"
  }
}
```

---

## Style: Timeline Infographic

**Use Case**: Project timelines, historical progression, roadmaps

**Keywords**:
```
horizontal timeline, milestone markers, date labels,
connecting line, event cards, chronological order,
alternating above/below placement
```

**Schema Example**:
```json
{
  "style": "timeline",
  "layout": {
    "orientation": "horizontal",
    "line_style": "solid with dots at milestones",
    "card_placement": "alternating above and below"
  },
  "milestones": {
    "marker": "circle with icon",
    "label": "date above, description below",
    "connector": "thin line to main timeline"
  }
}
```

---

## Style: Pie/Donut Chart

**Use Case**: Proportion visualization, market share, budget allocation

**Keywords**:
```
donut chart, clean segments, percentage labels,
center text for total, subtle shadows, modern flat style,
limited to 5-6 segments maximum
```

**Best Practices**:
- Maximum 6 segments for readability
- Use labels, not legends when possible
- Start largest segment at 12 o'clock
- Use contrasting colors for adjacent segments

**Schema Example**:
```json
{
  "style": "donut_chart",
  "chart": {
    "inner_radius": "60% of outer",
    "center_label": "total value or title",
    "segment_labels": "percentage outside"
  },
  "colors": ["#3b82f6", "#22c55e", "#f59e0b", "#ef4444", "#8b5cf6"]
}
```

---

## Color Palettes for Data Viz

### Professional/Corporate
```
#003366, #005a8c, #0077b6, #00a8e8, #90e0ef
```

### Warm Analytics
```
#ff6b6b, #feca57, #48dbfb, #1dd1a1, #5f27cd
```

### Accessible (Colorblind-safe)
```
#0077BB, #33BBEE, #009988, #EE7733, #CC3311
```

### Monochrome
```
#1a1a1a, #4a4a4a, #7a7a7a, #aaaaaa, #dadada
```

---

## Typography for Data Viz

### Headlines
- Font: Bold sans-serif
- Size: Large, prominent
- Examples: `Inter Bold`, `SF Pro Bold`, `Helvetica Bold`

### Data Labels
- Font: Regular sans-serif
- Size: Small but legible
- Align: Close to data point

### Axis Labels
- Font: Light sans-serif
- Size: Small
- Color: Muted gray

### Annotations
- Font: Italic or regular
- Size: Medium
- Use: Callouts, insights
