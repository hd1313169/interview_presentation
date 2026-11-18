# Design

## Context

頁面由 `deck/_tools/build.py` 產生，講稿放在 `notes.py`，並以頁面名稱對應。素材放在 `deck/_assets/<案例>/`，截圖用 `capture_site.py`（無頭 Chrome）。`deck/_tools/README.md` 裡還寫著舊的 `presentation/_tools` 路徑，實作時以 `deck/_tools` 為準。OddBird 的內容來源是 `C:\Users\wsad7\Desktop\oddbird` 的 `PRODUCT.md`、`DESIGN.md`、封存的 OpenSpec change，以及 git 紀錄。

## Goals / Non-Goals

**Goals:**
- 讓 OddBird 和 Partime 一樣用 case-cover 封面加內容頁，沿用既有視覺 token 和逐步顯示（每頁最多 4 步）
- 把 OddBird 和 Partime 拉開：Partime 講需求與規格驅動流程；OddBird 講多人即時協作、資料一致性和現場可用性，不再放一頁「AI 協作流程」

**Non-Goals:**
- 整份簡報其他章節的編排與文案（使用者表示之後再調整）
- 公開 OddBird 的程式碼或分享連結本身

## Decisions

- **頁面順序靠調整 build.py 的 slide 陣列**，不另外做排序機制。原因是目前的頁面本來就依陣列順序輸出。
- **截圖**：用 `capture_site.py` 截檢視頁，電腦版（1440 寬）各功能分頁與手機版（390 寬），放進 `deck/_assets/oddbird/`。截圖前要確認畫面沒有真實姓名以外的個資；球員暱稱如果是真名，就用模糊處理或改截不含姓名的區塊。
- **迭代歷程頁只寫各階段新增的功能**：不寫改版次數、日期或使用數據。
- **封面欄位**比照 Partime：只列專案時程（2026.09 — 至今）和使用工具（Claude Code・Impeccable・Supabase）。

## Risks / Trade-offs

- [兩個 side project 共 9 頁] → OddBird 已精簡成 4 頁，日後整份簡報一起調整
- [線上資料可能變動，截圖內容和簡報說法對不上] → 截圖後對照頁面文案，以截圖當下的畫面為準
- [新頁面的中文字可能不在內嵌字型裡] → build 後跑 `fonts.py` 補字，再 build 一次

## Open Questions

- 如果之後補上真實使用數據，迭代歷程頁可以改成「試用回饋」（不影響這次的結構）
