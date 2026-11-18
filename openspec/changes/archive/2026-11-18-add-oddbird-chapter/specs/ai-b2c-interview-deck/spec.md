## MODIFIED Requirements

### Requirement: 章節結構與順序
主線 SHALL 依序包含：封面、關於我、議程、案例一（選址決策工具）、案例二（Echorise）、AI 協作流程總覽頁、第三章（證券業 CRM 的 AI 原型工作流）、第四章（AI × Storybook）、第五章（Partime 個人工資管理工具）、第六章（OddBird 羽球場地排點與計分工具）、收尾。簡報 MUST NOT 包含「視覺與素材設計」段落、整合行銷內部管理系統的頁面，也不得有附錄。

#### Scenario: 章節順序
- **WHEN** 從第一頁依序翻到最後一頁
- **THEN** 依序是封面、關於我、議程、CASE 01、CASE 02、流程總覽頁、CASE 03（CRM）、CASE 04（Storybook）、CASE 05（Partime）、CASE 06（OddBird）、收尾，後面沒有任何附錄頁

#### Scenario: 已刪除的內容
- **WHEN** 在發佈的 HTML 裡搜尋「視覺與素材」「GoBridge」「LPG」「整合行銷」「附錄」
- **THEN** 都沒有結果

### Requirement: 兩組敘事分組
議程頁 SHALL 把六章分成三組呈現：「B2C 產品設計」（01、02）、「AI 應用」（03、04）、「Side Project」（05、06）。案例之間 MUST NOT 有額外的轉場頁；流程總覽頁不算轉場頁。

#### Scenario: 議程分組
- **WHEN** 顯示議程頁
- **THEN** 「B2C 產品設計」下列出選址、Echorise，「AI 應用」下列出 CRM、Storybook，「Side Project」下列出 Partime、OddBird；每章都有標題與一行說明，點擊後會跳到該章封面

#### Scenario: 不加轉場頁
- **WHEN** 從 Storybook 最後一頁翻到下一頁
- **THEN** 直接顯示 Partime 章封面

### Requirement: 第三章沿用 CRM 案例
CRM 章 SHALL 包含封面與 4 頁內容（挑戰、AI 分工、驗證方式、推動採用與成果），不含設計決策頁。驗證方式頁 MUST NOT 有「驗收時發現」段落；成果頁 SHALL 只用放大的時程圖呈現提前天數，不另列數字文字。章節標示 SHALL 是「CASE 03」，頁面 MUST NOT 有附錄的標記或樣式。

#### Scenario: 不再是附錄
- **WHEN** 顯示 CRM 章任一頁
- **THEN** 不會出現「附錄」字樣，頁碼與進度條和主線連續，總覽裡沒有附錄的虛線標記

#### Scenario: 成果數字保留
- **WHEN** 顯示 CRM 章成果頁
- **THEN** 時程圖顯示 Phase 1／2／3 分別提前 1／5／7 天，圖上方沒有另外的數字文字

### Requirement: 第四章 AI × Storybook
Storybook 章（CASE 04）SHALL 呈現為一套工作流程的示範，不是專案：用 Claude Code 透過 Figma MCP 讀取 Figma 設計稿的 design system，轉成 Storybook，以提升 AI 協作開發的準確性。內容依序是封面、兩個用途、架構、六步閉環、角色與影響。封面 SHALL 只列主要職責與使用工具（Figma、Figma MCP、Claude Code、Storybook），並使用 BatchExportDialog 文件頁截圖。這一章 MUST NOT 顯示元件數、頁面數或展示網址。

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

#### Scenario: 章節標示
- **WHEN** 顯示 Storybook 章封面
- **THEN** 章節標示是「CASE 04」

### Requirement: Partime 章節
CASE 05 SHALL 是 Partime 個人工資管理工具，共 5 頁，依序為：封面、從試算表衍伸、適用情境、AI 協作流程、試用回饋。內容 SHALL 只圍繞三個重點：使用者只想知道每份工作賺多少（記帳軟體混了支出）、工具從試算表衍伸、適用「單一工作不同計算方式」與「身兼多職」兩種情境。封面 SHALL 只列專案時程（2026.06 — 至今，格式和其他案例相同）與使用工具（Claude Code・Open Spec・Impeccable）。每頁標題 SHALL 總結該頁要呈現的內容，不得使用沒有具體資訊的口號。從試算表衍伸那頁 SHALL 把試算表的每個問題和工具的做法一對一對應；從試算表衍伸那頁列出的工具優勢 MUST 是試算表做不到的。AI 協作流程 SHALL 以依序串接的流程呈現，每點擊一次出現一步，所有步驟使用相同樣式。試用回饋頁 SHALL 一致使用「週報表」這個名稱。

#### Scenario: 頁面順序
- **WHEN** 從 Partime 封面往後翻
- **THEN** 依序是從試算表衍伸、適用情境、AI 協作流程、試用回饋，接著是 OddBird 章封面

#### Scenario: 封面欄位
- **WHEN** 顯示 Partime 封面
- **THEN** 只看到專案時程「2026.06 — 至今」與使用工具兩個欄位

#### Scenario: 試用回饋
- **WHEN** 顯示試用回饋頁
- **THEN** 依序串起「手機使用居多」→「週報表在手機上看得清楚、可單手操作」→「擴充權限功能，讓所有人都能自由登入使用」

## ADDED Requirements

### Requirement: OddBird 章節
CASE 06 SHALL 是 OddBird 羽球場地排點與計分工具，共 4 頁，依序為：封面、功能、即時同步、迭代歷程。封面副標 SHALL 以「一位主辦在紀錄台用單一裝置操作、球員用手機查看」為情境，MUST NOT 強調多位管理員或多裝置操作；封面 SHALL 只列專案時程（2026.09 — 至今）與使用工具（Claude Code・Impeccable・Supabase），並使用紀錄台賽程看板截圖。每頁標題 SHALL 涵蓋該頁所有重點，不得使用口號。功能頁 SHALL 呈現自由安排、自動輪替、場邊即時提醒三項功能（含掃 QR code 免登入、只能查看），各附截圖，MUST NOT 包含比賽紀錄與成績統計。即時同步頁 SHALL 只講紀錄台變動同步到球員手機與連線狀態。迭代歷程頁 SHALL 只描述各階段新增的功能，MUST NOT 出現改版次數或日期，並附名人堂與分享 QR code 截圖。這一章 MUST NOT 有獨立的「AI 協作流程」頁。

#### Scenario: 頁面順序
- **WHEN** 從 OddBird 封面往後翻
- **THEN** 依序是功能、即時同步、迭代歷程，接著是收尾頁

#### Scenario: 功能截圖
- **WHEN** 顯示功能頁並點擊到最後一步
- **THEN** 看得到自由安排、自動輪替、場邊即時提醒三張截圖，沒有比賽紀錄或成績統計的畫面，且離線也能顯示

### Requirement: OddBird 不虛構成效
OddBird 章節 MUST NOT 出現使用人數、場次、滿意度、改版次數等沒有來源或不適合當指標的數據。

#### Scenario: 搜尋數據
- **WHEN** 檢查 OddBird 各頁
- **THEN** 頁面上沒有人數、場次、改版次數或日期區間
