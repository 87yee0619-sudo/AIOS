# AIOS System Data

## Purpose

本文件定義 AIOS 的基礎資料架構。

AIOS 的資料不只是檔案。

資料包含：

- Knowledge
- Memory
- Configuration
- Identity
- Key Metadata
- Task
- Event
- Version
- File
- AI Output
- Evidence
- Reasoning Trace
- Governance Data
- System State
- Device State

## Core Principle

資料必須：

- 可保存
- 可搜尋
- 可同步
- 可版本化
- 可備份
- 可恢復
- 可移動
- 可重新整理
- 可長期演化

資料結構不應綁死於單一資料庫、檔案格式或程式語言。

## Data Layers

AIOS 資料可以分為：

1. Foundation Data
2. System Data
3. Identity Data
4. Configuration Data
5. Operational Data
6. Knowledge Data
7. Reasoning Data
8. Governance Data
9. Archive Data

## Foundation Data

Foundation Data 是系統長期存在的基礎資料。

例如：

- Core Principles
- Architecture Principles
- Identity Structure
- Governance Structure
- Naming Rules
- Version Rules

這類資料的變更需要較高層級的治理流程。

## System Data

System Data 描述 AIOS 本身。

例如：

- Installed Components
- Services
- Modules
- Plugins
- Devices
- System Version
- System State

## Identity Data

Identity Data 描述身份。

包括：

- Identity ID
- Identity Level
- Parent Identity
- Child Identity
- Key Status
- Scope
- Creation Time
- Version
- Relationship

Identity Data 不等同於使用者的所有私人內容。

## Key Metadata

Key 本身應與 Key Metadata 分離。

Metadata 可以包含：

- Key ID
- Identity ID
- Level
- Scope
- Status
- Created At
- Suspended At
- Revoked At
- Parent
- Children
- Device Associations

實際 Secret 不應以明文形式任意保存。

## Configuration Data

Configuration 可以包含：

- System Config
- AI Config
- Device Config
- Tool Config
- Plugin Config
- Network Config
- Storage Config
- Task Config

Configuration 必須支援版本。

## Operational Data

Operational Data 是系統日常運作產生的資料。

例如：

- Task
- Event
- Log
- Notification
- Device State
- Service State

## Task Data

Task 至少應保存：

- Task ID
- Source
- Destination
- Creator
- Created Time
- Start Time
- Completion Time
- Priority
- Status
- Result
- Error
- Related Files

## Task Status

Task 可以具有：

- Created
- Queued
- Running
- Paused
- Waiting
- Completed
- Failed
- Cancelled
- Recovering
- Archived

## Event Data

Event 至少包含：

- Event ID
- Event Type
- Timestamp
- Source
- Identity
- Related Task
- Related Device
- Result
- Severity

## Knowledge Data

Knowledge Data 用於保存 AIOS 長期累積的知識。

包括：

- Facts
- Concepts
- Research
- Evidence
- Conclusions
- Open Questions
- Unsolved Seeds

## Reasoning Data

AIOS 不只保存答案，也可以保存：

- Question
- Initial Understanding
- Assumptions
- Wrong Assumptions
- Corrections
- Evidence
- Reasoning Trace
- Final Understanding
- Principles Derived
- Open Questions

目標是保存：

> 知識是如何被得到的。

## Evidence

重要結論應可以連結到 Evidence。

Evidence 可以來自：

- Documents
- Websites
- Experiments
-
