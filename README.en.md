# Academic Research Skills for Claude Code

[![Version](https://img.shields.io/badge/version-v3.9.4.2-blue)](https://github.com/Imbad0202/academic-research-skills/releases/tag/v3.9.4.2)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Sponsor](https://img.shields.io/badge/sponsor-Buy%20Me%20a%20Coffee-orange?logo=buy-me-a-coffee)](https://buymeacoffee.com/crucify020v)

[English](README.en.md) · [简体中文](README.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja-JP.md)

> **AI is your copilot, not the pilot.** This tool won't write your paper for you. It handles the grunt work — hunting down references, formatting citations, verifying data, checking logical consistency — so you can focus on the parts that actually require your brain: defining the question, choosing the method, interpreting what the data means, and writing the sentence after "I argue that."

---

## What is this project?

**Academic Research Skills (ARS)** is a comprehensive suite of [Claude Code](https://claude.ai/install.sh) skills for academic research, covering the full pipeline from literature search to publication.

### Four Core Modules

| Module | What it does | AI Agents |
|--------|-------------|:---------:|
| **Deep Research** | Literature search, systematic review, fact-checking, Socratic guided research | 13 |
| **Academic Paper** | Outline planning, drafting, revision, format conversion (LaTeX/APA/IEEE, etc.) | 12 |
| **Academic Paper Reviewer** | Multi-perspective peer review simulation (Editor-in-Chief + reviewers + Devil's Advocate) | 7 |
| **Academic Pipeline** | 10-stage orchestrator connecting all modules above | Orchestrator |

### Human-in-the-loop, not full automation

ARS is built on the premise that **a human researcher augmented by AI avoids failure modes better than either alone**. Built-in integrity gates automatically check for fabricated references, claim-citation alignment, statistical errors, logical consistency, and temporal integrity.

---

## Quick Install

**Prerequisites:** [Claude Code](https://claude.ai/install.sh) (v3.7.0+) with `ANTHROPIC_API_KEY` configured.

**Option 1: Plugin (recommended)**

In Claude Code:
```text
/plugin marketplace add Imbad0202/academic-research-skills
/plugin install academic-research-skills
```

**Option 2: Traditional clone**
```bash
git clone https://github.com/Imbad0202/academic-research-skills.git ~/ars
cd /path/to/your/project
mkdir -p .claude/skills
ln -s ~/ars/deep-research .claude/skills/deep-research
ln -s ~/ars/academic-paper .claude/skills/academic-paper
ln -s ~/ars/academic-paper-reviewer .claude/skills/academic-paper-reviewer
ln -s ~/ars/academic-pipeline .claude/skills/academic-pipeline
```

**Verify:** Run `/ars-plan` in Claude Code and describe a paper you're working on.

---

## Usage Examples

```text
# Full pipeline
"I want to write a complete research paper on AI's impact on higher education"

# Socratic guided research
"Guide my research on AI in educational evaluation"

# Literature review
"Do a literature review on demographic decline"

# Review an existing paper
"Review this paper" (then provide the paper)

# Check pipeline status
"status"
```

---

## In-depth Reading

| Document | Content |
|----------|---------|
| [Architecture docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) | Pipeline flow, stage matrix, data flow, quality gates |
| [Setup Guide docs/SETUP.md](docs/SETUP.md) | Five installation methods, Pandoc/tectonic config, cross-model verification |
| [Performance docs/PERFORMANCE.md](docs/PERFORMANCE.md) | Token budgets, cost estimates (~$4-6 per full paper), Claude Code settings |
| [Quick Start QUICKSTART.md](QUICKSTART.md) | 3-step quick start |
| [Changelog CHANGELOG.md](CHANGELOG.md) | Version history and detailed changes |
| [Design Docs docs/design/](docs/design/) | Specs and technical decisions per release |
| [Showcase examples/showcase/](examples/showcase/) | Real pipeline output (paper PDFs, review reports, integrity reports) |

---

## Features

- **7 research modes**: full, quick, systematic-review, socratic, fact-check, lit-review, review
- **Multi-format output**: APA 7.0 / Chicago / MLA / IEEE / Vancouver; Markdown / DOCX / LaTeX / PDF
- **Multi-perspective review**: EIC + 3 dynamic reviewers + Devil's Advocate, 0-100 scoring
- **Integrity assurance**: reference verification, claim-citation alignment, statistical error detection, temporal integrity audit
- **Cross-model verification** (optional): second AI model independently validates results
- **Multi-language**: Traditional Chinese and English by default; Socratic mode works in any language
- **Style calibration**: learns your academic voice from past writing
- **Writing quality check**: detects machine-generated patterns

---

## Companion Tools

| Tool | Purpose |
|------|---------|
| [Experiment Agent](https://github.com/Imbad0202/experiment-agent) | Run experiments between ARS Stage 1 and Stage 2 |
| [Codex CLI Distribution](https://github.com/Imbad0202/academic-research-skills-codex) | Codex-native packaging of the same workflows |

---

## Glossary

| Term | Meaning |
|------|---------|
| Agent | An AI role responsible for a specific task |
| Skill | Claude Code skill package containing agent definitions and trigger rules |
| Pipeline | End-to-end workflow from research to publication |
| Material Passport | A record of all literature sources used in research |
| Stage 2.5 / 4.5 | Mandatory integrity verification gates |

---

## License

CC-BY-NC 4.0. Attribution format:
```
Based on Academic Research Skills by Cheng-I Wu
https://github.com/Imbad0202/academic-research-skills
```

## Contributors

**Cheng-I Wu** (吳政宜) — Author and maintainer. See [CONTRIBUTING.md](CONTRIBUTING.md).
