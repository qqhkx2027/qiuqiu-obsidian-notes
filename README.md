# 秋秋 Obsidian 笔记助手

把主题、文章、剪藏或已有笔记整理成可链接、可行动、可持续迭代的 Obsidian 笔记。

当前版本支持从 0 到 1 规划 Obsidian 文件夹、首页工作台、KOS 样式、七节常青笔记卡片、知识库双向链接，以及芒格多元思维模型自动打标。

## 核心能力

- 将一个概念整理成七节常青卡片。
- 从文章、剪藏或已有笔记中提炼公共知识。
- 搜索知识库已有卡片并建立真实 `[[双向链接]]`。
- 使用芒格多元思维模型格栅自动生成 `tags`。
- 参考现有 Vault 的目录和笔记，从 0 到 1 生成文件夹结构预览。
- 根据真实目录生成首页工作台，并建立可验证的导航入口。
- 生成或更新根目录 `kos.css`，提供 KOS 视觉规范和安全差异预览。
- 安全新建或增量更新 Markdown 文件。
- 保留用户填写的私人内化、来源、批注和现有链接。

## 七节常青卡片

固定结构：

1. 问题（Problem）
2. 概念（Concept）
3. 关系（Relation）
4. 案例（Example）
5. 行动（Action）
6. 边界（Boundary）
7. 内化（Insight）

前六节由 AI 提炼公共知识；第七节始终保留给用户填写：

> AI 提炼公共知识，你沉淀私人知识。

## 芒格心智模型标签

常青卡片完成后，技能会强制调用心智模型打标流程：

```text
提取核心观点与机制
→ 判断底层学科
→ 筛选1–5个规范标签
→ 写入YAML的tags
```

示例：

```yaml
tags: [心智模型/微观经济学, 心智模型/复杂系统与决策科学]
```

标签按底层规律分类，不按“AI文章、跑步文章、商业文章”等表面主题分类。技能内置 15 个规范学科标签，不会创建单独的 `mental_models` 属性。

## 使用示例

只生成内容，不保存：

```text
使用 $qiuqiu-obsidian-notes，把“机会成本”制作成一张 Obsidian 常青笔记卡片，先不保存。
```

生成并保存：

```text
使用 $qiuqiu-obsidian-notes，把“费曼学习法”制作成常青卡片并保存。
```

从素材生成：

```text
使用 $qiuqiu-obsidian-notes，把下面这篇文章整理成常青卡片并归档：[粘贴文章]
```

只给已有笔记打标签：

```text
使用 $qiuqiu-obsidian-notes，给“03-Resources/Evergreen/机会成本.md”添加芒格心智模型标签，只修改YAML。
```

从现有笔记规划文件夹：

```text
使用 $qiuqiu-obsidian-notes，参考我的 Obsidian 笔记，从 0 到 1 规划文件夹结构，先只输出预览，不要创建。
```

确认后创建缺失文件夹：

```text
确认创建上一步规划的文件夹，只创建缺失目录，不移动或重命名现有笔记。
```

生成首页工作台：

```text
使用 $qiuqiu-obsidian-notes，参考我的 Obsidian 笔记生成首页工作台，先输出 Markdown 预览，不要写入。
```

生成 KOS 样式：

```text
使用 $qiuqiu-obsidian-notes，参考我的首页和笔记风格设计 kos.css，先输出 CSS 和差异说明，不要写入。
```

## 默认 Obsidian 约定

- 常青卡片保存到 `03-Resources/Evergreen/`。
- 文件名等于核心词，不添加日期、序号或冗余后缀。
- 正文不重复添加与文件名相同的一级标题。
- YAML 使用 `name`、`description`、`category`、`tags`、`source`、`status`。
- 双链只指向真实存在或用户明确计划创建的笔记。
- 同名文件存在时不得静默覆盖。

## 文件结构

```text
qiuqiu-obsidian-notes/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── evergreen-card.md
    ├── mental-model-tags.md
    └── obsidian-standards.md
```

- `SKILL.md`：触发规则、模板路由与安全写入流程。
- `evergreen-card.md`：七节常青卡片模板和质量门禁。
- `mental-model-tags.md`：15 个芒格多元思维模型标签及判断流程。
- `obsidian-standards.md`：YAML、双链、命名与更新规范。
- `vault-bootstrap.md`：从现有 Vault 推断并安全创建文件夹结构的流程。
- `home-dashboard.md`：首页工作台的信息架构与安全写入规则。
- `kos-css.md`：KOS `kos.css` 的样式方向、覆盖范围与验收规则。

默认识别的编号式结构也包括 `04-Archives/`，用于存放已完成、暂不活跃但仍需保留的项目与资料。

## 校验

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```
