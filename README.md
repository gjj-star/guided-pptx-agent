# guided-pptx (Agent Skill)

跨平台交互式 PPT 需求澄清 skill。支持 Codex、Cursor、WorkBuddy、Qoderwork、Claude Code 等任何支持 Agent Skills 标准的工具。

## 快速安装

### Codex (OpenAI)

```bash
# 安装到用户全局
cp -r guided-pptx-agent ~/.agents/skills/guided-pptx

# 或安装到项目
cp -r guided-pptx-agent /your-project/.agents/skills/guided-pptx
```

然后说 `$guided-pptx` 或自然描述你的 PPT 需求即可触发。

### Cursor

```bash
# 方式 A: 作为 skill 安装
cp -r guided-pptx-agent /your-project/.cursor/skills/guided-pptx

# 方式 B: 将 AGENTS.md 放到项目根目录
cp guided-pptx-agent/AGENTS.md /your-project/AGENTS.md
```

方式 A 支持 skill 系统（按需加载，更省 context）。方式 B 最简单，任何项目直接生效。

### WorkBuddy

```bash
# 安装到用户全局
cp -r guided-pptx-agent ~/.workbuddy/skills/guided-pptx

# 或安装到项目
cp -r guided-pptx-agent /your-project/.agents/skills/guided-pptx
```

### Qoderwork

```bash
# 将 SKILL.md 内容粘贴为自定义 skill
# 或将 AGENTS.md 放到项目根目录
cp guided-pptx-agent/AGENTS.md /your-project/AGENTS.md
```

### Claude Code

```bash
cp -r guided-pptx-agent ~/.claude/skills/guided-pptx
```

注意：Claude Code 已有专用版本在 `../guided-pptx/SKILL.md`，支持 AskUserQuestion 原生交互。本版本为跨平台通用版。

## 使用方式

安装后，在任何支持的 AI agent 工具中说：

```
帮我做一个关于 AI Agent 的分享 PPT
```

Agent 会自动激活 guided-pptx，开始 3 轮结构化提问。你全程只需选选项，不需要写 prompt。

## 与其他 PPT 工具的关系

guided-pptx 只做一件事：**把模糊需求翻译成可执行规格**。它输出一份 Markdown 文档，你可以：

- 交给 Claude Code 的 pptx-generator 自动生成 PPTX
- 将规格内容逐页粘贴到 PowerPoint/Keynote/Canva
- 转为 JSON 后调用 python-pptx 等库
- 交给 Gamma、Beautiful.ai 等在线工具作为参考大纲

## 文件说明

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 完整版 skill（遵循 Open Agent Skills 标准） |
| `AGENTS.md` | 精简版（纯 markdown，适合放项目根目录） |
| `reference/expert-questions.md` | 19 个专家问题的完整推导 |
| `reference/minimal-questions.md` | 问题压缩策略和依赖分析 |
| `reference/question-flow.md` | 交互流程设计文档 |

## 与 Claude Code 专用版的关系

`../guided-pptx/SKILL.md` — Claude Code 专用，利用 AskUserQuestion 原生 UI。

`./SKILL.md` — 跨平台通用，用纯文本对话替代专有工具。

两者知识库共享 `reference/`，独立维护。
