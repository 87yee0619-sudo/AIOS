# 01 Governance

Governance 定義 AIOS 中「誰可以做什麼、誰對誰負責、權限如何授予，以及權限如何被限制」。

Governance 不應綁定特定：

- AI
- 程式語言
- 作業系統
- 裝置
- 金鑰實作方式
- 身分驗證技術
- 雲端服務
- 儲存平台

未來可以替換技術實作，但治理關係必須保持可辨識、可驗證、可演化與可回退。

---

## Current Version

AIOS Governance v1.0.0

Main document:

`AIOS-Governance-v1.0.0.md`

---

## Core Governance Structure

目前治理層級：

- Level 1 — Root Governor
- Level 2A — Delegated Shared Identity
- Level 2B — Independent Branch Governor
- Level 3 — Governance Assistance Layer
- Level 4 — AI / Agent / Execution Layer
- Level 5 — Reserved
- Level 6 — Reserved

Level 5 與 Level 6 暫時保留。

保留代表尚未定義，而不是未來不能使用。

---

## Evolution

Governance 可以修改、擴充或重新設計。

但是治理變更必須：

1. 有明確版本。
2. 保留必要歷史。
3. 可以追蹤變更原因。
4. 可以在重大錯誤時回退。
5. 不得由低權限角色自行提升自己的治理權限。
