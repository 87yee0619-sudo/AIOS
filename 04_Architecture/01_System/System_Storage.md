# AIOS System Storage

## Purpose

本文件定義 AIOS 的儲存架構。

Storage 的目的不是綁定某一種資料庫或檔案系統，而是讓 AIOS 能夠長期保存、管理、同步、備份、恢復與遷移資料。

## Core Principle

AIOS 不綁定單一 Storage。

可以使用：

- Local Storage
- File System
- Git
- Database
- External Storage
- Network Storage
- Cloud Storage
- Future Storage Technology

基本結構：

AIOS
→ Storage Interface
→ Storage Implementation

## Storage Independence

上層系統不應直接依賴某一種 Storage。

例如：

AIOS Core
→ Storage Interface
→ Git

未來可以：

AIOS Core
→ Storage Interface
→ New Storage

因此更換 Storage 不應要求整個 AIOS 重寫。

## Storage Types

### Local Storage

用於：

- 系統資料
- 本地檔案
- Cache
- Work Memory
- Device-specific Data

### Git Storage

Git 可以保存：

- 程式碼
- 文件
- Configuration
- Architecture
- Version History
- AIOS Development History

Git 是一種 Storage / Version Implementation，而不是 AIOS 永久地基。

### Database

Database 可以保存：

- Metadata
- Index
- Task
- Event
- Identity Metadata
- Search Data
- Structured Knowledge

### External Storage

可以連接：

- Network Storage
- Cloud Storage
- External Drive
- Other AIOS
- Future Storage System

## Storage Scope

資料可以具有不同 Scope：

- System
- Identity
- Group
- Device
- Project
- Task
- Shared
- Private
- Temporary

Storage 必須保存 Scope 資訊。

## Storage Metadata

重要資料應具有：

- Data ID
- Storage ID
- Path
- Type
- Size
- Hash
- Version
- Created Time
- Modified Time
- Source
- Owner / Scope

## Storage Identity

資料不應只依賴 Path 判斷身份。

例如：

/project/file.md

Path 可以改變。

因此資料應具有獨立的 Data ID。

## Storage Path

Path 是資料的位置，而不是資料本身的永久身份。

例如：

Old Path
→ /project/a/file.md

可以變成：

New Path
→ /archive/project/a/file.md

Data ID 不應因此改變。

## File Organization

Storage 應支援：

- Rename
- Move
- Copy
- Merge
- Split
- Archive
- Restore

檔案重新整理不能破壞資料身份。

## Naming

Storage 中的檔案必須遵守 AIOS Naming Convention。

避免不同 AI 使用完全不同的命名方式。

例如：

AI A：

result.md

AI B：

final_result.md

AI C：

final_result_v2_final.md

這會造成長期管理困難。

應由：

Naming Convention
+
Secretary
+
Integrator

協助統一。

## Version Storage

重要資料應可以保存版本。

例如：

File
→ v1.0
→ v
