## Why

AI 應用組（CRM、Storybook）目前直接從案例封面開始，缺少一頁交代整體 AI 協作流程。先用一張流程圖說明「AI 負責產出、判斷留在我這邊」，後面兩個案例就能對應到流程中的不同階段。之前拿掉的「AI 應用」過場頁，也由這頁補上開場的功能。

## What Changes

- 在 CRM 章節封面前新增一頁「AI 協作流程」泳道圖，作為 AI 應用組的開場頁
- 文案依 `AI workflow.md`：小標 AI WORKFLOW，主標「從需求到交付，AI 協作的五個階段」，5 個階段 × 2 排卡片（AI 產出／我的判斷），部分文案經使用者修訂
- 下排「我負責判斷」用黑底卡片強調；逐步顯示分兩步，先上排、再下排
- 不列入議程，也不佔案例編號
- 講者備註放入文件中的講稿，以及被追問時用的補充（原型階段細部流程、設計稿階段口頭例子）；投影片上不放
- 總頁數多 1 頁，之後的頁碼順延

## Capabilities

### New Capabilities

（無）

### Modified Capabilities

- `ai-b2c-interview-deck`：AI 應用組開頭新增一頁流程總覽

## Impact

- 建置工具：`deck/_tools/part2.py`（在 CRM 封面前插入頁面與 CSS）、`deck/_tools/notes.py`（講稿）、`deck/_tools/fonts.py`／`missing.txt`（補字）
- 產出檔案：`index.html`、`RyanChiang_presentation.notes.html`（由 build 產生）
- 與進行中的 `add-partime-chapter` 獨立；本頁固定插在 CRM 章節封面前，不受章節編號影響
