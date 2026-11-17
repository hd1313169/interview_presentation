# Proposal

## Why

下一場面試的方向是「AI 應用」加上「B2C 接案」，兩邊都要重視。目前的簡報以兩個產品案例加上視覺素材為主，AI 相關內容只放在附錄，無法讓面試官在主線看到 AI 應用能力。

## What Changes

- 把目前的簡報（今天的 `index.html`）封存到 `bear/RyanChiang_presentation.html`，作為上一場面試的最終版本（覆蓋 bear 資料夾裡較舊的同名檔，舊版可從 git 歷史取回）。
- 新版簡報直接取代根目錄 `index.html`，主線改成四章、分兩組：
  - **B2C 產品**：01 選址決策工具、02 Echorise
  - **AI 應用**：03 證券業 CRM 的 AI 原型工作流、04 AI × Storybook
- 案例一：
  - 刪除「流程驗證」頁（標題「看到流程之後，業主才知道少了什麼」）
  - 成果頁改成「已上線 2 年／付費使用者 50+／產出報告 400+」
  - 封面與議程的副標不再寫「從流程驗證到上線」
- 案例二（Echorise）維持不變。
- **BREAKING**（相對於 bear 版）：
  - 刪除「視覺與素材設計」整個段落（段落封面、GoBridge ×2、LPG、banner、廣告素材、社群貼文）
  - 刪除附錄「整合行銷內部管理系統」（封面 + 4 頁）
- 附錄「證券業 CRM 的 AI 原型工作流」移到主線成為第三章。各頁內容與格式不變，只把標示從「附錄」改成正式章節（CASE 03）。
- 新增第四章「AI × Storybook」：把 ai-workflow-demo Storybook 的 Introduction 視覺化，約 4–5 頁，內容是問題 → 架構 → 六步閉環 → 我的角色與成果。
- 議程頁改成四章兩組；收尾頁改寫成同時涵蓋產品與 AI 兩條線。

## Capabilities

### New Capabilities
- `ai-b2c-interview-deck`：AI 加 B2C 版面試簡報的章節結構、內容來源、新章節的呈現方式，以及發佈規則。

### Modified Capabilities
- `deck-homepage`：根目錄 `index.html` 改為指向新的 AI 加 B2C 版，不再是 bear 版；bear 版改由 `bear/RyanChiang_presentation.html` 保存。

## Impact

- `index.html`（重新產生）、`RyanChiang_presentation.notes.html`（本機講稿版，重新產生）
- `bear/RyanChiang_presentation.html`（改成封存今天的 `index.html`）
- 建置工具：bear 版的 `build.py`、`notes.py`、`fonts.py` 已經移到 `bear/_tools/`，但程式裡的路徑還是寫 `presentation/...`，目前無法執行。新版需要一份自己的工具資料夾。
- `presentation/RyanChiang_presentation.html` 轉址頁目前在工作區是刪除狀態，需要恢復。
- 不動 `athena/`、`cocomart/`。
