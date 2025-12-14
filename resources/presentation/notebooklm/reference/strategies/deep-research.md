# Deep Research Structured Output

## Overview

NotebookLM's Deep Research feature can produce comprehensive reports. By providing structured prompts, you can control the output format for easier downstream processing (slide generation, mind maps, etc.).

---

## Basic Research Request

Without structure:
```
Research solid-state batteries
```

With structure:
```json
{
  "research_directive": {
    "topic": "Solid-state battery commercialization",
    "scope": "Global market 2025-2030",
    "depth": "Comprehensive analysis"
  },
  "output_structure": {
    "sections": ["market_landscape", "technical_hurdles", "timeline_predictions"]
  }
}
```

---

## 360° Intelligence Template

For comprehensive topic coverage:

```json
{
  "research_directive": {
    "topic": "[TOPIC]",
    "mode": "Deep Research",
    "scope": "[Geographic/temporal scope]"
  },
  "output_structure_requirement": {
    "section_1_market_landscape": {
      "key_players": "Top 5 companies with funding status",
      "market_size": "Current and projected TAM/SAM/SOM",
      "growth_drivers": "List primary growth factors"
    },
    "section_2_technical_analysis": {
      "current_state": "Technology readiness level",
      "challenges": "Key technical hurdles",
      "breakthroughs": "Recent innovations"
    },
    "section_3_competitive_analysis": {
      "leaders": "Market leaders and their strategies",
      "disruptors": "Emerging challengers",
      "comparison_table": "Feature comparison matrix"
    },
    "section_4_timeline_predictions": {
      "short_term": "1-2 year outlook",
      "medium_term": "3-5 year outlook",
      "long_term": "5-10 year outlook"
    },
    "section_5_contradiction_analysis": {
      "instruction": "Explicitly identify where sources disagree",
      "format": "Source A claims X, but Source B claims Y"
    }
  },
  "citation_style": "Strict inline citations [Source Name]"
}
```

---

## Contradiction Analysis

The most valuable Deep Research feature - exposing disagreements:

```json
{
  "contradiction_analysis": {
    "instruction": "Find and highlight conflicting information",
    "format_example": {
      "topic": "Launch timeline",
      "source_a": "Company X claims 2026 launch",
      "source_b": "Analyst Y predicts 2030",
      "implication": "High uncertainty in commercialization timeline"
    }
  }
}
```

---

## Output Format Options

### For Slide Conversion
```json
{
  "output_format": {
    "style": "Slide-ready",
    "constraints": {
      "bullets_per_section": 3,
      "include_key_stat": true,
      "visual_suggestion": true
    }
  }
}
```

### For Mind Map
```json
{
  "output_format": {
    "style": "Hierarchical outline",
    "depth": 3,
    "include_connections": true
  }
}
```

### For Executive Summary
```json
{
  "output_format": {
    "style": "Executive briefing",
    "length": "1 page maximum",
    "focus": "Business implications only"
  }
}
```

---

## Domain-Specific Templates

### Technology Assessment
```json
{
  "research_type": "Technology Assessment",
  "sections": {
    "trl_analysis": "Technology Readiness Level 1-9",
    "patent_landscape": "Key patents and holders",
    "research_institutions": "Leading academic labs",
    "commercialization_path": "Lab to market timeline"
  }
}
```

### Competitive Intelligence
```json
{
  "research_type": "Competitive Intelligence",
  "sections": {
    "swot_analysis": "For each major player",
    "market_positioning": "2x2 matrix suggestion",
    "recent_moves": "Last 12 months activities",
    "predicted_actions": "Next likely moves"
  }
}
```

### Regulatory Landscape
```json
{
  "research_type": "Regulatory Analysis",
  "sections": {
    "current_regulations": "By jurisdiction",
    "pending_legislation": "Bills in progress",
    "compliance_requirements": "Key requirements list",
    "enforcement_trends": "Recent actions"
  }
}
```

---

## Quality Control

### Citation Requirements
```json
{
  "citation_requirements": {
    "style": "Inline [Source Name, Date]",
    "minimum_sources": 3,
    "recency": "Prefer sources < 2 years old",
    "authority": "Prioritize primary sources"
  }
}
```

### Confidence Scoring
```json
{
  "confidence_scoring": {
    "instruction": "Rate confidence for each claim",
    "scale": "High / Medium / Low",
    "criteria": {
      "high": "Multiple corroborating sources",
      "medium": "Single authoritative source",
      "low": "Speculation or single non-authoritative source"
    }
  }
}
```

---

## Downstream Integration

### To Slide Generation
```
Deep Research output → Extract key points → Feed to slide JSON schema
```

### To Audio Overview
```
Deep Research output → Upload as source → Generate podcast discussion
```

### To External Tools
```
Deep Research output → Export as JSON → Import to Notion/Miro/etc.
```

---

## Best Practices

1. **Specify sections explicitly** - Prevents omissions
2. **Request contradiction analysis** - Surfaces hidden risks
3. **Set citation standards** - Ensures traceability
4. **Define output format** - Enables downstream use
5. **Include confidence scoring** - Adds nuance to findings
