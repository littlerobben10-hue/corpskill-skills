---
name: job-fit-evaluator
description: Score how well a candidate fits a job posting and decide whether to apply. Use when the user shares a job description (text or URL) together with their resume or background and asks "should I apply", "how good a fit am I", or wants a tailored pitch.
license: Apache-2.0
metadata:
  industry: careers
  scenario: job-search
  author: CorpSkill
  version: 0.1.0
---

# Job Fit Evaluator

Give a 1–5 fit score with evidence, the gaps that matter, and a go / no-go recommendation.

## Workflow

1. **Parse the job.** Extract title, seniority, location / remote policy, comp range if stated, must-have requirements, nice-to-haves, and signals about the team (stage, size, domain).
2. **Parse the candidate.** From the resume or the user's description, list skills, years per domain, notable outcomes (with numbers), and constraints (visa, location, salary floor) if known. Ask for the resume if neither is available — do not invent a background.
3. **Match requirement by requirement.** For each must-have mark ✅ met (cite resume evidence), 🟡 partial, or ❌ missing.
4. **Score** using the rubric. Any ❌ on a hard requirement (license, clearance, mandatory degree, location) caps the score at 2.
5. **Recommend.** Apply (≥4), apply with a tailored angle (3–3.9), or skip (<3). Give the single strongest angle to lead with and the gap to address proactively.

## Rubric (weights)

| Dimension | Weight |
|---|---|
| Must-have requirements met | 40% |
| Domain / industry relevance | 20% |
| Seniority match | 15% |
| Evidence of impact on similar problems | 15% |
| Logistics (location, visa, comp) | 10% |

## Output format

```
## <Title> @ <Company> — Fit 3.8 / 5 → Apply with angle

| Requirement | Match | Evidence |
|---|---|---|

**Lead with:** <one sentence>
**Address proactively:** <gap + how to frame it>
**Red flags in the posting:** <if any>
```

Keep it honest: a low score with clear reasons is more useful than an inflated one.
