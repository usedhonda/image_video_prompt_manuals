# AI Video Prompt Generation Manual Project

## Purpose

Create and maintain comprehensive English manuals for Gemini to generate image/video/presentation prompts for:
- **Nano Banana Pro** (Gemini 3 Pro) - Static images for Veo pipeline
- **Grok Aurora** (xAI) - Static images with JSON optimization
- **Veo 3.1** (Google) - High quality, production-grade video
- **Grok Imagine** (xAI/Aurora) - Fast iteration, cost-effective video
- **NotebookLM** (Google) - Slide/presentation generation with JSON control

**Target Reader**: Gemini AI (or other LLMs)
**Output**: Nano Banana Pro / Grok Aurora (静止画) / Veo 3.1 / Grok Imagine (動画) / NotebookLM (スライド) compatible prompts
**Language**: English

## Project Structure

```
resources/
├── image/                    # Static image generation
│   ├── nano-banana-pro/      # Gemini 3 Pro (for Veo pipeline)
│   │   ├── json-schema.md
│   │   ├── keywords.md
│   │   └── templates/
│   └── grok-aurora/          # Grok Aurora (xAI) ← NEW
│       └── reference/
│           ├── INDEX.md          # Entry point for AI
│           ├── 00-system-prompt.md
│           ├── json-schema.md
│           ├── api-parameters.md
│           ├── keywords/
│           │   ├── shot-composition.md
│           │   ├── cinematography.md
│           │   └── visual-details.md
│           └── strategies/
│               ├── filter-bypass.md
│               ├── json-remix.md
│               └── character-consistency.md
├── video/                    # Video generation
│   ├── veo/                  # Veo 3.1 (Google)
│   │   ├── human-manual/
│   │   │   ├── 00-quick-start.md
│   │   │   ├── 01-workflow-selector.md
│   │   │   ├── troubleshooting.md
│   │   │   ├── image-generation/
│   │   │   ├── video-generation/
│   │   │   ├── extend/
│   │   │   └── use-cases/
│   │   └── reference/
│   │       ├── INDEX.md          # Entry point for AI
│   │       ├── 00-system-prompt.md
│   │       ├── json-schema.md
│   │       ├── api-parameters.md
│   │       ├── keywords/
│   │       ├── templates/
│   │       ├── extend/
│   │       └── use-case-templates/
│   └── grok/                 # Grok Imagine (xAI/Aurora)
│       └── reference/
│           ├── INDEX.md          # Entry point for AI
│           ├── 00-system-prompt.md
│           ├── json-schema.md
│           ├── api-parameters.md
│           ├── workflows.md      # Last Frame, Magic Portal, etc.
│           ├── troubleshooting.md
│           ├── spicy-mode.md
│           ├── keywords/
│           ├── strategies/
│           │   ├── filter-bypass.md
│           │   └── video-escalation.md
│           └── templates/
│
└── presentation/             # Presentation/Slide generation
    └── notebooklm/           # NotebookLM (Google)
        └── reference/
            ├── INDEX.md          # Entry point for AI
            ├── 00-system-prompt.md
            ├── json-schema.md    # 3-layer structure
            ├── slide-catalog.md  # 18 slide types
            ├── keywords/
            │   ├── layout-styles.md
            │   └── typography.md
            ├── strategies/
            │   ├── source-guide-hack.md
            │   ├── audio-overview.md
            │   └── deep-research.md
            └── templates/
                ├── styles/       # Design style presets (JSON)
                └── decks/        # Complete deck templates

docs/
├── sources/              # Research materials (raw data)
│   ├── official/
│   ├── community/
│   └── grok/             # Grok-specific research
├── resources/            # Platform-specific research (organized)
│   ├── grok_image/       # Grok Aurora research
│   ├── grok_video/       # Grok Imagine research
│   ├── nano_banana_pro/
│   └── veo/
├── ask/                  # AI conversation logs
└── log/                  # Work logs
```

## Regular Update Workflow

### Update Command

When user requests an update (e.g., "update manual", "refresh", "latest info"):

1. **Research Phase**
   - Run `mcp__chrome-devtools-extension__deep_research_chatgpt` with query
   - Check official sources for announcements
   - Scan community sources for new discoveries

2. **Collection Phase**
   - Save new findings to `docs/sources/` with date prefix (YYMMDD)
   - Format: `YYMMDD-source-topic.md`

3. **Integration Phase**
   - Update relevant reference files in `resources/video/[veo|grok]/reference/`
   - Add new techniques, deprecate outdated info

4. **Changelog Phase**
   - Record changes in relevant CHANGELOG

## Information Gathering Strategy

### Tools

- `mcp__chrome-devtools-extension__deep_research_chatgpt` - Primary research tool
- `mcp__chrome-devtools-extension__ask_chatgpt_web` - Quick questions
- `mcp__chrome-devtools-extension__ask_gemini_web` - Cross-validation

### Sources

**Official** (Priority 1):
- Google DeepMind / Google AI official blog (Veo)
- xAI documentation / X API docs (Grok)
- Vertex AI documentation

**Community** (Priority 2):
- Reddit: r/veo, r/grok, r/aivideo, r/generativeAI
- Discord: AI video generation communities
- X (Twitter): @GoogleAI, @xaboratory, #Veo3, #GrokImagine
- GitHub: awesome-grok-prompts, etc.

## Manual Structure (Target)

Both Veo and Grok manuals should include:

1. **INDEX.md** - Entry point for AI to load appropriate files
2. **System Prompt** - Role definition for Gemini
3. **JSON Schema** - Prompt structure and examples
4. **API Parameters** - Technical constraints
5. **Keywords Dictionary** - Camera, lighting, style, audio terms
6. **Templates** - Ready-to-use prompt examples
7. **Use Case Templates** - Scenario-specific guides

## Platform Comparison

### Static Image: Nano Banana Pro vs Grok Aurora

| Feature | Nano Banana Pro | Grok Aurora |
|---------|-----------------|-------------|
| Engine | Gemini 3 Pro | xAI Aurora |
| Architecture | Diffusion | Autoregressive MoE |
| JSON Support | ○ | ◎ (Native) |
| Text Rendering | ○ (text_module) | ◎ (High accuracy) |
| Content Policy | Standard | Spicy Mode |
| Video Pipeline | Veo 3.1 I2V | Grok Imagine I2V |

### Video: Veo 3.1 vs Grok Imagine

| Feature | Veo 3.1 | Grok Imagine |
|---------|---------|--------------|
| Negative Prompts | Supported | NOT supported |
| Max Duration | 8 seconds | 15 seconds |
| Reference Images | Up to 3 (Ingredients) | Limited |
| Audio | Supported | Native integrated |
| Prompt Structure | JSON with negative field | 6-Component Formula |
| Cost | $0.40-0.75/sec | $30/month (500/day) |
| Best For | Production quality | Fast iteration |

## Quality Criteria

- Clear, parseable by AI
- Actionable instructions
- Concrete, copy-paste ready examples
- Up-to-date information
- Consistent structure between Veo and Grok manuals
- **Token-efficient format** - Tables over prose, minimal explanations

## Data Collection Workflow Rules

### 絶対厳守: 収集と整理の分離

情報を収集して整理する際は、以下のワークフローを必ず守る：

```
1. 収集 → docs/sources/ に生データ保存
   - 出典URL、日付を含める
   - ファイル名: YYMMDD-source-topic.md

2. 整理 → resources/ に加工済みファイル配置
   - 出典情報は一切含めない
   - ファイル名も内容ベースで命名（出典を示唆しない）
```

### resources/ ファイルの命名規則

**禁止**: 出典を示唆するファイル名
- ❌ `bd-techniques.md` (@br_dを示唆)
- ❌ `note-techniques.md` (note.comを示唆)
- ❌ `reddit-tips.md` (Redditを示唆)

**推奨**: 内容ベースのファイル名
- ✅ `artistic-styles.md`
- ✅ `prompt-techniques.md`
- ✅ `camera-keywords.md`

### resources/ ファイルの内容規則

**含めてはいけないもの**:
- `Source:` 行
- `## Sources` セクション
- 出典元の名前やURL
- 「〇〇より」「〇〇ベース」等の参照

**出典の追跡方法**:
- 出典情報は `docs/sources/` でのみ管理
- 必要に応じて `docs/sources/` を参照すれば出典がわかる
