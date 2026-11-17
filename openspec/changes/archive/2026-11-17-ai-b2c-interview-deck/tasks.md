# Tasks

## 1. 封存 bear 版與整理資料夾

- [x] 1.1 執行 `git show HEAD:index.html > bear/RyanChiang_presentation.html`，用 `cmp` 確認和 HEAD 版完全相同
- [x] 1.2 在 `.gitignore` 加入 `deck/_*`、`bear/*.md`、`bear/_*`，用 `git status --short bear/` 確認只剩 `RyanChiang_presentation.html` 和 PDF 會被追蹤
- [x] 1.3 把 `bear/_tools/` 複製到 `deck/_tools/`、`bear/_assets/echorise/` 複製到 `deck/_assets/echorise/`，路徑改成 `deck/...`；先不改內容，跑 `python deck/_tools/build.py`，確認產生的 `index.html` 和 HEAD 版的頁面標題清單（`data-title`）一致

## 2. 刪除與案例一調整

- [x] 2.1 從 build 中刪除「視覺與素材設計」段落和整合行銷系統的附錄頁，刪掉對應的講稿；build 後搜尋 GoBridge、LPG、整合行銷，確認都沒有結果
- [x] 2.2 刪除「案例一｜流程驗證」頁，把封面與議程的副標改掉「從流程驗證到上線」；確認案例一剩 6 頁、順序符合 spec
- [x] 2.3 成果頁改成「已上線 2 年／付費使用者 50+／產出報告 400+」，同步更新講稿；搜尋確認 1000+、100+ 不再出現在案例一

## 3. 第三章：CRM 移入主線

- [x] 3.1 CRM 封面與 5 頁改到收尾之前，移除 `data-appendix`，eyebrow 改成 CASE 03；截圖確認沒有「附錄」字樣、頁碼正常顯示、總覽沒有虛線標記
- [x] 3.2 在案例二與第三章之間加入黑底「AI 應用」轉場頁；截圖確認

## 4. 第四章：AI × Storybook

- [x] 4.1 製作第四章封面（case-cover 樣式，CASE 04）
- [x] 4.2 問題頁：兩張卡片（不知道已有元件而自己重做／看不到畫面、無法自我驗證）
- [x] 4.3 架構頁：分層圖 tokens.json → primitive / semantic / component → 29 個 fb-* 元件 → 頁面，逐步顯示不超過 4 步
- [x] 4.4 閉環頁：六步流程加上對應工具（OpenSpec、Storybook、fb-* + token、npm run shots、lint:tokens / lint:brand、GitHub Actions → Pages），以及兩條回圈；截圖確認
- [x] 4.5 角色與成果頁：三個角色、29 個元件、11 個頁面、demo 網址
- [x] 4.6 為第四章各頁加講稿；逐項和 Introduction 頁對照，確認沒有自行補的事實，也沒有提到 CRM

## 5. 開場與收尾

- [x] 5.1 議程頁改成兩組四章（B2C 產品設計：01、02；AI 應用：03、04）；截圖確認
- [x] 5.2 收尾頁改寫成同時涵蓋產品與 AI 兩個面向，保留「謝謝，歡迎提問」、網站與 email；確認沒有公司名稱
- [x] 5.3 「關於我」頁如果有提到視覺素材，就改成符合新的兩組定位；和使用者確認文案

## 6. 建置與整體驗證

- [x] 6.1 執行 `fonts.py` 補字後重新 build，直到 `missing.txt` 是空的
- [x] 6.2 確認 `index.html` 沒有 `class="notes"`、沒有外部請求（搜尋 `http` 只剩文案裡的網址），並確認沒有任何公司名稱
- [x] 6.3 恢復 `presentation/RyanChiang_presentation.html` 轉址頁，開啟 `#5` 確認會轉到根目錄的第 5 頁
- [x] 6.4 在瀏覽器把整份簡報從頭翻到尾：每頁逐步顯示不超過 4 步、頁碼連續、首頁按鈕和進度條都正常
- [x] 6.5 確認 `athena/`、`cocomart/` 沒有任何變動（`git status`）

## 7. 第一輪回饋修正

- [x] 7.1 Wizard 流程頁：流程先置中，點擊後移到左上並出現第一張圖；截圖確認三個狀態
- [x] 7.2 移除「AI 應用」轉場頁（取代 3.2）；確認案例二成果後直接接第三章封面
- [x] 7.3 第三章移除設計決策頁、驗證方式頁的「驗收時發現」段落與講稿；小標重新編號 01–04
- [x] 7.4 第三章成果頁移除 Phase 提前天數文字，時程圖放大到 1500px；截圖確認

## Workflow follow-up

- 使用者確認後再 commit 並推上 GitHub Pages。
- 完成後封存這個 change，並把 delta 同步到主 specs。
