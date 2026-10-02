# geodaoyu-skills

Personal collection of agent skills — plain `SKILL.md` bundles, not tied to any single agent.

Each skill is just a directory with a `SKILL.md` (YAML frontmatter: `name` + `description`, then the instructions). Any agent that understands the Agent Skills convention can load them, including **Claude Code** and **DeepSeek (DSH)**.

## Skills

### ramda

Ramda functional programming library skill. Provides guidance on function selection, common patterns, anti-patterns, and design philosophy for the Ramda library (272 auto-curried, data-last functions).

Trigger: mention of Ramda, Ramda functions (R.map, R.pipe, R.lens, etc.), point-free JavaScript, or functional programming with Ramda.

### trip-packing-list

出差行李清单 skill。以长期维护的基础清单（工作 / 生活 / 现场购买 三类）为骨架，按出差季节、天数、目的地天气和行程性质做裁剪与补充，输出可直接勾选的 Markdown 清单。

Trigger: 出差、要带什么、行李清单、打包、收拾行李、出差准备、packing list。

### weekly-report

个人周报 skill。扫描配置的 GitLab 目录，按本人身份（`--author`）过滤本周提交，结合用户补充的会议、面试等非编码工作，输出「本周完成工作 / 本周工作总结 / 下周工作计划」结构的周报；支持 monorepo 按子应用（scope）拆分。

Trigger: 周报、本周完成、工作总结、写周报、生成周报。

### project-report

项目报告 skill。只统计用户给定路径下的项目（不会再自己去 GitLab 目录里遍历），且包含项目内**全部成员**的提交，输出「本周进展 / 风险问题 / 下周计划」三段式的项目维度报告——只看项目推进到哪了，不写是谁做的。默认本周，支持上周、近两周、指定区间；monorepo 按子应用（scope）前缀归类，并用文件路径复核伪 scope。

Trigger: 项目报告、项目周报、项目进展、项目汇报、项目这周做了什么、统计某项目本周的提交。

### jiangnan

江南文风写作 skill。两种用法：**给大纲 → 成文**（补齐第一画面 / 代价 / 信物，按片段、短篇、中篇三档骨架写，贯穿画面先行、缺失驱动、反差构图、信物、时间折叠、不说破六条内核）；**给现成文字 → 润色**（去锚定 → 冗余切除 → 句式注入 → 通感激活 → 软转折加固，只改质感不动骨架）。带 `references/` 句式库、通感对照表、慎用词表与两个完整范例。**只借文风，不涉及任何具体作品的角色、设定或续写。**

Trigger: 江南风格、江南文风、江南体、用江南的笔法写、模仿江南、润色成江南风格、悲壮热血、少年感文字、画面感强的小说，或"照这个大纲写成故事""把这段改得更有画面感 / 更催泪"。

## Installation

Copy the skill directory into your agent's skills folder. For example, with Claude Code or DeepSeek (DSH):

```bash
# Claude Code
cp -r ramda ~/.claude/skills/

# DeepSeek (DSH)
cp -r ramda ~/.dsh/skills/
```

Or just point your agent at this repo — skills can also be discovered from a project or custom skill root, so you can drop a skill directory (or symlink it) wherever your setup scans. No code, no build step, no dependencies.
