# Design

## Context

- 根目錄的 `index.html` 不是手寫的，是 build 產物。`build.py` 讀取 `athena/RyanChiang_presentation.html` 的版面與 CRM 頁面，組出各頁內容，再透過 `notes.py` 套上講稿、`fonts.css` 內嵌字型子集。最後產生兩份：`index.html`（發佈版，沒有講稿）和 `RyanChiang_presentation.notes.html`（本機講稿版）。
- 工具已經從 `presentation/_tools/` 搬到 `bear/_tools/`，但 `build.py` 裡仍然寫死 `presentation/_tools/...` 和 `presentation/_assets/...`，現在無法直接執行。
- `bear/` 目前沒有被 git 追蹤，而且裡面有寫著應徵公司名稱的文案檔（`*.md`）。`bear/RyanChiang_presentation.html` 是比今天的 `index.html` 更舊的版本。
- `presentation/RyanChiang_presentation.html`（轉址頁）在工作區是刪除狀態。

## Goals / Non-Goals

**Goals:**
- 用 build 流程產生新版，講稿版與發佈版維持同一份來源。
- bear 版完整封存，之後可以獨立打開。

**Non-Goals:**
- 不改視覺系統、講者工具或互動行為。
- 不更新 PDF 匯出（需要時另外跑 `export_pdf.py`，不列入這次驗收）。
- 不改 `athena/`、`cocomart/`。

## Decisions

1. **新版工具放在 `deck/_tools/`，bear 版工具凍結在 `bear/_tools/`。** 把 `bear/_tools/` 複製到 `deck/_tools/`，把路徑改成 `deck/...`，圖片素材也複製到 `deck/_assets/`。
   - 考慮過的替代做法：直接修改 `bear/_tools/build.py`。缺點是 bear 版就無法再重建。
   - 考慮過的替代做法：手改 `index.html`。缺點是講稿版會不同步、新字無法補進字型子集，而且 base64 圖片很大，不好手動編輯。
2. **bear 版封存用的是 `git show HEAD:index.html`**，而不是工作區的檔案。這樣可以確保拿到的是變更前已 commit 的版本，與 spec 的「位元組完全相同」一致。
3. **案例二只刪不改。** 移除 GoBridge、LPG 和素材頁之後，`deck/_assets/` 只需要保留 `echorise/`。
4. **第三章沿用 athena 的 CRM 頁面。** 只移除 `data-appendix`、把 eyebrow 從「附錄 · …」改成「CASE 03 · …」，其他標記不動。原本的附錄樣式規則（`.slide[data-appendix]`）保留在 CSS 裡也沒有影響。
5. **分組轉場用一張黑底轉場頁**，放在案例二成果頁和第三章封面之間，大字寫「AI 應用」並附一行說明，沿用原本「行銷素材｜段落封面」黑底頁的樣式。這比在第三章封面加小標更明顯，也跟議程的分組對應。B2C 組則在議程頁直接帶入，不另外加轉場頁。
6. **第四章的版面：**
   - 封面：沿用 case-cover 的樣式（主要職責：UI/UX Designer、設計系統、AI 協作流程；工具：Storybook・Claude Code・OpenSpec・GitHub Actions）
   - 問題頁：兩張對比卡片
   - 架構頁：由上到下的分層圖，逐步顯示 3 步
   - 閉環頁：橫向的六步流程，下方對應工具，兩條回圈用虛線箭頭表示，逐步顯示 3 步（規格與盤點 → 實作與驗證 → 把關與部署）
   - 角色與成果頁：三個角色加上 29 和 11 兩個數字，附 demo 網址

   全部用 HTML/CSS 繪製，不用截圖，這樣字型子集可以涵蓋所有文字。
7. **講稿**：在 `deck/_tools/notes.py` 為新頁面加入講稿，刪掉已移除頁面的講稿，更新案例一成果頁的數字。
8. **git 忽略規則**：加入 `deck/_*`、`bear/*.md`、`bear/_*`，避免文案與工具被發佈。`bear/RyanChiang_presentation.html` 本身要納入版本控制。

## Risks / Trade-offs

- [新文字不在字型子集裡，會退回系統字型] → build 後執行 `fonts.py` 把 `missing.txt` 裡的字補進字型，再 build 一次，直到 `missing.txt` 是空的。
- [第三章原本的頁碼與附錄 CSS 綁在一起，可能出現隱藏的頁碼] → 檢查 `.slide[data-appendix]::after{display:none}`，移除 `data-appendix` 後頁碼應該正常顯示，用截圖確認。
- [bear 資料夾裡的文案檔含公司名稱，可能被推上 GitHub] → 先加 `.gitignore`，再 `git add`，並用 `git status` 確認。
- [整份簡報變長] → 預估主線 31 頁（3 + 6 + 6 + 1 + 6 + 6 + 1）。計時器維持 12 分鐘，實際講述時間交給講稿控制，不在這次範圍。

## Migration Plan

1. 先封存 bear 版，再產生新版。
2. 如果要還原：`git checkout HEAD -- index.html`，把 `index.html` 還原成變更前的版本。
