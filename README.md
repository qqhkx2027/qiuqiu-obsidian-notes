# 秋秋 Obsidian 笔记助手

一个面向个人知识库的 Obsidian skill。它陪你从第一次打开 Vault 开始，逐步建立文件夹、首页、笔记、链接、标签和视觉样式。

调用方式：

```text
使用 $qiuqiu-obsidian-notes，……
```

## 如果你是第一次使用 Obsidian

不要一开始就设计复杂系统，按下面顺序做：

1. **先看清现状**：确认 Vault 在哪里、已有多少笔记、正在使用什么主题和插件。
2. **建立最小结构**：先规划目录，不急着移动旧笔记；确认后只创建缺失目录。
3. **做一个首页**：用 `00-Home.md` 作为入口，链接到真实存在的目录和索引。
4. **记录第一条笔记**：从一个问题、一篇文章或一个想法开始，不要求一次整理完美。
5. **把重要主题变成常青卡片**：使用七节模板，让知识可以复习和复用。
6. **补充链接与心智模型标签**：连接已有知识，再把底层学科写入 `tags`。
7. **最后再美化**：结构稳定后再设计首页布局和 `kos.css`。

可以直接从这句话开始：

```text
使用 $qiuqiu-obsidian-notes，我是 Obsidian 新手，请先扫描我的 Vault，告诉我现状和最小可行的文件夹结构，只输出规划，不要创建。
```

## 适合做什么

| 功能 | 结果 | 默认位置 |
| --- | --- | --- |
| 常青笔记 | 七节知识卡片，保留最后一节供你内化 | `03-Resources/Evergreen/` |
| 心智模型打标 | 将模型标签写入现有 YAML 的 `tags` | 原笔记 |
| 文件夹规划 | 根据真实 Vault 生成目录预览 | Vault 根目录 |
| 首页工作台 | 生成可导航的首页 Markdown | `00-Home.md` |
| KOS 样式 | 设计或更新 `kos.css` | Vault 根目录 |
| 系统守则分析 | 按健康 → 生活 → 价值分析决策与困惑 | 对话输出 |

## 五项核心能力

### 1. 七节常青笔记

每张卡片只解释一个可以独立命名的概念，固定包含：

1. 问题（Problem）
2. 概念（Concept）
3. 关系（Relation）
4. 案例（Example）
5. 行动（Action）
6. 边界（Boundary）
7. 内化（Insight）

前六节由 AI 提炼公共知识，第七节留给你填写自己的理解、经历和迁移。AI 不代写私人内化。

### 2. 芒格多元思维模型标签

常青卡片完成后，会先分析核心机制，再从 15 个规范学科中选择最多 3–5 个标签，写入原有 YAML 的 `tags`：

```yaml
tags:
  - 心智模型/微观经济学
  - 心智模型/复杂系统与决策科学
```

不新增 `mental_models` 属性，也不按“AI文章、商业文章”等表面主题强行分类。

### 3. 从 0 到 1 规划 Vault

技能会先读取现有目录、笔记数量和代表性笔记，再区分“已存在、建议新增、需要决定”的目录。默认识别的编号结构包括：

```text
00-Attachments/   附件与素材
01-Projects/      进行中的项目
02-Areas/         持续维护的领域
03-Resources/     可复用知识与资料
04-Archives/      已完成但仍需保留的内容
05-Agents/        技能与自动化
```

规划不会自动移动、重命名或删除笔记。只有你明确确认后，才创建缺失文件夹。

### 4. 首页工作台

根据真实目录和常用索引生成 `00-Home.md`，通常包含项目、领域、资源、归档、Agents、常青卡片和收件箱等入口。只链接到真实存在的文件或文件夹，不为了视觉效果创建空文件。

### 5. KOS CSS

检查现有主题和 CSS snippets 后，生成或更新 Vault 根目录的 `kos.css`。默认使用 Obsidian CSS 变量、低饱和色彩和 `.kos-*` 前缀，并提供差异预览，不静默覆盖已有样式。

### 6. 秋秋笔记系统守则

分析决策和困惑时，遵循：

```text
健康 > 生活 > 价值
```

先定位主线和领域，再对照领域基本事实，检查三线耦合，给出判断，最后追问缺失信息。11 个领域包括运动、饮食、睡眠、情绪、家庭、社群、体验、休闲、财务、工作和学习。

直接使用：

```text
使用 $qiuqiu-obsidian-notes，分析我是否应该接这个新项目。
```

## 直接复制使用

### 制作常青卡片

```text
使用 $qiuqiu-obsidian-notes，把“机会成本”制作成一张 Obsidian 常青笔记卡片，先不保存。
```

### 从文章整理笔记

```text
使用 $qiuqiu-obsidian-notes，把下面这篇文章整理成常青卡片并保存：[粘贴文章]
```

### 给已有笔记打标签

```text
使用 $qiuqiu-obsidian-notes，给“03-Resources/Evergreen/机会成本.md”添加芒格心智模型标签，只修改 YAML。
```

### 规划并创建文件夹

```text
使用 $qiuqiu-obsidian-notes，参考我的 Obsidian 笔记，从 0 到 1 规划文件夹结构，先只输出预览，不要创建。
```

确认后：

```text
确认创建上一步规划的文件夹，只创建缺失目录，不移动或重命名现有笔记。
```

### 生成首页工作台

```text
使用 $qiuqiu-obsidian-notes，参考我的 Obsidian 笔记生成首页工作台，先输出 Markdown 预览，不要写入。
```

### 设计 KOS 样式

```text
使用 $qiuqiu-obsidian-notes，参考我的首页和笔记风格设计 kos.css，先输出 CSS 和差异说明，不要写入。
```

## 安全规则

- 默认先输出内容或预览；用户明确要求保存后才写入文件。
- 同名文件存在时先展示差异，不静默覆盖。
- 不删除、移动、批量重命名或合并已有笔记。
- 双链只指向真实存在或用户明确计划创建的目标。
- 不把 `.obsidian/`、`.git/`、`.trash/`、缓存和凭据当作知识内容分析。
- 更新 `kos.css` 时不修改第三方主题文件，也不删除已有 CSS 规则。

## 默认约定

- 文件名使用核心词，不添加日期、序号或冗余后缀。
- 正文不重复添加与文件名相同的一级标题。
- YAML 沿用知识库已有字段：`name`、`description`、`category`、`tags`、`source`、`status`。
- 首页默认写入 Vault 根目录 `00-Home.md`；已有首页时先合并规划，不直接覆盖。

## 文件结构

```text
qiuqiu-obsidian-notes/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── evergreen-card.md
    ├── mental-model-tags.md
    ├── vault-bootstrap.md
    ├── home-dashboard.md
    ├── kos-css.md
    ├── system-rules.md
    └── obsidian-standards.md
```

## 校验

在技能目录执行：

```bash
python3 tools/validate_skill.py .
```
