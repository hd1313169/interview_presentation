## Context

頁面由 `deck/_tools/build.py` 產生，AI 應用組在 `part2.py` 中組裝：先插入 CRM 封面（`sec('案例二｜封面')`），再接 CRM 其他頁與 `ch4.py`（Storybook）。可重用的樣式有 `.card`、`.gates .card.src`（黑底卡片）、`.frag`／`data-group`（逐步顯示，每頁最多 4 步）。

## Goals / Non-Goals

**Goals:**
- 一頁讀得懂的 6×2 泳道圖，投影時字夠大
- 視覺重心在下排「我負責判斷」

**Non-Goals:**
- 不改議程、不改其他章節編號與內容
- 不放出處案例或原型細部流程

## Decisions

- **插入位置**：在 `part2.py` 中，於 `S.append(CRM 封面)` 之前呼叫 `slide(...)`。用位置而非章節編號定位，不受 `add-partime-chapter` 的編號調整影響。
- **版面**：整頁 `dark`。5 欄 × 3 列 grid：第一列為編號與階段名（無卡片、無箭頭）；第二列為深灰「AI 產出」卡片；第三列為白底「我的判斷」卡片。兩列卡片之間用六步閉環的線段箭頭連接。三段各自獨立，同列高度自動對齊。
- **逐步顯示**：階段名不參與逐步顯示。兩列卡片依階段兩個一組：01–02 為 `data-group="a"`、03–04 為 `b`、05 為 `c`，共 3 步，符合每頁最多 4 步的限制。組內用 `--d` transition-delay 錯開（AI 產出 0／260ms、我的判斷 130／390ms），進場改為 `translateX(-24px)` 由左向右，取代預設的由下往上。
- **文案**：照 `AI workflow.md` 表格；若某格在 1 欄寬度內超過兩行，就在不改意思的前提下縮短，並在實作時回報。
- **頁碼與標題**：`data-title` 為「AI 協作流程」，使用 `pageno='00'`，交給 build 重新編號；eyebrow 用「AI WORKFLOW」。

## Risks / Trade-offs

- 6 欄每欄約 250px，較長的格子（原型、設計稿）可能換成兩行 → 先實作再截圖檢查，必要時縮字或微調文案
- 新字元可能不在內嵌字型內 → 跑缺字檢查，補進 `missing.txt` 後重跑 `fonts.py`
