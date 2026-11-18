## Why

面試時要盡量展示作品，不再受 12 分鐘限制。Partime 是一個 C 端 Side Project：從自己用的試算表開始，再用 AI 協作做成工具，目前有一間工作室在試用。目前的簡報缺少「自己發起、自己定義需求」的 C 端作品，Partime 剛好補上這一塊。

## What Changes

- 新增 Partime 章節（5 頁：封面、從試算表衍伸、適用情境、AI 協作流程、試用回饋），放在第三章，文案來源是 `Partime.md`
- 議程頁的「B2C 產品設計」組改成 01、02、03（Partime）；「AI 應用」組改成 04（CRM）、05（Storybook）
- **BREAKING（編號）**：CRM 從 CASE 03 改成 CASE 04，Storybook 從 CASE 04 改成 CASE 05，`data-title` 前綴、議程連結和頁碼一起更新；總頁數從 26 頁變成 31 頁
- 還沒確定的內容（第 6 頁的回饋、第 4 頁的設計理由）先用明顯的「待補」樣式呈現，之後再補
- 第 4 頁使用線上版 https://hd1313169.github.io/partime/ 的週報表截圖，並標註三個位置

## Capabilities

### New Capabilities

（無）

### Modified Capabilities

- `ai-b2c-interview-deck`：章節結構從四章變成五章，議程分組加入 Partime，CRM 和 Storybook 順延編號；新增 Partime 章節的內容要求

## Impact

- 建置工具：`deck/_tools/build.py`（頁面）、`deck/_tools/notes.py`（講稿）、`deck/_tools/fonts.py`（補字）
- 產出檔案：`index.html`（公開版）、`RyanChiang_presentation.notes.html`（本機講稿版）；兩份都由 build 產生
- 新素材：`deck/_assets/partime/`（截圖）
- 不受影響：`cocomart/`、`athena/`、`bear/`
