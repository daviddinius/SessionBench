# Provenance

This document traces the origins of SessionBench and the research insights that shaped its design.

---

## Origin

SessionBench was developed in January 2026 to address a critical gap in AI coding assistant evaluation: **no existing benchmark measures multi-session performance**.

Current benchmarks (SWE-bench, HumanEval, MBPP) evaluate single-shot code generation. But real software development happens across multiple sessions over days or weeks. The failure modes that matter most—context loss, decision drift, workflow degradation—are invisible to single-session metrics.

---

## Research Foundation

### The Gap We Identified

| Finding | Implication |
|---------|-------------|
| 65% of developers cite context as their biggest pain point with AI tools (Qodo 2025) | Context persistence is the dominant problem |
| METR randomized controlled trial found Cursor made experienced developers 19% slower | Single-session productivity gains don't translate to real-world improvement |
| No published benchmark tests multi-session AI coding performance | Genuine research gap—first-mover opportunity |
| Existing frameworks (SpecKit, OpenSpec, BMAD) make claims without empirical validation | Industry needs rigorous measurement |

### Key Insights

| Insight | Source | Impact on Design |
|---------|--------|------------------|
| Context persistence reduces failure rates 54% → 16% | [Research Landscape Analysis](https://github.com/daviddinius/ContextMap/blob/main/research/ai_developer_tools_research_landscape.md) | Justified testing context tools as independent variable |
| TDD reduces defects 40-90% (Nagappan et al. 2008) | [Literature Review](https://github.com/daviddinius/ContextMap/blob/main/research/context-engineering-literature-review.md) | Justified testing workflow discipline as independent variable |
| Token ROI estimated 10:1, Time ROI 27:1 for context persistence | [ContextMap Analysis](https://github.com/daviddinius/ContextMap/blob/main/README.md) | Hypotheses H1 and H4 |
| Combined tools may show synergy effects | Theoretical analysis | Hypothesis H3 |

---

## Design Decisions

### Why 2×2 Factorial Design

Testing Context Persistence (ContextMap) and Workflow Discipline (Superpowers) as independent factors allows us to:
- Isolate the effect of each tool
- Detect interaction effects (synergy or interference)
- Make specific, defensible claims about each intervention

### Why 15 Sessions

| Consideration | Decision |
|---------------|----------|
| Long enough to surface amnesia/drift | Sessions 7, 9, 12 specifically target memory of earlier decisions |
| Short enough to complete multiple runs | 5 runs × 4 conditions = 300 sessions total |
| Complex enough to require real architecture | Static site generator with plugins, themes, caching |

### Why Adversarial Prompts

Pre-written prompts ensure:
- Identical conditions across all runs
- Targeted testing of specific failure modes
- Reproducibility by other researchers

Each prompt was designed to trigger a known failure mode (amnesia, drift, TDD skipping, debug thrashing, scope creep, verification skipping).

### Why Static Site Generator

| Criterion | SSG Suitability |
|-----------|-----------------|
| Multiple interacting systems | Templates, plugins, themes, caching, dev server |
| Decisions that compound | Template engine choice affects Sessions 3, 7, 10, 12 |
| Realistic complexity | Not trivial, not enterprise-scale |
| Clear success criteria | Tests pass, features work, documentation complete |

---

## Failure Modes Targeted

These failure modes were identified through practitioner experience and validated against industry research:

| Failure Mode | Description | Sessions Targeting It |
|--------------|-------------|----------------------|
| **Session Amnesia** | Forgetting context/decisions from previous sessions | 7, 9, 12 |
| **Decision Drift** | Unconsciously changing approach mid-project | 7, 10 |
| **TDD Skipping** | Writing implementation before tests despite instructions | 2, 5, 6, 11 |
| **Debug Thrashing** | Random changes without systematic diagnosis | 9 |
| **Verification Skipping** | Claiming completion without running tests | 6, 15 |
| **Scope Creep** | Adding unrequested features | 13 |

---

## Full Research Archive

All exploratory research, literature reviews, and design notes are preserved in the ContextMap repository:

- [Research Landscape Analysis](https://github.com/daviddinius/ContextMap/blob/main/research/ai_developer_tools_research_landscape.md)
- [Context Engineering Literature Review](https://github.com/daviddinius/ContextMap/blob/main/research/context-engineering-literature-review.md)
- [Key Findings Summary](https://github.com/daviddinius/ContextMap/blob/main/research/key-findings-summary.md)
- [Funding Research](https://github.com/daviddinius/ContextMap/blob/main/AI_Developer_Tools_Funding_Research_2026.md)
- [Full research directory](https://github.com/daviddinius/ContextMap/tree/main/research)

---

## Tools Under Evaluation

### ContextMap (Context Persistence)

A Claude Code plugin that maintains project context across sessions through:
- Constitutional documents (project principles, architecture decisions)
- Auto-updated state files (current phase, recent changes, blockers)
- Structured session summaries

Repository: https://github.com/daviddinius/ContextMap

### Superpowers (Workflow Discipline)

A Claude Code plugin that enforces development practices:
- Mandatory brainstorming before implementation
- Test-driven development workflows
- Systematic debugging protocols
- Verification requirements before completion claims

Repository: https://github.com/superpowers-marketplace/superpowers

---

*Document created: 2026-01-05*
