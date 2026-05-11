---
description: 分析代码库并创建中文版 CLAUDE.md 文件
argument-hint: [路径]
allowed-tools: Read, Glob, Grep, Bash, Write, Edit
---

# 初始化 CLAUDE.md (中文版)

分析当前代码库并创建 CLAUDE.md 文件，所有内容使用中文。

## 执行步骤

1. **发现项目结构**
   - 查找主要源代码目录和文件类型
   - 识别项目类型（Delphi、Python、Java、Node.js 等）
   - 查找构建配置文件（.dpr、package.json、pom.xml 等）

2. **分析构建和测试命令**
   - 查找构建脚本和配置
   - 识别测试框架和测试命令
   - 查找 lint/格式化工具

3. **理解架构**
   - 分析核心模块和它们的职责
   - 识别关键入口点
   - 发现重要的设计模式或约定

4. **生成 CLAUDE.md**
   - 使用中文编写所有内容
   - 包含必要的编译/构建命令
   - 描述项目架构
   - 记录非显而易见的模式和约定
   - 不包含显而易见的通用建议

## 输出格式

生成的 CLAUDE.md 必须以以下内容开头：

```
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.
```

## 内容要求

**必须包含（如适用）：**
- 项目概述（一句话描述）
- 编译/构建命令
- 测试运行方式
- 核心架构说明
- 编码规范或约定（项目特有的）
- 非显而易见的陷阱或注意事项

**不应包含：**
- 通用的开发最佳实践
- 显而易见的说明
- 详细的文件列表（可通过探索发现）
- 敏感信息（API密钥、密码等）

## 示例模板

```markdown
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

此文件为Claude AI编程助手（claude.ai/code）在使用本仓库中的代码时提供指导。

## 项目概述

<一句话描述项目用途>

## 编译命令

| 命令 | 说明 |
|------|------|
| `<构建命令>` | 构建/编译项目 |
| `<测试命令>` | 运行测试 |
| `<其他命令>` | 其他操作 |

## 架构

```
<项目结构说明>
```

## 关键文件

- `<文件路径>` - <用途说明>

## 编码规范

- <项目特有约定>

## 注意事项

- <非显而易见的陷阱>
```

## 使用方式

```
/init-zh
/init-zh /path/to/project
```