# マニュアル更新計画

**スコープ**: Veo 3.1 + Grok（NotebookLMは今回対象外）
**Filter Bypass**: 警告追加のみ（検証なし）

---

## 発見された重大な変更点

### Veo 3.1 (2026年1月13日アップデート)

| 項目 | 旧ドキュメント | 最新情報 |
|------|--------------|---------|
| 最大解像度 | 1080p | **4K (3840x2160)** |
| 最大尺 | 8秒 | **60秒** |
| 縦動画 | クロップ必要 | **ネイティブ9:16サポート** |
| Ingredients | 基本機能 | **キャラクター一貫性向上** |
| アップスケーリング | なし | **1080p/4Kアップスケール** |

### Grok Imagine

| 項目 | 旧ドキュメント | 最新情報 |
|------|--------------|---------|
| T2V尺 | 5-15秒 | **6-15秒（音声付き）** |
| 生成速度 | 記載なし | **平均17秒以下** |
| Video Extension | なし | **Web UIで利用可能** |
| HD Upscaling | なし | **Web UIで利用可能** |
| Meme Mode | なし | **新モード追加** |
| サブスク | Free/Pro | **Free/Heavy/SuperGrok** |
| Live Search API | 記載あり | **2026年1月12日で廃止** |

---

## 更新作業

### Step 1: Veo 3.1 APIパラメータ更新

**ファイル**: `resources/video/veo/reference/api-parameters.md`

変更内容:
- 解像度に4K追加
- 尺の上限を60秒に更新
- アップスケーリングパラメータ追加
- ネイティブ縦動画パラメータ追加

### Step 2: Veo 3.1 JSONスキーマ更新

**ファイル**: `resources/video/veo/reference/json-schema.md`

変更内容:
- metaセクションにresolution: "4K"追加
- duration制約を60秒まで拡張
- upscalingオプション追加

### Step 3: Veo差分ドキュメント更新

**ファイル**: `resources/video/veo/reference/veo3-vs-3.1-differences.md`

変更内容:
- 2026年1月13日アップデートセクション追加
- 4K/60秒/アップスケーリング記載

### Step 4: Grok APIパラメータ更新

**ファイル**: `resources/video/grok/reference/api-parameters.md`

変更内容:
- Live Search API廃止警告追加
- サブスクリプションティア更新（SuperGrok追加）
- Video Extension/HD Upscalingパラメータ追加
- 生成速度（<17秒）追記

### Step 5: Grok ワークフロー更新

**ファイル**: `resources/video/grok/reference/workflows.md`

変更内容:
- Video Extension ワークフロー追加
- HD Upscaling ワークフロー追加

### Step 6: Grok JSONスキーマ更新

**ファイル**: `resources/video/grok/reference/json-schema.md`

変更内容:
- Meme Modeテンプレート追加
- 音声同期の記述更新

### Step 7: Filter Bypass警告追加

**ファイル**:
- `resources/video/grok/reference/strategies/filter-bypass.md`
- `resources/video/grok/reference/strategies/video-escalation.md`
- `resources/image/grok-aurora/reference/strategies/filter-bypass.md`

変更内容:
- 各戦略に「⚠️ 2026年1月時点: 効果が低下している可能性あり」警告追加
- 特にLoin Patch Glitchは「パッチ済みの可能性が高い」と明記

### Step 8: INDEX/CHANGELOGの更新

**ファイル**:
- `resources/video/veo/reference/INDEX.md`
- `resources/video/grok/reference/INDEX.md`
- 各CHANGELOG.md

変更内容:
- Last Updated日付を2026-01-21に更新
- CHANGELOGに今回の更新内容追記

---

## 検証方法

更新完了後:
1. JSONスキーマの構文チェック
2. リンク切れチェック（内部リンク）
3. 用語の一貫性確認

---

## 情報ソース

- [Google Developers Blog - Veo 3.1](https://developers.googleblog.com/en/introducing-veo-3-1-and-new-creative-capabilities-in-the-gemini-api/)
- [Google Blog - Veo 3.1 Ingredients](https://blog.google/innovation-and-ai/technology/ai/veo-3-1-ingredients-to-video/)
- [xAI Docs - Models](https://docs.x.ai/docs/models)
