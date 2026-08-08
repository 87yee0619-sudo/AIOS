# AIOS System Security

## Purpose

本文件定義 AIOS 的基礎安全架構。

AIOS Security 的目標不是阻止所有變化，而是在平台可以持續擴充、替換與演化的情況下，保護：

- Identity
- Key
- Permission
- Data
- System
- Device
- AI
- Tool
- Plugin
- Governance

## Core Principle

AIOS 必須同時做到：

> 可以自由擴充，但不能透過擴充突破權限邊界。

安全系統不應把所有功能鎖死。

安全應該保護：

- 誰可以做什麼
- 誰不能做什麼
- 發生問題時如何發現
- 發現後如何通知
- 發生錯誤時如何恢復

## Security Layers

基本安全架構：

Identity
→ Authentication
→ Authorization
→ Execution Control
→ Monitoring
→ Recovery

每一層負責不同工作。

## Authentication

Authentication 用於確認：

> 目前使用 AIOS 的人或系統是不是所宣稱的身份。

可以使用：

- Key
- Password
- Device Authentication
- Hardware Authentication
- Future Authentication

未來可以增加新的 Authentication 方法。

## Key

Key 是身份進入 AIOS 的重要憑證。

Key 必須具備：

- Identity
- Level
- Scope
- Status
- Creation Time
- Version
- Relationship
- Recovery Information

Key 不應只是一段單純文字。

## Key Status

Key 可以具有：

- Active
- Suspended
- Revoked
- Archived

### Active

可以正常使用。

### Suspended

暫停使用。

資料與身份關係保留。

### Revoked

永久取消該 Key 的使用資格。

資料仍不代表必須被刪除。

### Archived

長期保存但目前不使用。

## Authorization

Authentication 確認：

> 你是誰。

Authorization 確認：

> 你可以做什麼。

兩者必須分離。

## Least Privilege

一般身份只應取得完成工作所需的能力。

但 AIOS 不應把此原則解釋成：

> 所有人都只能做很少的事情。

真正目的為：

> 權限必須與身份與工作範圍一致。

## Level 1 Security

Level 1 是最高管理身份。

任何其他身份不得：

- 超越 Level 1
- 建立另一個最高身份
- 移除 Level 1
- 修改 Level 1 的最高權限
- 解除 Level 1 與其下層平台的關係
- 偽造 Level 1
- 阻止 Level 1 的合法管理能力

## Level 2 Security

Level 2 的安全邊界依其類型不同。

### Level 2A

Level 2A 可以使用被授權的平台與資料。

Level 2A 不自行決定 Level 1 的：

- 核心更新
- 核
