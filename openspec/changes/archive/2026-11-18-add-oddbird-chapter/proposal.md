# Proposal

## Why

OddBird（羽球場地排點與計分工具）是第二個用 AI 協作做出的 side project，目前不在簡報裡。另外，Partime 現在夾在正式案例中間，使「正式工作 → side project」的敘事不連貫，所以要一起調整章節順序。

## What Changes

- 新增 OddBird 章節（4 頁）：封面、功能（自由安排、自動輪替、場邊即時提醒）、即時同步、迭代歷程
- 調整章節順序：案例一 → 案例二 → AI 流程總覽頁 → CRM → Storybook → Partime → OddBird → 收尾
- 重新編號：CRM 改成 CASE 03、Storybook 改成 CASE 04、Partime 改成 CASE 05、OddBird 為 CASE 06
- 議程頁改成三組：B2C 產品設計（01、02）、AI 應用（03、04）、Side Project（05、06）
- OddBird 截圖取自線上檢視頁 `https://oddbird.vercel.app/v/9ebdca6f-d5f7-4275-bcc3-bab01dc53c18`
- 重新 build 公開版、講稿版，並重新匯出 PDF

## Capabilities

### New Capabilities
（無）

### Modified Capabilities
- `ai-b2c-interview-deck`：修改章節順序、議程分組、CRM、Storybook、Partime 的章節編號；新增 OddBird 章節與 OddBird 不虛構成效兩條需求

## Impact

- `deck/_tools/build.py`（頁面內容）、`deck/_tools/notes.py`（講稿）
- 新增素材 `deck/_assets/oddbird/`
- 產出物：`index.html`、`RyanChiang_presentation.notes.html`、`presentation/*.pdf`
- `Partime.md` 開頭的擺放位置說明要更新
