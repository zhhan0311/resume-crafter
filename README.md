# Resume Crafter 🔧

> 7-module AI resume optimization engine — paste a JD, get a targeted resume + action plan in minutes.

一个由 AI 驱动的7模块简历定制系统。粘贴岗位 JD，即可获得针对性的简历优化方案、差距分析和求职行动计划。

---

## ✨ Features

| # | Module | What It Does |
|---|--------|-------------|
| 1 | **Hidden Role Finder** | 分析简历，识别15个匹配职位（含行业外机会），按契合度/薪资/需求/难度分类 |
| 2 | **Transferable Skills Translator** | 提取20-30项可迁移技能，映射到具体行业、部门和职位 |
| 3 | **Qualification Gap Analyzer** | 逐条对比简历 vs 目标 JD，输出满足/部分满足/缺失清单 + 弥补建议 |
| 4 | **Industry Scanner** | 识别10个适配行业，按招聘热度/薪资/远程潜力/成长空间/进入难度评分 |
| 5 | **Resume Rewriter** | 重写职业概述和经历要点，适配目标角色，保留事实、只改表述 |
| 6 | **Job Search Strategist** | 生成30天求职计划：职位标题、关键词、企业名单、申请目标、每周检查点 |
| 7 | **Career Pivot Map** | 5条职业转型路线：初始角色、可迁移经验、缺失技能、30天过渡计划 |

## 🚀 Quick Start

### Prerequisites

- An AI tool that supports system prompts (ChatGPT / Claude / Hermes Agent / etc.)
- Your resume in plain text or Markdown format

### Usage

**Option 1: Direct Prompt (any AI tool)**

Copy the prompt from `prompts/module-N.md` → paste into your AI chat along with your resume → get results.

**Option 2: Hermes Agent Skill**

```bash
# Copy to your Hermes skills directory
cp -r prompts/ ~/.hermes/skills/resume-crafter/
# Then use in Hermes chat:
# "帮我看看这个JD" → auto-runs Module 3 + Module 5
# "我能干什么工作" → runs Module 1 + Module 2
# "帮我做求职计划" → runs Module 6
```

**Option 3: Claude Code / Cursor / Aider**

Drop `SKILL.md` into your project's `.claude/` or equivalent directory. The AI will follow the 7-module workflow automatically.

## 📂 Project Structure

```
resume-crafter/
├── README.md              # This file
├── LICENSE                # MIT License
├── SKILL.md               # Hermes Agent / Claude Code skill file
├── prompts/               # 7 standalone prompt templates
│   ├── module-1-hidden-role-finder.md
│   ├── module-2-transferable-skills.md
│   ├── module-3-gap-analyzer.md
│   ├── module-4-industry-scanner.md
│   ├── module-5-resume-rewriter.md
│   ├── module-6-search-strategy.md
│   └── module-7-career-pivot.md
├── templates/             # Output format templates
│   ├── role-table.md
│   ├── skills-matrix.md
│   ├── gap-report.md
│   ├── industry-table.md
│   ├── rewritten-resume.md
│   ├── weekly-plan.md
│   └── pivot-cards.md
└── examples/              # Example outputs
    └── sample-gap-report.md
```

## 🧭 Workflow Guide

### When to use which module

| Your situation | Recommended modules |
|---------------|-------------------|
| 粘了一个 JD，想看匹配度 | **3** → **5** |
| 不知道还能干什么 | **1** → **2** |
| 想转行但没方向 | **7** → **4** |
| 准备投简历 | **5** → **6** |
| 全面了解自己 | **2** → **1** → **4** → **7** |

### Module Execution Rules

- **Modules 3 & 5 require a JD** — the system will ask for one if not provided
- **Never fabricate** experience, metrics, or qualifications
- **Quantification rule**: only use numbers already in the resume; if no number exists, use descriptive language
- **Format rule**: each bullet point follows `Action Verb + Task + Quantified Result`
- **Summary cap**: career summary ≤ 150 words, must highlight core match to target role

## 📋 Output Examples

### Module 3: Gap Analysis (excerpt)

```
✅ 已满足：
- 3年以上嵌入式开发经验 → ✅ 有聚光科技PCBA制造实习+实验室嵌入式项目
- 熟悉Linux开发环境 → ✅ 课程项目涉及Linux驱动开发

⚠️ 部分满足：
- 产品需求文档撰写能力 → ⚠️ 有技术文档经验，但非标准PRD格式

❌ 缺失：
- 硬件产品经理相关实习经历 → 🔧 建议：研二暑期投硬件PM实习，同步做产品分析side project

综合匹配度：68%
```

## 🛠 Customization

### Adapt to your field

Each prompt template has a `[CUSTOMIZE]` section at the bottom. Edit it to:

- Add industry-specific terminology
- Adjust evaluation dimensions (e.g., add "visa sponsorship" for overseas job search)
- Change output language (Chinese ↔ English)

### Integrate with career-ops

If you're using [career-ops](https://github.com/career-ops-hq/career-ops), this skill complements it:

- **career-ops** handles: PDF generation, application tracking, company research
- **resume-crafter** handles: JD analysis, resume content optimization, skill translation

## 📄 License

MIT — use it, fork it, improve it. A star ⭐ would be nice.

## 🤝 Contributing

Issues and PRs welcome. If you add a new module, follow the existing format in `prompts/` and add the output template in `templates/`.
