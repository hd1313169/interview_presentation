# Tasks

## 1. 素材

- [x] 1.1 用 `deck/_tools/capture_site.py` 截 OddBird 檢視頁的電腦版（1440 寬）和手機版（390 寬）場地看板，以及比賽紀錄、成績統計、名人堂、場地與名單、使用說明各分頁，存到 `deck/_assets/oddbird/`；驗證：檔案存在，並確認畫面沒有不應公開的個資
- [x] 1.2 從 `oddbird/public/avatars` 挑一張鳥頭像給封面用，複製到 `deck/_assets/oddbird/`；驗證：檔案存在

## 2. 章節順序與編號

- [x] 2.1 在 `build.py` 把頁面順序改成：案例一、案例二、流程總覽、CRM、Storybook、Partime、收尾；驗證：build 後 `data-title` 依此順序出現
- [x] 2.2 把章節標示改成 CRM＝CASE 03、Storybook＝CASE 04、Partime＝CASE 05，同時更新各頁 `data-title` 的「第N章」；驗證：用 grep 確認沒有殘留的舊編號
- [x] 2.3 議程頁改成三組（B2C 產品設計 01–02、AI 應用 03–04、Side Project 05–06），連結都指向各章封面；驗證：瀏覽器點擊每個議程項目，都會跳到正確的封面

## 3. OddBird 章節

- [x] 3.1 在 `build.py` 的 Partime 之後、收尾之前新增 4 頁（封面、功能、即時同步、迭代歷程），各功能附截圖，文案依 spec，每頁最多 4 步；驗證：瀏覽器逐頁翻閱，順序正確
- [x] 3.2 在 `notes.py` 為 4 頁寫講稿；驗證：講稿版有備註，`index.html` 沒有
- [x] 3.3 迭代歷程頁列出三個階段新增的功能，不寫改版次數、日期或使用數據；驗證：檢查頁面沒有數字指標

## 4. 建置與輸出

- [x] 4.1 執行 build，再跑 `fonts.py` 補新字，然後重新 build；驗證：`missing.txt` 沒有剩下的字，離線開啟沒有缺字
- [x] 4.2 重新匯出 PDF；驗證：PDF 頁數等於簡報頁數，OddBird 截圖清楚
- [x] 4.3 更新 `Partime.md` 開頭的擺放位置說明，以及 `deck/_tools/README.md` 的路徑；驗證：文件內容和實際一致
