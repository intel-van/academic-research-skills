# Academic Research Skills (ARS)

[![Version](https://img.shields.io/badge/version-v3.9.4.2-blue)](https://github.com/Imbad0202/academic-research-skills/releases/tag/v3.9.4.2)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Sponsor](https://img.shields.io/badge/sponsor-Buy%20Me%20a%20Coffee-orange?logo=buy-me-a-coffee)](https://buymeacoffee.com/crucify020v)

[English](README.en.md) · [简体中文](README.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja-JP.md)

> **AI 是你的副驾驶，不是机长。** 这个工具不会替你写论文。它处理脏活——搜文献、排格式、验数据、查逻辑一致性——让你专注在真正需要思考的事上：定义问题、选择方法、解读数据、写出「我认为」后面那句话。

---

## 这个项目是做什么的？

**Academic Research Skills (ARS)** 是一套运行在 [Claude Code](https://claude.ai/install.sh) 上的学术研究工具包。它把论文写作的全流程拆成四个核心模块，每个模块都由多个 AI Agent（智能体）组成，协同完成研究任务。

### 四个核心模块

| 模块 | 功能 | AI Agent 数量 |
|------|------|:---:|
| **Deep Research**（深度研究） | 文献搜索、系统性回顾、事实核查、苏格拉底式引导研究 | 13 个 |
| **Academic Paper**（论文撰写） | 大纲规划、初稿写作、修订优化、格式转换（LaTeX/APA/IEEE 等） | 12 个 |
| **Academic Paper Reviewer**（论文审稿） | 模拟期刊审稿流程，含主编 + 多角度审稿人 + 魔鬼代言人 | 7 个 |
| **Academic Pipeline**（全流程调度） | 把以上三个模块串成 10 个阶段的完整流水线 | 编排器 |

### 核心理念：人机协作，而非全自动

Lu 等人（2026, *Nature* 651:914-919）发表的 **The AI Scientist** 是第一个全自动 AI 研究系统。他们自己的 Limitations 章节列出了这类系统会遇到的失败模式：实现错误、幻觉结果、方法论伪造、引用幻觉等。

ARS 建立在这个前提上：**人类研究者 + AI 的组合，比纯自动或纯人工更能避开这些陷阱**。

项目内置了多道「学术诚信闸门」，在关键阶段自动检查：
- 引用是否真实存在
- 论文中的论断是否被引用的文献真正支持
- 统计方法是否正确
- 逻辑是否一致
- 时序是否合理（引用时间不早于被引文献发表时间）

---

## 快速安装

**前提条件：** 已安装 [Claude Code](https://claude.ai/install.sh)（v3.7.0+）并配置 `ANTHROPIC_API_KEY`。

**方式一：Plugin 安装（推荐）**

在 Claude Code 中执行：

```text
/plugin marketplace add Imbad0202/academic-research-skills
/plugin install academic-research-skills
```

**方式二：传统 clone 安装**

```bash
git clone https://github.com/Imbad0202/academic-research-skills.git ~/ars
cd /path/to/your/project
mkdir -p .claude/skills
ln -s ~/ars/deep-research .claude/skills/deep-research
ln -s ~/ars/academic-paper .claude/skills/academic-paper
ln -s ~/ars/academic-paper-reviewer .claude/skills/academic-paper-reviewer
ln -s ~/ars/academic-pipeline .claude/skills/academic-pipeline
```

**验证安装：** 在 Claude Code 中运行 `/ars-plan`，描述你想写的论文，ARS 会开始苏格拉底式对话帮你规划章节。

---

## 使用示例

```text
# 启动完整研究流水线
"我想做一篇关于 AI 对高等教育影响的论文"

# 苏格拉底引导式研究
"引导我研究 AI 在教育评估中的应用"

# 文献回顾
"帮我做关于少子化影响的文献回顾"

# 审稿
"帮我审查这篇论文"（然后提供论文内容）

# 查看进度
"进度"
```

---

## 深度阅读

| 文档 | 内容 |
|------|------|
| [架构全景 docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) | 全流程架构图、阶段矩阵、数据流向、质量闸门 |
| [安装指南 docs/SETUP.md](docs/SETUP.md) | 五种安装方式详解、Pandoc/tectonic 配置、跨模型验证 |
| [性能与费用 docs/PERFORMANCE.md](docs/PERFORMANCE.md) | Token 预算、费用估算（完整论文约 $4-6）、Claude Code 设置建议 |
| [快速入门 QUICKSTART.md](QUICKSTART.md) | 三步快速上手 |
| [变更日志 CHANGELOG.md](CHANGELOG.md) | 版本历史与详细改动 |
| [设计文档 docs/design/](docs/design/) | 各版本的设计规格与技术决策 |
| [实际产出展示 examples/showcase/](examples/showcase/) | 真实 pipeline 运行的完整产出（含论文 PDF、审稿报告、诚信报告） |

---

## 功能特色

- **定制化研究**：7 种研究模式（完整、快速、系统性回顾、苏格拉底引导、事实核查、文献回顾、研究质量审查）
- **多格式论文撰写**：APA 7.0 / Chicago / MLA / IEEE / Vancouver，支持 Markdown / DOCX / LaTeX / PDF 输出
- **多角度审稿**：主编 + 3 位动态审稿人 + 魔鬼代言人，0-100 质量评分
- **学术诚信保障**：引用真实性验证、论断与引用一致性检查、统计错误检测、时序完整性审计
- **跨模型验证**（可选）：用第二个 AI 模型交叉验证结果
- **多语言支持**：默认支持繁体中文和英文，苏格拉底模式支持任意语言
- **风格校准**：从你过去的写作中学习你的学术风格
- **写作质量检查**：识别让文字读起来像机器生成的模式

---

## 搭配工具

| 工具 | 作用 |
|------|------|
| [Experiment Agent](https://github.com/Imbad0202/experiment-agent) | 在 ARS Stage 1（研究）和 Stage 2（写作）之间执行实验、验证结果 |
| [Codex CLI 版](https://github.com/Imbad0202/academic-research-skills-codex) | 用 Codex CLI 的替代分发版 |

---

## 术语说明

| 术语 | 含义 |
|------|------|
| Agent | AI 智能体，负责某个特定任务的 AI 角色 |
| Skill | Claude Code 技能包，包含 Agent 定义和触发规则 |
| Pipeline | 流水线，从研究到出版的完整流程 |
| Material Passport | 材料护照，记录研究中使用的所有文献来源 |
| Stage 2.5 / 4.5 | 学术诚信检查闸门，不可跳过 |

---

## 授权条款

本作品采用 [CC-BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) 授权。

**署名格式：**
```
Based on Academic Research Skills by Cheng-I Wu
https://github.com/Imbad0202/academic-research-skills
```

---

## 贡献者

**吴政宜** (Cheng-I Wu) — 作者与维护者

感谢所有 [贡献者](https://github.com/Imbad0202/academic-research-skills/graphs/contributors) 的参与。详见 [CONTRIBUTING.md](CONTRIBUTING.md)。
