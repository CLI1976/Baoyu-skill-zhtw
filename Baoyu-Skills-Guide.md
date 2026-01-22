# Baoyu Skills 完整介紹

這是一套 Claude Code 技能集，用於內容創作、圖片生成、內容轉換與社群發布。

---

## 📝 內容創作類

| 技能 | 功能 | 適合場景 |
|------|------|----------|
| **baoyu-article-illustrator** | 智能文章插圖生成 | 為部落格、技術文章自動添加概念插圖 |
| **baoyu-cover-image** | 文章封面圖生成 | 社群媒體貼文封面、部落格文章 Header |
| **baoyu-comic** | 知識漫畫創作 | 傳記漫畫、教學漫畫、概念解說（有角色一致性管理） |
| **baoyu-infographic** | 資訊圖表生成 | 數據視覺化、流程圖、比較表（20 種版型 × 17 種風格） |
| **baoyu-slide-deck** | 簡報圖片生成 | 會議簡報、教學投影片、演講素材 |
| **baoyu-xhs-images** | 小紅書圖文系列 | 社群行銷、知識分享貼文（1-10 張系列圖） |

### baoyu-article-illustrator

智能分析文章結構，識別需要視覺輔助的位置，自動生成插圖。

```bash
/baoyu-article-illustrator path/to/article.md
/baoyu-article-illustrator path/to/article.md --style warm
```

**支援 21 種風格**：notion（預設）、elegant、warm、minimal、playful、watercolor、chalkboard、blueprint、pixel-art、fantasy-animation 等。

### baoyu-cover-image

為文章生成手繪風格封面圖。

```bash
/baoyu-cover-image path/to/article.md
/baoyu-cover-image path/to/article.md --style blueprint
```

**支援風格**：elegant（預設）、flat-doodle、blueprint、bold-editorial、dark-atmospheric、fantasy-animation 等。

### baoyu-comic

創作知識漫畫，支援角色一致性管理。

```bash
/baoyu-comic posts/turing-story/source.md
/baoyu-comic --style ohmsha  # 歐姆社漫畫風格
```

**特色**：
- 支援 Logicomix/Ligne Claire 風格
- 角色定義模板（外觀、服裝、表情）
- 分鏡版型：standard、cinematic、dense、splash、webtoon

### baoyu-infographic

生成專業資訊圖表，兩個維度自由組合。

```bash
/baoyu-infographic path/to/content.md
/baoyu-infographic path/to/content.md --layout hierarchical-layers --style craft-handmade
```

**20 種版型**：bridge、circular-flow、funnel、iceberg、tree-branching、venn-diagram 等。

**17 種風格**：craft-handmade（預設）、chalkboard、cyberpunk-neon、ikea-manual、pixel-art 等。

### baoyu-slide-deck

將內容轉換為簡報圖片。

```bash
/baoyu-slide-deck path/to/content.md
/baoyu-slide-deck path/to/content.md --style sketch-notes --slides 10
/baoyu-slide-deck path/to/content.md --audience executives
```

**支援風格**：blueprint（預設）、chalkboard、notion、corporate、dark-atmospheric 等。

### baoyu-xhs-images

生成小紅書風格的系列圖文。

```bash
/baoyu-xhs-images posts/ai-future/article.md
/baoyu-xhs-images posts/ai-future/article.md --style notion --layout dense
```

**風格**：notion、bold、cute、fresh、minimal、pop、retro、warm、chalkboard

**版型**：balanced、comparison、dense、flow、list、sparse

---

## 🖼️ 圖片生成後端

| 技能 | 功能 | 適合場景 |
|------|------|----------|
| **baoyu-image-gen** | AI SDK 圖片生成 | 使用 OpenAI/Google **官方 API**（需付費） |
| **baoyu-danger-gemini-web** | Gemini Web 圖片生成 | 使用 Gemini **網頁版**（免費但需登入） |

> ⚠️ 其他創作類技能（cover-image、infographic 等）會呼叫這兩個後端之一

### baoyu-image-gen

使用官方 API 生成圖片。

```bash
# 需要設定 API Key
# 支援 OpenAI DALL-E、GPT Image
# 支援 Google Imagen、Gemini
```

### baoyu-danger-gemini-web

使用 Gemini 網頁版生成圖片（免費）。

```bash
# 需要 Chrome 登入 Google 帳號
# 支援文字生成和圖片生成
# 支援參考圖片輸入
```

---

## 🔄 內容轉換類

| 技能 | 功能 | 適合場景 |
|------|------|----------|
| **baoyu-url-to-markdown** | 網頁轉 Markdown | 儲存網頁文章、建立知識庫 |
| **baoyu-danger-x-to-markdown** | X/Twitter 轉 Markdown | 保存推文串、X Articles |
| **baoyu-compress-image** | 圖片壓縮 | 轉 WebP、PNG 壓縮（部落格優化） |

### baoyu-url-to-markdown

使用 Chrome CDP 抓取網頁並轉換為 Markdown。

```bash
/baoyu-url-to-markdown https://example.com/article
```

**特色**：
- 自動模式：頁面載入後立即擷取
- 等待模式：適用於需要登入的頁面

### baoyu-danger-x-to-markdown

將 X/Twitter 內容轉換為 Markdown。

```bash
/baoyu-danger-x-to-markdown https://x.com/user/status/123456
```

**支援**：
- 推文串 → Markdown（含 YAML front matter）
- X Articles → 完整文章內容

### baoyu-compress-image

跨平台圖片壓縮工具。

```bash
/baoyu-compress-image image.png  # 輸出 WebP
/baoyu-compress-image image.png --format png  # 保持 PNG
```

**特色**：
- 預設輸出 WebP 格式
- 支援 PNG-to-PNG 壓縮
- 自動選擇系統工具（sips、cwebp、ImageMagick）

---

## 📤 發布類

| 技能 | 功能 | 適合場景 |
|------|------|----------|
| **baoyu-post-to-x** | 發布到 X/Twitter | 自動發推、發布長文 X Articles |
| **baoyu-post-to-wechat** | 發布到微信公眾號 | 文章發布、圖文發布 |

### baoyu-post-to-x

使用 Chrome CDP 發布到 X/Twitter。

```bash
/baoyu-post-to-x "這是一則推文"
/baoyu-post-to-x path/to/article.md --type article  # 發布長文
```

**支援**：
- 一般推文（含圖片/影片）
- X Articles（長篇 Markdown 文章）

### baoyu-post-to-wechat

發布到微信公眾號。

```bash
/baoyu-post-to-wechat path/to/article.md --type article  # 文章
/baoyu-post-to-wechat path/to/content.md --type image-text  # 圖文
```

---

## 使用場景速查表

| 我想要... | 使用技能 |
|-----------|----------|
| 寫技術文章並加插圖 | `baoyu-article-illustrator` |
| 製作文章封面圖 | `baoyu-cover-image` |
| 把複雜概念做成漫畫 | `baoyu-comic` |
| 製作資訊圖表摘要 | `baoyu-infographic` |
| 做會議簡報 | `baoyu-slide-deck` |
| 做小紅書圖文系列 | `baoyu-xhs-images` |
| 保存網頁文章 | `baoyu-url-to-markdown` |
| 保存 Twitter 推文 | `baoyu-danger-x-to-markdown` |
| 壓縮圖片 | `baoyu-compress-image` |
| 自動發 Twitter | `baoyu-post-to-x` |
| 自動發微信公眾號 | `baoyu-post-to-wechat` |

---

## ⚠️ 注意事項

1. **`danger-` 開頭的技能**：使用逆向工程 API，可能有風險或違反服務條款
2. **`post-to-*` 技能**：需要瀏覽器登入（Chrome CDP 自動化）
3. **圖片生成後端選擇**：
   - `baoyu-image-gen`：官方 API，穩定但需付費
   - `baoyu-danger-gemini-web`：免費但需登入，可能不穩定

---

## 技能依賴關係

```
內容創作技能
├── baoyu-article-illustrator ──┐
├── baoyu-cover-image ──────────┤
├── baoyu-comic ────────────────┼──→ 圖片生成後端
├── baoyu-infographic ──────────┤    ├── baoyu-image-gen (官方 API)
├── baoyu-slide-deck ───────────┤    └── baoyu-danger-gemini-web (免費)
└── baoyu-xhs-images ───────────┘
```

---

## 快速開始

1. 安裝技能集：
   ```bash
   /plugin marketplace add CLI1976/Baoyu-skill-zhtw
   ```

2. 重啟 Claude Code

3. 使用技能：
   ```bash
   /baoyu-cover-image my-article.md
   ```
