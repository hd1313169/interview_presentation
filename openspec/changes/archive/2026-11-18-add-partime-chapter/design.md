## Context

簡報由 `deck/_tools/build.py` 產生：頁面在 `build.py`，講稿在 `notes.py`（用 `data-title` 對應），補字由 `fonts.py` 處理，截圖由 `capture_site.py` 產生。build 會同時輸出 `index.html`（公開版，沒有講稿）與 `RyanChiang_presentation.notes.html`（本機版）。字型是內嵌的子集，所以新文字一定要補字。目前第三、四章的 `data-title` 前綴是「第三章｜」「第四章｜」。

## Goals / Non-Goals

**Goals:**
- 在案例二和 CRM 之間插入 Partime 6 頁，議程歸到「B2C 產品設計」組
- CRM、Storybook 順延成 CASE 04、05，頁碼、議程與跳轉都要正常
- 待補內容用一眼就看得出來的樣式先放上去

**Non-Goals:**
- 不改 CRM、Storybook 和前兩章的內容（只改編號）
- 不動 `cocomart/`、`athena/`、`bear/`
- 不移除 12 分鐘計時器（它只是講者工具，不會限制內容）

## Decisions

- **`data-title` 的命名**：Partime 用「第三章｜Partime ...」，CRM 改成「第四章｜CRM ...」，Storybook 改成「第五章｜...」。議程的 `data-goto`、`notes.py` 的對應鍵一起改名。另一個做法是保留舊前綴、只改 eyebrow，但這樣標題和實際章節會對不上，以後很容易搞混。
- **版面沿用現有元件**：封面用 `case-cover`，問題頁用兩張卡片，試算表那頁用 `cmp` 表格，AI 分工頁用兩欄表格，回饋頁用三張卡片。不新增設計語言。
- **設計判斷頁**：截圖加上三個編號標註，用逐步顯示一次出現一個（3 步，符合每頁最多 4 步）。
- **待補樣式**：新增 `.tbd` class，虛線框加上一個帶色的「待補」chip，內容寫要補什麼（例如「工作室給了什麼回饋」）。公開版也照樣顯示，讓你發佈前就看得到。
- **截圖**：用 `capture_site.py` 從線上版截週報表，存到 `deck/_assets/partime/`。如果線上版需要先輸入資料才會出現報表，就用 JS 參數填入示範資料。
- **講稿**：第 3、5 頁用大綱中的講者備註；其他頁從大綱補一句簡短提示。大綱中提到應徵公司的那一句不放進去。

## Risks / Trade-offs

- [線上版截圖拿不到有資料的週報表] → 退而使用空狀態截圖並在 tasks 中記錄，請使用者提供截圖
- [第 5 頁和 CRM 的 AI 分工重疊] → Partime 版強調「決定不做什麼」，CRM 版強調流程；如果還是太像，之後再刪
- [`data-title` 改名漏改，造成跳轉失效或講稿對不上] → build 後檢查每個 `data-goto` 都有對應的頁，以及每頁都有講稿
