# AI Image & Video Prompt Generation Manual

画像・動画生成AI（Nano Banana Pro / Veo 3.1 / Grok Imagine）のためのプロンプトマニュアル。GeminiなどのAIにリファレンスを読み込ませることで、最適なプロンプトを生成させることが目的。

## Purpose

**Target Reader**: Gemini AI (or other LLMs)
**Output**: Nano Banana Pro (静止画) / Veo 3.1 / Grok Imagine (動画) compatible prompts
**Language**: English (prompts) / Japanese (documentation)

---

## resources/ Structure

```
resources/
├── image/                    # 静止画生成
│   ├── nano-banana-pro/      # Gemini 3 Pro
│   └── grok-aurora/          # Grok Aurora（xAI）← NEW
└── video/                    # 動画生成
    ├── veo/                  # Veo 3.1（高品質・プロ向け）
    │   ├── human-manual/
    │   └── reference/
    └── grok/                 # Grok Imagine（高速・コスト重視）
        └── reference/
```

---

## Veo vs Grok: Which to Use?

| 項目 | Veo 3.1 | Grok Imagine |
|------|---------|--------------|
| **価格** | $0.40-0.75/秒 | $30/月（500本/日） |
| **品質** | プロフェッショナル | 実験・プロトタイプ向け |
| **動画長** | 4-8秒 | 5-15秒 |
| **生成速度** | 数分 | 30秒以下 |
| **ネガティブプロンプト** | 対応 | 非対応 |
| **参照画像** | 最大3枚（Ingredients） | 限定的 |
| **オーディオ** | 対応 | ネイティブ統合 |
| **最適用途** | 最終制作物 | 高速イテレーション |

**推奨:**
- **プロダクション品質** → Veo 3.1
- **実験・プロトタイプ・大量生成** → Grok Imagine
- **静止画生成（Gemini）** → Nano Banana Pro (Gemini 3 Pro)
- **静止画生成（Grok）** → Grok Aurora（JSON構造化、Spicy Mode）

---

## Image Generation: Nano Banana Pro (`resources/image/nano-banana-pro/`)

Gemini 3 Proによる静止画生成。VeoとGrok両方の入力画像として共通使用。

### 特徴

- **推論エンジン搭載** - 生成前に物理法則を計画（logic_chain）
- **JSON構造化プロンプト** - 直接パラメータ注入
- **14枚画像ミキシング** - 複数参照画像の合成
- **テキストレンダリング** - 6語以内で高精度（text_module）
- **Search Grounding** - Google検索による実世界精度

### ディレクトリ構造

| Folder | Description |
|--------|-------------|
| `logic/` | JSONスキーマ、multi-image-slots、grounding-rules |
| `vocabulary/` | photography, cinematography, typography, fluid-dynamics, text-integration |
| `strategies/` | prompt-techniques, video-workflow, troubleshooting, quality-techniques |
| `styles/` | artistic-styles, corporate-data-viz, ui-ux-design |
| `templates/` | ユースケース別JSONテンプレート |

### 主要ファイル

| File | Description |
|------|-------------|
| `INDEX.md` | **エントリーポイント**（ルーター機能付き） |
| `00-system-prompt.md` | Geminiへのロール定義・モデル哲学 |
| `logic/json-schema.md` | マスターJSONスキーマ + logic_chain + text_module |
| `strategies/quality-techniques.md` | 品質向上テクニック（Ingredients Method等） |

### テンプレート一覧

- `character-sheet.json` - キャラクター一貫性用
- `cyberpunk-character.json` - 詳細キャラクター例（Veo連携対応）
- `product-shot.json` - 商品撮影
- `scene-background.json` - 環境・背景
- `manga-panel.json` - 漫画パネル
- `ui-mockup.json` - UI/UXモックアップ
- `architecture-floorplan.json` - 建築・間取り図
- `fashion-lookbook.json` - ファッション撮影
- `social-media-influencer.json` - SNSコンテンツ

---

## Image Generation: Grok Aurora (`resources/image/grok-aurora/`)

xAI Aurora エンジンによる静止画生成。自己回帰型アーキテクチャでJSON構造化プロンプトに最適化。

### 特徴

- **自己回帰型MoE** - トークン予測ベースの生成（拡散モデルとは異なる）
- **ネイティブJSON対応** - 構造化プロンプトでの精密制御
- **テキストレンダリング** - 高精度な画像内テキスト生成
- **Spicy Mode** - 緩和されたコンテンツモデレーション
- **Grok Imagine連携** - 生成画像をそのままI2V入力に使用可能

### ディレクトリ構造

| Folder | Description |
|--------|-------------|
| `keywords/` | shot-composition, cinematography, visual-details |
| `strategies/` | filter-bypass, json-remix, character-consistency |

### 主要ファイル

| File | Description |
|------|-------------|
| `INDEX.md` | **エントリーポイント** |
| `00-system-prompt.md` | Aurora専用ロール定義 |
| `json-schema.md` | Aurora専用JSONスキーマ（shot, cinematography, visual_details） |
| `api-parameters.md` | APIパラメータ仕様 |
| `strategies/json-remix.md` | スタイル維持・一部変更テクニック |
| `strategies/character-consistency.md` | キャラクター一貫性 |
| `strategies/filter-bypass.md` | 静止画用フィルタ回避 |

### Nano Banana Pro vs Grok Aurora

| 項目 | Nano Banana Pro | Grok Aurora |
|------|-----------------|-------------|
| **エンジン** | Gemini 3 Pro | xAI Aurora |
| **アーキテクチャ** | 拡散モデル | 自己回帰型MoE |
| **JSON対応** | ○ | ◎（ネイティブ） |
| **テキストレンダリング** | ○（text_module） | ◎（高精度） |
| **コンテンツ制限** | 標準 | Spicy Mode対応 |
| **動画連携** | Veo 3.1 I2V | Grok Imagine I2V |
| **最適用途** | Veoパイプライン | Grokパイプライン |

---

## Video: Veo 3.1 (`resources/video/veo/`)

### human-manual/

人間がワークフローを理解するためのガイド（日本語）

| File | Description |
|------|-------------|
| `00-quick-start.md` | 5分で始めるクイックスタート |
| `01-workflow-selector.md` | ユースケース別ワークフロー選択 |
| `troubleshooting.md` | よくある問題と解決策 |
| `image-generation/` | 静止画生成手順 |
| `video-generation/` | 動画生成手順 |
| `extend/` | 動画延長手順 |
| `use-cases/` | ユースケース別詳細ガイド |

### reference/

GeminiがVeo 3.1プロンプトを生成する際のリファレンス（英語）

| File | Description |
|------|-------------|
| `INDEX.md` | **エントリーポイント** |
| `00-system-prompt.md` | Geminiへのロール定義 |
| `json-schema.md` | 動画生成スキーマ |
| `keywords/` | カメラ・ライティング・スタイル |
| `keywords/camera-movement.md` | シネマティックカメラワーク |
| `keywords/audio-cues.md` | サウンドデザインキーワード |
| `use-case-templates/` | ユースケース別JSONテンプレート |

---

## Video: Grok Imagine (`resources/video/grok/`)

### reference/

GeminiがGrok Imagineプロンプトを生成する際のリファレンス（英語）

| File | Description |
|------|-------------|
| `INDEX.md` | **エントリーポイント** |
| `00-system-prompt.md` | Geminiへのロール定義 |
| `json-schema.md` | **6要素フォーマット・JSONサンプル** |
| `api-parameters.md` | APIパラメータ仕様 |
| `workflows.md` | ワークフローテクニック（Last Frame等） |
| `troubleshooting.md` | トラブルシューティング |
| `spicy-mode.md` | Spicy Mode詳細 |
| `strategies/filter-bypass.md` | フィルタ回避テクニック |
| `strategies/video-escalation.md` | 静止画→動画でのフィルタ回避 |
| `keywords/` | カメラ・ライティング・スタイル・オーディオ |
| `keywords/digital-aesthetics.md` | インターネット美学（glitch, vaporwave等） |

---

## Usage

### For Humans

1. 作りたい動画のプラットフォーム（Veo/Grok）を選択
2. 該当する `human-manual/00-quick-start.md` を読む
3. Geminiに依頼する際の参考にする

### For Gemini (Image - Nano Banana Pro)

```
resources/image/nano-banana-pro/INDEX.md を読んで、
[ユースケース] のNano Banana Proプロンプトを生成して
```

### For Gemini (Veo)

```
resources/video/veo/reference/INDEX.md を読んで、
[ユースケース] のVeo 3.1プロンプトを生成して
```

### For Gemini (Grok Imagine - Video)

```
resources/video/grok/reference/INDEX.md を読んで、
[ユースケース] のGrok Imagineプロンプトを生成して
```

### For Gemini (Grok Aurora - Image)

```
resources/image/grok-aurora/reference/INDEX.md を読んで、
[ユースケース] のGrok Aurora静止画プロンプトを生成して
```

### For Gemini (Grok Pipeline - Image + Video)

```
resources/image/grok-aurora/reference/INDEX.md と
resources/video/grok/reference/INDEX.md を読んで、
[ユースケース] のGrok静止画+動画パイプラインを設計して
```

---

## Integration for App Development

アプリ開発でプロンプト生成機能を組み込む場合、`reference/` フォルダをプロジェクトに取り込む。

```
your-app/
├── src/
└── prompts/
    ├── image-nano/        ← resources/image/nano-banana-pro/ をコピー
    ├── image-aurora/      ← resources/image/grok-aurora/reference/ をコピー
    ├── veo-reference/     ← resources/video/veo/reference/ をコピー
    └── grok-reference/    ← resources/video/grok/reference/ をコピー
```

LLM APIに `INDEX.md` をエントリーポイントとして渡す。`INDEX.md` がユースケースに応じて必要なファイルを指示する。

---

## Workflow Overview

### Veo 3.1 Workflow
```
[Image]                 [Video]                 [Extend]
Nano Banana Pro    →    Veo 3.1            →    Video Extension
(Gemini 3 Pro)          Text-to-Video           8s → longer
                        Image-to-Video
                        Ingredients mode
```

### Grok Workflow (Image + Video)
```
[Image]                 [Video]
Grok Aurora        →    Grok Imagine
(xAI Aurora)            Text-to-Video
                        Image-to-Video
                        Native Audio
```

**Note**: Grok AuroraからGrok ImagineへのI2V連携は、同一エコシステム内で最もスムーズに動作。Video Escalationテクニックにも最適。

---

## Key Concepts

### Nano Banana Pro（静止画）
- **Nano Banana Pro**: Gemini 3 Pro による静止画生成（推論エンジン搭載、JSON構造化プロンプト対応）
- **logic_chain**: 物理法則・空間配置の事前計画スキーマ
- **text_module**: テキストレンダリング専用モジュール
- **Quality Techniques**: Ingredients Method, Search-to-Render, Physics-Aware等

### Veo 3.1（動画）
- **Veo 3.1**: Google の動画生成AI（高品質、4/6/8秒）
- **Ingredients**: Veo用参照画像によるキャラクター一貫性機能

### Grok Aurora（静止画）
- **Grok Aurora**: xAI の静止画生成AI（自己回帰型MoE、JSON最適化）
- **JSON Remix**: 参考画像から特徴抽出→一部変更で新規生成
- **Character Consistency**: アンカーイメージとVLMによる一貫性維持
- **Spicy Mode (Image)**: 静止画用の緩和されたコンテンツモデレーション

### Grok Imagine（動画）
- **Grok Imagine**: xAI の動画生成AI（高速、5-15秒、Aurora Engine）
- **6-Component Formula**: Grok用プロンプト構造（Subject + Action + Camera + Lighting + Environment + Audio）
- **Last Frame Method**: Grokで長尺動画を作成するテクニック
- **Spicy Mode (Video)**: 動画用の緩和されたコンテンツモデレーション
- **Video Escalation**: 静止画→動画変換でフィルタを回避するテクニック

### 共通
- **JSON Prompt**: 構造化されたプロンプトフォーマット

---

## docs/ Structure

```
docs/
├── sources/              # 調査資料（収集した生データ）
│   ├── official/         # 公式ドキュメント
│   ├── community/        # コミュニティ情報
│   └── grok/             # Grok調査資料
├── resources/            # プラットフォーム別調査資料（整理済み）
│   ├── grok_image/       # Grok Aurora静止画調査資料
│   ├── grok_video/       # Grok Imagine動画調査資料
│   ├── nano_banana_pro/  # Nano Banana Pro調査資料
│   └── veo/              # Veo調査資料
├── ask/                  # AI会話ログ（自動保存）
└── log/                  # 作業ログ
```
