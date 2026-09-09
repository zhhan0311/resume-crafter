# Resume Crafter — Hermes Agent / Claude Code Skill

---
name: resume-crafter
description: "用7个提示词模块拆解JD、分析匹配度、改写简历、生成求职策略。用户粘JD或说目标职位时触发。"
tags: [resume, career, jd, job-search]
---

# Resume Crafter — 7-Module Resume Optimization Engine

## When to use

- User pastes a JD → run Module 3 (Gap Analysis) + Module 5 (Rewriter)
- User asks "what else can I do" → Module 1 (Hidden Roles) + Module 2 (Transferable Skills)
- User wants to career-pivot → Module 7 (Pivot Map) + Module 4 (Industry Scanner)
- User wants a search plan → Module 6 (30-Day Strategy)

## Execution Flow

1. Read user resume (check `cv.md` in working dir or ask user)
2. Confirm target JD/role if needed
3. Call the appropriate module(s)
4. Output structured Chinese results (English terms OK for jargon)

## Rules

- NEVER fabricate experience, metrics, or qualifications
- Quantification: only use numbers from the original resume
- Bullet format: `Action Verb + Task + Quantified Result`
- Career summary: ≤ 150 words, highlight core match
- Modules 3 & 5 require a JD — ask for one if missing

## Module Quick Reference

| # | Module | Trigger | Needs JD? |
|---|--------|---------|-----------|
| 1 | Hidden Role Finder | "我能干什么" | No |
| 2 | Transferable Skills | "技能翻译" | No |
| 3 | Gap Analyzer | "差距分析"/"JD对比" | **Yes** |
| 4 | Industry Scanner | "行业扫描" | No |
| 5 | Resume Rewriter | "改简历"/"重写" | **Yes** |
| 6 | Search Strategy | "求职计划" | No |
| 7 | Career Pivot | "转行"/"pivot" | No |
