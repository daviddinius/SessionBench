# Success Criteria

## Overview

This document defines what success looks like for SessionBench, across three goals:
1. Internal Validation
2. Marketing Evidence
3. Product Improvement

---

## Goal 1: Internal Validation

**Question:** Do these tools actually work?

### Primary Metrics

| Metric | Baseline Expected | Success Threshold |
|--------|-------------------|-------------------|
| **Decision Consistency** | ~50% | Context conditions: >80% |
| **TDD Compliance** | ~20% | Workflow conditions: >70% |
| **Feature Completion** | ~70% | Combined condition: >90% |
| **Token Efficiency** | Baseline | Context conditions: 30%+ reduction |

### Statistical Requirements

- At least 2 of 4 primary metrics show improvement
- p < 0.05 (statistically significant)
- Effect size Cohen's d > 0.5 (medium effect)

### What Would FAIL Validation

- No significant difference between conditions
- Improvement in <2 metrics
- High variance obscuring any signal
- Combined condition not better than individual tools

---

## Goal 2: Marketing Evidence

**Question:** What can we defensibly claim publicly?

### Defensible Claims (Examples)

If data supports:

> "In our 15-session benchmark, projects using ContextMap maintained
> architectural consistency 2x better than projects without context
> persistence tools."

> "Developers using workflow discipline tools (Superpowers) completed
> test-first implementations 3.5x more often than baseline."

> "Combined usage of context persistence and workflow discipline
> reduced total tokens spent by 35% while completing 20% more features."

### NOT Defensible

- Vague claims without numbers
- Extrapolation beyond what was measured
- Claims about project types not tested
- Promises ("will" instead of "did")

### Requirements for Marketing Claims

1. **Specific:** Numbers, not vague statements
2. **Measured:** Based on actual benchmark data
3. **Hedged:** "In our benchmark" not "universally"
4. **Reproducible:** Methodology published

### Documentation Required

For any public claim:
- Link to full methodology
- Raw data available
- Statistical analysis
- Acknowledged limitations

---

## Goal 3: Product Improvement

**Question:** How can we make the tools better?

### Insights to Capture

1. **Which failure modes persist despite tools?**
   - If context tools don't prevent Session 7 amnesia, why?
   - If workflow tools don't prevent TDD skipping, when/why?

2. **Where do users struggle despite tools?**
   - Sessions with highest failure rates
   - Common error patterns

3. **Tool usage patterns**
   - Which ContextMap files are referenced?
   - Which Superpowers skills are invoked vs. skipped?
   - Unused features

4. **Token consumption patterns**
   - Where do tokens spike?
   - What context is loaded unnecessarily?

### Actionable Insights Threshold

**Success:** Identify at least 3 concrete improvements with evidence

Example insights:
- "Session 7 (theme system) had 60% amnesia rate even with ContextMap - need better template engine documentation prompts"
- "TDD skipping spiked in Session 9 (debugging) - Superpowers should have debugging-specific TDD reminders"
- "Token usage 40% higher in Sessions 10-15 - context pruning needed for later sessions"

### Improvement Prioritization

For each insight, document:
- **Evidence:** What data shows this?
- **Impact:** How many sessions/runs affected?
- **Effort:** How hard to fix?
- **Priority:** High/Medium/Low

---

## Overall Success Definition

### Minimum Success (Validation)

- [ ] Completed 300 sessions (4 conditions × 5 runs × 15 sessions)
- [ ] 2+ primary metrics show significant improvement (p < 0.05)
- [ ] Combined condition outperforms individual tools

### Good Success (Marketing)

All of minimum, plus:
- [ ] 3+ primary metrics show significant improvement
- [ ] Effect sizes medium or large (d > 0.5)
- [ ] Clean narrative for public claims
- [ ] Methodology reviewable

### Excellent Success (Publication)

All of good, plus:
- [ ] Pre-registered hypotheses confirmed
- [ ] Second operator verification
- [ ] External review of methodology
- [ ] Academic collaborator sign-off
- [ ] Paper-ready analysis

### Failure Conditions

The experiment fails if:
- [ ] Unable to complete runs (technical issues)
- [ ] No significant differences between any conditions
- [ ] High variance makes all results inconclusive
- [ ] Major methodology flaws discovered post-hoc

---

## Hypotheses (For Pre-Registration)

### H1: Context Persistence

**Hypothesis:** ContextMap will improve decision consistency compared to baseline.

- **Metric:** Decision drift score
- **Expected effect:** d > 0.5
- **Direction:** ContextMap conditions > non-ContextMap conditions

### H2: Workflow Discipline

**Hypothesis:** Superpowers will reduce TDD skipping compared to baseline.

- **Metric:** Test-before-implementation rate
- **Expected effect:** d > 0.8
- **Direction:** Superpowers conditions > non-Superpowers conditions

### H3: Synergy

**Hypothesis:** Combined tools will outperform either tool alone on feature completion.

- **Metric:** Features completed out of 15
- **Expected effect:** d > 0.3 vs. best single-tool condition
- **Direction:** Combined > max(Context-only, Workflow-only)

### H4: Efficiency

**Hypothesis:** Context persistence reduces total tokens spent.

- **Metric:** Total tokens across 15 sessions
- **Expected effect:** 20%+ reduction
- **Direction:** ContextMap conditions < non-ContextMap conditions

### Analysis Plan

- 2×2 ANOVA with Context and Workflow as factors
- Planned contrasts for each hypothesis
- Bonferroni correction for multiple comparisons
- Report effect sizes (Cohen's d) for all comparisons
