## MODIFIED Requirements

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

## ADDED Requirements

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
