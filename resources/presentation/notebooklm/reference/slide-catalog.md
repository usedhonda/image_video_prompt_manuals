# Slide Type Catalog (18 Types)

## Overview

The Yoshifuji Method defines 18 slide archetypes. Select appropriate types based on content needs.

---

## Catalog Reference

| ID | Name (JP) | Name (EN) | Best For |
|----|-----------|-----------|----------|
| 01 | タイトル・タイポグラフィ | Scatter Title | Opening, awards |
| 02 | テキスト＋データ強調 | Asymmetric Split | Key metrics |
| 03 | カードグリッド | Card Grid | Features, team |
| 04 | 全画面グラフィック | Full Bleed Image | Hero shots |
| 05 | 写真＋リスト分割 | Photo + List | Details |
| 06 | ミニマル地図 | Minimal Map | Locations |
| 07 | 垂直タイムライン | Vertical Timeline | History, process |
| 08 | バブルチャート/ベン図 | Bubble/Venn | Relationships |
| 09 | 対話形式 | Chat Dialogue | Testimonials |
| 10 | 年表リスト | Year List | Milestones |
| 11 | ダークモード図解 | Dark Network | Concepts |
| 12 | 3ステップ・カラム | 3-Step Column | Process |
| 13 | ロゴグリッド | Logo Grid | Partners |
| 14 | 2カラム（課題vs解決） | Problem/Solution | Before/After |
| 15 | 中央配置（ダークモード） | Cinematic Center | Impact |
| 16 | 数式・フロー図 | Formula/Flow | Technical |
| 17 | 矢印ステップ | Arrow Steps | Workflow |
| 18 | チャート | Scientific Chart | Data |

---

## Detailed Definitions

### 01. Scatter Title (タイトル・タイポグラフィ)

```json
{
  "id": "scatter_title",
  "name_jp": "タイトル・タイポグラフィ",
  "description": "Scattered layout with award badges and keywords placed like stamps",
  "elements": ["award_badges", "keywords", "central_title"],
  "layout": {
    "title_position": "center",
    "badge_placement": "random_scatter",
    "keywords_style": "stamp_like"
  },
  "best_for": "Opening slides, achievement highlights"
}
```

---

### 02. Asymmetric Split (テキスト＋データ強調)

```json
{
  "id": "asymmetric_split",
  "name_jp": "テキスト＋データ強調",
  "description": "Narrative text on left, giant metric number on right with thin divider",
  "elements": ["text_block", "giant_metric", "vertical_line"],
  "layout": {
    "split_ratio": "40:60",
    "metric_font_size": "120pt+",
    "metric_color": "primary_black",
    "divider_weight": "1px"
  },
  "best_for": "Key statistics, impact numbers"
}
```

---

### 03. Card Grid (カードグリッド)

```json
{
  "id": "card_grid",
  "name_jp": "カードグリッド",
  "description": "Tight grid of cards with minimal gaps, web-like aesthetic",
  "elements": ["cards", "icons", "labels"],
  "layout": {
    "columns": "3-4",
    "gap": "8px",
    "card_style": "flat_minimal"
  },
  "best_for": "Feature lists, team members, product grid"
}
```

---

### 04. Full Bleed Image (全画面グラフィック)

```json
{
  "id": "full_bleed",
  "name_jp": "全画面グラフィック",
  "description": "Edge-to-edge architectural photo with desaturated treatment",
  "elements": ["hero_image", "overlay_text"],
  "layout": {
    "image_treatment": "desaturated",
    "text_position": "bottom_left",
    "padding": "0"
  },
  "best_for": "Hero moments, section dividers"
}
```

---

### 05. Photo + List (写真＋リスト分割)

```json
{
  "id": "photo_list_split",
  "name_jp": "写真＋リスト分割",
  "description": "50:50 split with photo left, detailed list right",
  "elements": ["photo", "bullet_list", "subheading"],
  "layout": {
    "split_ratio": "50:50",
    "list_style": "numbered_or_bulleted",
    "photo_position": "left"
  },
  "best_for": "Detailed explanations, case studies"
}
```

---

### 06. Minimal Map (ミニマル地図)

```json
{
  "id": "minimal_map",
  "name_jp": "ミニマル地図",
  "description": "Silhouette map on light gray, ultra-thin callout lines",
  "elements": ["silhouette_map", "callout_lines", "location_labels"],
  "layout": {
    "map_style": "silhouette_white",
    "background": "light_gray",
    "line_weight": "0.5px"
  },
  "best_for": "Office locations, market presence"
}
```

---

### 07. Vertical Timeline (垂直タイムライン)

```json
{
  "id": "vertical_timeline",
  "name_jp": "垂直タイムライン",
  "description": "Central vertical line with events branching left and right",
  "elements": ["timeline_line", "event_nodes", "date_labels"],
  "layout": {
    "line_position": "center",
    "branch_alternating": true,
    "node_style": "circle_or_square"
  },
  "best_for": "Company history, project phases"
}
```

---

### 08. Bubble/Venn (バブルチャート/ベン図)

```json
{
  "id": "bubble_venn",
  "name_jp": "バブルチャート/ベン図",
  "description": "Wireframe circles with transparency overlap",
  "elements": ["circles", "labels", "overlap_zone"],
  "layout": {
    "circle_style": "wireframe",
    "fill_opacity": 0.1,
    "stroke_weight": "1px"
  },
  "best_for": "Concept relationships, market positioning"
}
```

---

### 09. Chat Dialogue (対話形式)

```json
{
  "id": "chat_dialogue",
  "name_jp": "対話形式",
  "description": "Text blocks styled as chat conversation",
  "elements": ["chat_bubbles", "avatars", "timestamps"],
  "layout": {
    "bubble_alignment": "alternating",
    "bubble_style": "rounded_corners",
    "show_avatars": true
  },
  "best_for": "Testimonials, Q&A, user stories"
}
```

---

### 10. Year List (年表リスト)

```json
{
  "id": "year_list",
  "name_jp": "年表リスト",
  "description": "Large year numbers with contrasting description text",
  "elements": ["year_numbers", "descriptions", "dividers"],
  "layout": {
    "year_font_size": "72pt",
    "description_font_size": "14pt",
    "contrast_ratio": "high"
  },
  "best_for": "Milestones, historical achievements"
}
```

---

### 11. Dark Network (ダークモード図解)

```json
{
  "id": "dark_network",
  "name_jp": "ダークモード図解",
  "description": "Constellation-style network on black background",
  "elements": ["nodes", "connection_lines", "labels"],
  "layout": {
    "background": "#000000",
    "node_style": "glowing_dots",
    "line_style": "thin_gradient"
  },
  "background_override": "#000000",
  "text_override": "#FFFFFF",
  "best_for": "Concept maps, ecosystem diagrams"
}
```

---

### 12. 3-Step Column (3ステップ・カラム)

```json
{
  "id": "three_step_column",
  "name_jp": "3ステップ・カラム",
  "description": "Three columns with large step numbers as pillars",
  "elements": ["step_numbers", "titles", "descriptions"],
  "layout": {
    "columns": 3,
    "number_style": "giant_bold",
    "number_position": "top"
  },
  "best_for": "Process steps, methodology"
}
```

---

### 13. Logo Grid (ロゴグリッド)

```json
{
  "id": "logo_grid",
  "name_jp": "ロゴグリッド",
  "description": "Monochrome logo collection in uniform grid",
  "elements": ["logos", "company_names"],
  "layout": {
    "logo_treatment": "monochrome",
    "grid_columns": "4-6",
    "uniform_sizing": true
  },
  "best_for": "Partners, clients, integrations"
}
```

---

### 14. Problem/Solution (2カラム：課題vs解決)

```json
{
  "id": "problem_solution",
  "name_jp": "2カラム（課題vs解決）",
  "description": "Bold vertical line separating problem (left) and solution (right)",
  "elements": ["problem_block", "solution_block", "thick_divider"],
  "layout": {
    "divider_weight": "4px",
    "left_tone": "negative",
    "right_tone": "positive"
  },
  "best_for": "Before/after, challenge resolution"
}
```

---

### 15. Cinematic Center (中央配置・ダークモード)

```json
{
  "id": "cinematic_center",
  "name_jp": "中央配置（ダークモード）",
  "description": "Small centered video thumbnail or key visual on black with tagline",
  "elements": ["key_visual", "tagline", "subtle_cta"],
  "layout": {
    "visual_size": "40% canvas",
    "position": "center",
    "tagline_style": "english_emotional"
  },
  "background_override": "#000000",
  "text_override": "#FFFFFF",
  "best_for": "Impact moments, brand statements"
}
```

---

### 16. Formula/Flow (数式・フロー図)

```json
{
  "id": "formula_flow",
  "name_jp": "数式・フロー図",
  "description": "Serif typography for formal expressions, flowchart style",
  "elements": ["formula_text", "flow_arrows", "annotations"],
  "layout": {
    "font_family": "serif",
    "arrow_style": "thin_precise",
    "annotation_position": "inline"
  },
  "best_for": "Technical explanations, algorithms"
}
```

---

### 17. Arrow Steps (矢印ステップ)

```json
{
  "id": "arrow_steps",
  "name_jp": "矢印ステップ",
  "description": "High-contrast arrows connecting sequential steps",
  "elements": ["step_boxes", "arrow_connectors", "labels"],
  "layout": {
    "arrow_style": "bold_chevron",
    "direction": "left_to_right",
    "contrast": "high"
  },
  "best_for": "Workflow, pipeline, process"
}
```

---

### 18. Scientific Chart (チャート)

```json
{
  "id": "scientific_chart",
  "name_jp": "チャート",
  "description": "Measurement-style graphs with precise annotations",
  "elements": ["chart", "axis_labels", "data_points", "legend"],
  "layout": {
    "chart_style": "clean_minimal",
    "grid_lines": "subtle",
    "annotation_style": "scientific"
  },
  "best_for": "Data visualization, research findings"
}
```

---

## Quick Selection Guide

| Content Type | Recommended Slides |
|--------------|-------------------|
| Opening | scatter_title, cinematic_center |
| Data | asymmetric_split, scientific_chart |
| Process | three_step_column, arrow_steps, vertical_timeline |
| Comparison | problem_solution, bubble_venn |
| Visual | full_bleed, photo_list_split |
| Technical | formula_flow, dark_network |
| Social Proof | logo_grid, chat_dialogue |
