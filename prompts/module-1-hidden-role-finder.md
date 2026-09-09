# Module 1: Hidden Role Finder (隐藏角色搜索器)

## Prompt

```
分析我的简历并识别15个与我的经验、技能、成就和可转移能力相匹配的职位名称。包括我当前行业之外的角色。

请按以下维度对每个职位分类：
1. 契合度（高 / 中 / 低）
2. 薪资潜力（给出范围，标注货币）
3. 市场需求（热 / 稳 / 冷）
4. 进入难度（易 / 中 / 难）

对每个职位，用一句话说明为什么我的简历经历与之匹配。

最后给出一个总结：哪些方向值得优先探索，原因是什么。
```

## Output Format

```markdown
| # | 职位名称 | 契合度 | 薪资潜力 | 需求 | 难度 | 匹配理由 |
|---|---------|--------|---------|------|------|---------|
| 1 | ...     | 高     | 20-30w  | 热   | 易   | ...     |

### 总结
优先探索方向：...
```

## Notes

- Output in Chinese (keep English for role titles if industry standard)
- Include roles outside the user's current industry to expand horizons
- If the user has a clear target field (e.g., hardware PM), weight related roles higher
