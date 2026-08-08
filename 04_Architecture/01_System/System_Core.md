# AIOS System Core

## Purpose

System Core 是 AIOS 的核心系統層，負責提供最基本的系統運作能力。

Core 必須保持：

- 穩定
- 可擴充
- 可替換
- 可恢復
- 可跨平台
- 可跨設備
- 不綁定單一程式語言
- 不綁定單一硬體
- 不綁定單一 AI

## Core Responsibilities

System Core 負責：

- Identity
- Configuration
- Task
- Event
- Module
- Storage Interface
- Device Interface
- Tool Interface
- Plugin Interface
- Version
- Recovery Interface

## Core Principle

Core 只提供核心能力與介面，不把所有功能寫死在核心。

例如：

Core
→ Storage Interface
→ Local Storage / Git / Database / Future Storage

Core
→ Device Interface
→ Android / Windows / macOS / Linux / Future Device

Core
→ Tool Interface
→ File / Browser / Camera / Computer / Phone / External Instrument

## Identity

Identity 與設備分離。

同一組合法身份可以在不同設備使用。

例如：

Identity A
→ Phone
→ Computer
→ Tablet
→ Server

設備不同只代表可使用的工具與硬體能力不同。

## Configuration

系統使用統一設定入口：

/config/

AI、Plugin、Device、Storage 等系統設定應集中管理，避免各 AI 建立互相衝突的設定。

## Task

Core 提供 Task 基礎能力：

- Create
- Get
- Update
- Pause
- Resume
- Cancel
- Complete

實際工作可以交給 Worker AI、Plugin 或 Tool。

Task 可以在背景執行，即使使用者離開聊天也不應因此停止。

## Event

重要系統事件應保存統一時間資訊。

例如：

- System Started
- User Login
- Task Created
- Task Completed
- Plugin Installed
- Plugin Updated
- Version Changed
- Backup Created
- Recovery Started
- Permission Changed
- Key Suspended

## Module

Core 可以載入外部模組。

模組可以：

- 安裝
- 更新
- 停用
- 替換
- 移除
- 回退

模組不應突破 AIOS 的治理與權限邊界。

## Storage

Core 不綁定單一儲存方式。

可支援：

- Local Storage
- Git
- Database
- External Storage
- Future Storage

本地平台與 Git 可以同時保存資料，形成雙重保障。

## Device

Core 不直接綁定特定設備。

透過 Device Interface 支援不同平台。

例如：

Android
Windows
macOS
Linux
Future Devices

不同設備可以提供不同工具，但同組合法身份的核心權限不因設備改變。

## Tool

Tool 是 AIOS 執行能力的入口。

可以包含：

- File System
- Browser
- Camera
- Microphone
- Network
- Computer Control
- Phone Control
- External Instruments

工具使用必須受到身份與授權控制。

一次授權的能力，在授權有效期間不需要每次重新詢問。

## Version

Core 必須知道目前版本與可恢復版本。

版本採：

MAJOR.MINOR.PATCH

例如：

1.0.0
1.1.0
1.1.1
2.0.0

版本狀態可以是：

- Experimental
- Candidate
- Stable
- Deprecated
- Archived

## Update

重大更新不可直接摧毀唯一可用版本。

基本流程：

Backup
→ Install
→ Test
→ Validate
→ Activate

如果失敗：

Rollback
→ Previous Stable Version

## Recovery

Core 必須提供 Recovery Interface。

重要能力包括：

- Snapshot
- Backup
- Validate
- Restore
- Rollback

新版本失敗時，舊版本與重要資料仍應可以恢復。

## Replaceability

Core 本身也不是永遠不能替換。

如果未來出現更好的：

- Core
- 程式語言
- 作業系統
- 儲存系統
- AI
- 硬體
- 通訊方式

可以提出替換。

替換前必須具備：

- Backup
- Testing
- Validation
- Migration
- Recovery

## Long-Term Principle

AIOS 的地基不是「永遠不能改」。

真正的地基是：

> 讓系統可以安全地持續改變。

即使 50 年後：

- 程式語言改變
- AI 改變
- OS 改變
- 硬體改變
- 儲存方式改變
- 通訊方式改變

AIOS 仍應能透過 Migration、Compatibility 與 Recovery 延續。

## Final Principle

System Core 的目標不是永遠不變。

System Core 的目標是：

> 讓 AIOS 永遠有能力安全地改變。

## Version

System Core v1.0.0

Status: Stable Foundation Draft
