# Interactive English Lesson Builder

一个面向英语教师的 Codex Skill，用于将静态英语教案逐步改造成可直接用于课堂投屏的互动 HTML 页面。

它不会直接跳到代码生成，而是按照“教案诊断 → 活动设计 → UI 设计 → 开发生成”的流程推进。每个阶段结束后都会暂停，等待教师确认或修改，确保互动设计真正服务于教学目标。

## 适用场景

- 将已有英语教案改造成互动课堂活动
- 为词汇、语法、阅读、听力、口语、写作或复习环节设计互动
- 为公开课、常态课或课堂展示制作互动页面
- 生成无需安装、浏览器直接打开的单文件 HTML

## 核心特点

- **教学目标优先**：互动必须服务于具体教学目标
- **保留原教案结构**：不强制套用模板或重写整份教案
- **教师全程掌控**：每个阶段确认后才进入下一阶段
- **单环节推进**：每次只设计和生成一个互动教学环节
- **投屏优先设计**：强调大屏可读、层级清晰和适度动效
- **原生 HTML 输出**：CSS 与 JavaScript 内嵌，默认不依赖外部资源

## 工作流程

### Phase 1：诊断与分析

分析教师提供的旧教案，识别：

- 原教案结构
- 学情与学段适配
- 教学目标
- 教学法建议
- 各环节互动潜力
- 优先改造环节

教师选择一个教学环节并确认后，进入下一阶段。

### Phase 2：活动与交互设计

围绕选定环节，按照以下逻辑设计互动：

```text
教学内容类型 → 具体教学目标 → 互动机制 → 活动方案
```

Skill 会提供最佳方案、备选方案 A 和备选方案 B，并说明教学目标匹配、课堂组织、预计时长和风险点。

### Phase 3：UI 与交互规范

根据学段、课堂场景和活动类型制定 UI Design Specification，包括视觉风格、页面结构、核心组件、交互反馈、动效和禁止项。

### Phase 4：开发与生成

1. 生成完整的 Master Game Generation Prompt，并等待教师确认。
2. 教师确认后，生成可直接运行的单文件 HTML，并完成教学、功能、投屏和可编辑性自检。

## 安装

将仓库克隆到 Codex 的个人 Skills 目录：

```bash
git clone https://github.com/joyzhu871208/interactive-english-lesson-builder.git ~/.codex/skills/interactive-english-lesson-builder
```

安装后建议新建一个 Codex 对话，使 Skill 被重新发现。

## 使用方法

在 Codex 中直接调用：

```text
使用 $interactive-english-lesson-builder 帮我把这份英语教案改造成互动 HTML 页面。
```

然后上传或粘贴旧教案。Skill 会从 Phase 1 开始，不会在未经确认的情况下跳到后续阶段。

也可以这样开始：

```text
请使用英语教案互动化改造 Skill，先诊断这份八年级英语阅读课教案。
```

## 支持的教学内容

- Vocabulary（词汇）
- Grammar（语法）
- Reading（阅读）
- Listening（听力）
- Speaking（口语）
- Writing（写作）
- Review（综合复习）

## 项目结构

```text
interactive-english-lesson-builder/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── html-quality-checklist.md
    └── output-templates.md
```

- `SKILL.md`：Skill 的核心工作流程与执行规则
- `agents/openai.yaml`：Codex UI 中显示的名称、简介与默认提示词
- `references/output-templates.md`：各阶段输出模板
- `references/html-quality-checklist.md`：HTML 页面生成后的质量检查清单

## 设计原则

1. 互动服务于教学目标，而不是单纯追求趣味。
2. 不是所有教学环节都必须互动化。
3. 页面应现代、清晰、精致，避免杂乱、低幼和过度炫技。
4. 教师可以在每个阶段确认、修改或推翻方案。

## 更新已安装的 Skill

进入 Skill 目录并拉取最新版本：

```bash
cd ~/.codex/skills/interactive-english-lesson-builder
git pull
```
