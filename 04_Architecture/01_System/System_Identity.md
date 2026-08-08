# AIOS System Identity

## Purpose

本文件定義 AIOS 的身份、設備身份與金鑰身份的基本架構。

AIOS 的身份系統必須支援：

- 多設備
- 多身份
- 跨設備使用
- 金鑰授權
- 權限分級
- 身份停權
- 身份恢復
- 長期演化
- 平台擴充

## Core Principle

身份與設備分離。

設備只是使用 AIOS 的載體，不代表身份本身。

因此：

同一個合法身份
→ Android 手機
→ Windows 電腦
→ macOS 電腦
→ Tablet
→ Server

都可以使用同一身份。

設備不同時，主要差異是設備本身能提供的工具與硬體能力。

## Identity

AIOS 的身份代表「誰正在使用平台」。

身份可以擁有：

- 身份等級
- 金鑰
- 授權
- 可使用工具
- 可使用設備
- 資料範圍
- 管理範圍
- 狀態

身份狀態可以包含：

- Active
- Suspended
- Revoked
- Archived

## Level 1

Level 1 是 AIOS 的最高管理身份。

Level 1 擁有平台最高權限。

Level 1 可以：

- 建立金鑰
- 授權金鑰
- 撤銷金鑰
- 停權金鑰
- 恢復金鑰
- 決定重大更新
- 決定重大安裝
- 決定平台架構變更
- 決定治理規則
- 決定平台擴充
- 決定平台替換
- 管理最高權限

Level 1 不應被任何其他身份取代或超越。

## Level 1 Across Devices

Level 1 金鑰不是綁定單一設備。

只要使用合法的 Level 1 金鑰登入：

Phone A
→ Level 1

Computer B
→ Level 1

Tablet C
→ Level 1

這些設備都具有相同的 Level 1 身份權限。

設備本身的能力可以不同，但身份權限不因設備改變。

## Level 2

Level 2 是由 Level 1 授權的身份。

Level 2 分為不同型態。

主要包含：

- Level 2A
- Level 2B

兩者用途不同。

## Level 2A

Level 2A 屬於 Level 1 的授權範圍。

Level 2A 可以使用 Level 1 平台所提供、培養與擴充的資料與能力。

Level 2A 主要定位為：

> 被授權使用平台，而不是建立另一個獨立平台。

Level 2A 不需要自行決定平台重大更新或安裝。

重大更新與重大安裝由 Level 1 決定。

Level 2A 主要負責使用。

如果需要新的功能或平台能力，可以提出需求，由下層工作系統整理後向上回報。

## Level 2B

Level 2B 是 Level 1 授權建立的獨立發展身份。

Level 2B 可以透過自己的金鑰在不同設備使用。

例如：

Phone
→ Level 2B

Computer
→ Level 2B

Tablet
→ Level 2B

只要使用同一組 Level 2B 金鑰，身份權限保持一致。

## Level 2B Independent Platform

Level 2B 可以擁有自己的：

- 資料
- AI
- Tool
- Plugin
- Module
- Research
- 擴充內容
- 本地平台環境

Level 2B 可以在自己的範圍內發展。

但是：

> Level 2B 不是另一個 Level 1。

Level 2B 的平台仍然存在於 Level 1 授權架構之下。

## Level 2B Expansion

Level 2B 可以擴充自己的平台。

例如：

Level 2B
→ 新增 AI
→ 新增 Tool
→ 新增 Module
→ 新增資料
→ 新增功能
→ 新增設備支援

Level 2B 的發展不應因為 Level 1 不需要知道一般工作內容而被不必要限制。

## Level 2B Key Creation

Level 2B 可以依照被授予的規則建立其下層金鑰。

但其建立範圍必須受到自身身份樹限制。

Level 2B 不得建立另一個脫離自身管理範圍的 Level 2B。

Level 2B 可以建立其下層允許的身份，例如：

Level 2B
→ Level 3 / Level 4 等工作身份

具體可建立的身份等級由 Governance 定義。

## No Privilege Escalation

任何身份都不能透過修改自己的資料、程式、Plugin 或金鑰來提升至 Level 1。

例如：

Level 2B
→ 修改 Key
→ Level 1

此行為必須被禁止。

同樣禁止：

- 移除 Level 1
- 修改 Level 1
- 解除自身與 Level 1 的關係
- 建立替代 Level 1
- 偽造最高權限
- 屏蔽 Level 1 的管理能力

## Key Suspension

Level 1 可以停權下層金鑰。

停權的意思是：

> 停止使用權限，而不是刪除資料。

因此：

Suspend
≠
Delete

被停權身份的：

- 資料
- 歷史
- 設定
- 研究
- 建立內容
- 金鑰關係

仍然可以保留。

## Descendant Suspension

如果 Level 2B 被 Level 1 停權：

Level 2B
→ A1
→ A2
→ A3

其管理範圍內的下層金鑰可以同步進入停權狀態。

例如：

B1 被停權
→ B1 的下層全部停止

B1 恢復後，是否恢復下層身份由 Level 1 決定。

## Key Revocation

撤銷與停權不同。

Suspended：

暫時停止使用。

Revoked：

永久取消該金鑰的有效性。

但即使撤銷金鑰，也不代表自動刪除其歷史資料。

## Recovery

被停權或撤銷的身份資料仍應可以被 Recovery 系統保存與恢復。

是否恢復使用權限，必須依照治理規則決定。

## Cross-Device Data

同一身份可以跨設備取得自己的合法資料。

例如：

Phone A
→ 要求 AIOS
→ Computer B
→ 取得資料
→ 傳回 Phone A

或：

Phone A
→ 指示 Computer B
→ 執行下載
→ 結果同步回 Phone A

跨設備操作必須遵守身份權限。

## Device Equality

同一組金鑰在不同設備登入時：

身份權限相同。

設備差異只影響：

- 硬體
- Tool
- OS
- UI
- 本地能力

例如：

手機可能可以使用：

Camera
GPS
Microphone

電腦可能可以使用：

File System
Browser
Development Tools

這些是設備能力差異，不是身份等級差異。

## One-Time Authorization

需要設備能力授權時，可以採一次授權模式。

例如：

Level 1 授權某個身份使用某項設備能力。

在授權仍有效且沒有被撤銷的情況下：

不需要每次重新詢問。

授權狀態必須可以被管理、撤銷與恢復。

## Identity Tree

AIOS 身份應形成清楚的上下關係。

例如：

Level 1
│
├── Level 2A
│
└── Level 2B
    ├── Child A
    ├── Child B
    └── Child C

下層身份的權限不能超越父層。

任何身份都不能超越 Level 1。

## Hidden Governance Monitoring

與身份相關的重要違規行為可以由獨立的治理監控機制偵測。

一般工作內容不應因此全部暴露給 Level 1。

監控系統主要負責：

- 發現重大違規
- 發現權限提升
- 發現金鑰篡改
- 發現治理繞過
- 發現非法解除關係
- 發現 Level 1 權限遭到影響

如果發現重大違規：

→ 產生事件
→ 通知 Level 1
→ 依規則處理

## Privacy Boundary

Level 1 不應因為擁有最高權限，就必然看到 Level 2B 的所有日常內容。

Level 2B 可以在授權範圍內獨立發展。

但涉及核心治理與四項最高限制的違規事件，必須能被治理系統發現並通知 Level 1。

## Long-Term Principle

身份系統必須能持續演化。

未來可以增加：

- 新身份類型
- 新授權方式
- 新設備
- 新金鑰形式
- 新驗證方式

但任何新增身份都不能破壞：

> Level 1 是最高權限。

## Final Principle

AIOS 的身份設計必須同時做到：

> 權限可以集中管理，發展可以保持自由。

Level 1 保持最高管理權。

Level 2B 可以在自己的範圍內自由發展。

下層身份可以持續擴充。

但任何身份都不能超越 Level 1。

## Version

System Identity v1.0.0

Status: Foundation Draft
