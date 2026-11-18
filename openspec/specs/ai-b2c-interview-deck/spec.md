# ai-b2c-interview-deck Specification

## Purpose
定義 AI 加 B2C 版面試簡報：主線分成 B2C 產品與 AI 應用兩組共四章，以單一離線 HTML 發佈在網站根目錄，讓內容、編排與發佈規則在後續修改時保持一致。

## Requirements

### Requirement: 章節結構與順序
主線 SHALL 依序包含：封面、關於我、議程、案例一（選址決策工具）、案例二（Echorise）、第三章（Partime 個人工資管理工具）、第四章（證券業 CRM 的 AI 原型工作流）、第五章（AI × Storybook）、收尾。簡報 MUST NOT 包含「視覺與素材設計」段落、整合行銷內部管理系統的頁面，也不得有附錄。

#### Scenario: 章節順序
- **WHEN** 從第一頁依序翻到最後一頁
- **THEN** 依序是封面、關於我、議程、CASE 01、CASE 02、CASE 03（Partime）、CASE 04（CRM）、CASE 05（Storybook）、收尾，共 31 頁，後面沒有任何附錄頁

#### Scenario: 已刪除的內容
- **WHEN** 在發佈的 HTML 裡搜尋「視覺與素材」「GoBridge」「LPG」「整合行銷」「附錄」
- **THEN** 都沒有結果

### Requirement: 兩組敘事分組
議程頁 SHALL 把五章分成兩組呈現：「B2C 產品設計」（01、02、03）與「AI 應用」（04、05）。案例之間 MUST NOT 有額外的轉場頁。

#### Scenario: 議程分組
- **WHEN** 顯示議程頁
- **THEN** 「B2C 產品設計」下列出選址、Echorise、Partime 三章，「AI 應用」下列出 CRM、Storybook 兩章，每章都有標題與一行說明，而且點擊後會跳到該章封面

#### Scenario: 不加轉場頁
- **WHEN** 從 Partime 最後一頁翻到下一頁
- **THEN** 直接顯示 CRM 章的封面

### Requirement: 案例一內容調整
案例一 MUST NOT 包含「流程驗證」頁（標題「看到流程之後，業主才知道少了什麼」）。成果頁 SHALL 顯示「已上線 2 年」「付費使用者 50+」「產出報告 400+」。封面與議程的副標 MUST NOT 寫「從流程驗證到上線」。Wizard 流程頁 SHALL 先在畫面中央顯示「分析位置 → 半徑範圍 → 產業別」，點擊後流程移到標題下方左側並出現第一張圖，再點擊出現第二張圖。其餘頁面維持 bear 版內容。

#### Scenario: 成果數字
- **WHEN** 顯示案例一成果頁
- **THEN** 三個數字依序是 2 年、50+、400+，頁面上沒有出現 1 年、100+、1000+

#### Scenario: 流程頁已刪除
- **WHEN** 檢查案例一的頁面
- **THEN** 依序是封面、脈絡訪查、Wizard 流程、地圖互動分層、條件微調、成果

### Requirement: 案例二不變
案例二（Echorise）的頁面、文案、圖片與數字 SHALL 和 bear 版一致，只有頁碼可以不同。

#### Scenario: 和 bear 版比對
- **WHEN** 把案例二各頁和 `bear/RyanChiang_presentation.html` 對照
- **THEN** 除了頁碼以外內容完全相同

### Requirement: 第三章沿用 CRM 案例
CRM 章 SHALL 包含封面與 4 頁內容（挑戰、AI 分工、驗證方式、推動採用與成果），不含設計決策頁。驗證方式頁 MUST NOT 有「驗收時發現」段落；成果頁 SHALL 只用放大的時程圖呈現提前天數，不另列數字文字。章節標示 SHALL 是「CASE 04」，頁面 MUST NOT 有附錄的標記或樣式。

#### Scenario: 不再是附錄
- **WHEN** 顯示 CRM 章任一頁
- **THEN** 不會出現「附錄」字樣，頁碼與進度條和主線連續，總覽裡沒有附錄的虛線標記

#### Scenario: 成果數字保留
- **WHEN** 顯示 CRM 章成果頁
- **THEN** 時程圖顯示 Phase 1／2／3 分別提前 1／5／7 天，圖上方沒有另外的數字文字

### Requirement: 第四章 AI × Storybook
Storybook 章（CASE 05）SHALL 呈現為一套工作流程的示範，不是專案：用 Claude Code 透過 Figma MCP 讀取 Figma 設計稿的 design system，轉成 Storybook，以提升 AI 協作開發的準確性。內容依序是封面、兩個用途、架構、六步閉環、角色與影響。封面 SHALL 只列主要職責與使用工具（Figma、Figma MCP、Claude Code、Storybook），並使用 BatchExportDialog 文件頁截圖。這一章 MUST NOT 顯示元件數、頁面數或展示網址。

#### Scenario: 不是專案
- **WHEN** 檢查 Storybook 章的頁面與講稿
- **THEN** 沒有「專案規模」、29 個元件、11 個頁面或 Storybook 網址

#### Scenario: 封面工具
- **WHEN** 顯示 Storybook 章封面
- **THEN** 使用工具只列 Figma・Figma MCP・Claude Code・Storybook，不含 OpenSpec 與 GitHub Actions

#### Scenario: 閉環主視覺
- **WHEN** 顯示六步閉環那一頁
- **THEN** 六個步驟以圖像化的流程呈現，並標出「缺元件先提案」與「截圖驗證失敗就重跑」這兩條回圈

#### Scenario: 架構頁說法
- **WHEN** 顯示架構頁
- **THEN** 以整個 Foundations 層（色彩、字級、間距與圓角）作為唯一來源，且沒有前端框架或建置相依的說明

### Requirement: 第三、四章各自獨立
CRM 章與 Storybook 章 SHALL 作為兩個獨立案例呈現：Storybook 章 MUST NOT 引用 CRM 章的頁面或數字，也不得把自己描述成 CRM 章的延伸。

#### Scenario: 第四章不提 CRM
- **WHEN** 檢查 Storybook 章的文案與講稿
- **THEN** 沒有提到證券業、CRM，也沒有用到 CRM 章的數字

### Requirement: 收尾涵蓋兩組
收尾頁 SHALL 沿用原版標語，講稿同時呼應產品設計與 AI 應用兩條線，並保留「謝謝，歡迎提問」、網站與 email。收尾頁 MUST NOT 有公司名稱或針對特定公司的句子。

#### Scenario: 收尾頁內容
- **WHEN** 顯示收尾頁
- **THEN** 標語維持原版「不只實踐想法，也持續驗證與成長」，下方顯示網站與 email

### Requirement: 視覺系統與講者工具沿用
簡報 SHALL 沿用 bear 版的頁面骨架、視覺 token、逐步顯示（每頁最多 4 步）、鍵盤翻頁、全螢幕、總覽、12 分鐘計時、可拖曳進度條，以及首頁按鈕。

#### Scenario: 逐步顯示上限
- **WHEN** 計算任一頁的逐步顯示次數
- **THEN** 不超過 4 步

### Requirement: 完全離線
簡報 SHALL 只靠單一 HTML 檔就能完整顯示，不需要網路，包括新章節的每個字都要在內嵌字型裡。

#### Scenario: 斷網開啟
- **WHEN** 斷網後開啟 `index.html`
- **THEN** 沒有任何外部請求，所有圖片都載入，沒有文字退回系統字型

### Requirement: 發佈版無講稿與公司名稱
發佈的 `index.html` MUST NOT 含有講稿文字、應徵公司名稱，或針對特定公司的句子。含講稿的版本 SHALL 只存在本機，並由 git 忽略。

#### Scenario: 講稿不外流
- **WHEN** 檢查發佈的 `index.html`
- **THEN** 沒有 `class="notes"` 的內容

### Requirement: bear 版封存
這次變更前的根目錄簡報 SHALL 原樣保存為 `bear/RyanChiang_presentation.html`，之後不再修改。

#### Scenario: 封存內容一致
- **WHEN** 把 `bear/RyanChiang_presentation.html` 和變更前 commit 的 `index.html` 比對
- **THEN** 兩者位元組完全相同

### Requirement: Partime 章節
CASE 03 SHALL 是 Partime 個人工資管理工具，共 5 頁，依序為：封面、從試算表衍伸、適用情境、AI 協作流程、試用回饋。內容 SHALL 只圍繞三個重點：使用者只想知道每份工作賺多少（記帳軟體混了支出）、工具從試算表衍伸、適用「單一工作不同計算方式」與「身兼多職」兩種情境。封面 SHALL 只列專案時程（2026.06 — 至今，格式和其他案例相同）與使用工具（Claude Code・Open Spec・Impeccable）。每頁標題 SHALL 總結該頁要呈現的內容，不得使用沒有具體資訊的口號。從試算表衍伸那頁 SHALL 把試算表的每個問題和工具的做法一對一對應；從試算表衍伸那頁列出的工具優勢 MUST 是試算表做不到的。AI 協作流程 SHALL 以依序串接的流程呈現，每點擊一次出現一步，所有步驟使用相同樣式。試用回饋頁 SHALL 一致使用「週報表」這個名稱。

#### Scenario: 頁面順序
- **WHEN** 從 Partime 封面往後翻
- **THEN** 依序是從試算表衍伸、適用情境、AI 協作流程、試用回饋，接著是 CRM 章封面

#### Scenario: 封面欄位
- **WHEN** 顯示 Partime 封面
- **THEN** 只看到專案時程「2026.06 — 至今」與使用工具兩個欄位

#### Scenario: 試用回饋
- **WHEN** 顯示試用回饋頁
- **THEN** 依序串起「手機使用居多」→「週報表在手機上看得清楚、可單手操作」→「擴充權限功能，讓所有人都能自由登入使用」

### Requirement: Partime 不外流公司名稱
Partime 章節的文案與講稿 MUST NOT 包含應徵公司的名稱，也不得有針對特定公司的句子。大綱中提到應徵公司的那一句 MUST NOT 放進簡報。

#### Scenario: 搜尋公司名稱
- **WHEN** 在 `index.html` 與 `RyanChiang_presentation.notes.html` 搜尋大綱中出現的應徵公司名稱
- **THEN** 沒有結果

### Requirement: AI 應用組開場的流程總覽頁
簡報 SHALL 在 CRM 章節封面前放一頁 AI 協作流程泳道圖。小標是「AI WORKFLOW」，主標是「從需求到交付，AI 協作的五個階段」，副標是「每個階段由 AI 先產出，再由我決定方向與標準」，整頁為深色模式以區隔前面的 B2C 單元。版面為 5 個階段（需求整理、規格文件、UI 設計、原型、交付）橫向排列；階段名、AI 產出卡片、我的判斷卡片分成三列（卡片內不加標籤），各自獨立，箭頭只出現在兩列卡片之間，各格文案依 `AI workflow.md` 並經使用者修訂，每格約一行。這頁 SHALL NOT 出現在議程頁，也 SHALL NOT 使用案例編號。

#### Scenario: 位置
- **WHEN** 簡報從 B2C 組最後一章往下翻
- **THEN** 先出現流程總覽頁，下一頁才是 CRM 章節封面

#### Scenario: 議程不列
- **WHEN** 檢視議程頁
- **THEN** 議程只列出各案例章節，沒有流程總覽頁

#### Scenario: 判斷強調與逐步顯示
- **WHEN** 進入流程總覽頁並依序按下一步
- **THEN** 上方 5 個階段名一直顯示；下方兩列卡片依階段兩個一組出現（01–02、03–04、05，共 3 步），組內各階段的卡片依序由左向右滑入，不同時出現；「我的判斷」卡片為白底深字，比深灰的「AI 產出」卡片更突出

#### Scenario: 追問補充不上投影片
- **WHEN** 檢視本機講稿版
- **THEN** 講者備註包含主講稿，以及原型階段細部流程與設計稿階段的補充；公開版 `index.html` 不含這些備註，投影片上也不出現
