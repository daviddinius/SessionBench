# SessionBench

**A benchmark for measuring AI coding assistant effectiveness across multi-session projects.**

---

## The Gap

Current AI coding benchmarks (SWE-bench, HumanEval, MBPP) measure single-session performance: "Can the AI write code?"

But real projects span multiple sessions. No one is measuring:
- Does the AI remember what was decided last session?
- Does it follow disciplined workflows (TDD, planning)?
- How much time is wasted re-explaining the codebase?

**SessionBench fills this gap.**

---

## What We Test

### Failure Modes

| Failure Mode | Description |
|--------------|-------------|
| **Session Amnesia** | Forgetting decisions/context between sessions |
| **Decision Drift** | Changing approach mid-project without realizing |
| **TDD Skipping** | Writing code before tests |
| **Debug Thrashing** | Random fixes instead of systematic debugging |
| **Verification Skip** | Claiming "done" without running tests |
| **Scope Creep** | Adding unrequested features |

### Experimental Design

**2x2 Factorial:**
- Context Persistence Tool (Yes/No)
- Workflow Discipline Tool (Yes/No)

**4 Conditions:**
1. Baseline (no tools)
2. Context persistence only
3. Workflow discipline only
4. Both combined

### The Benchmark Project

A **Static Site Generator ("ssg")** built over 15 sessions:
- Sessions 1-5: Foundation (pipeline, templates, config)
- Sessions 6-10: Extension (plugins, themes, assets)
- Sessions 11-15: Advanced (incremental builds, dev server)

Each session has pre-written prompts targeting specific failure modes.

---

## Metrics

| Category | Metrics |
|----------|---------|
| **Tokens** | Input/output per session, cumulative total |
| **Time** | Wall clock per session, time to first output |
| **Quality** | Test pass rate, coverage, lint clean, features complete |
| **Consistency** | Decision drift score across sessions |
| **Failure Modes** | Detection rate for each failure type |

---

## Structure

```
SessionBench/
├── prompts/           # 15 session prompts
│   ├── SESSION-01.md
│   ├── SESSION-02.md
│   └── ...
├── protocol/          # How to run the benchmark
│   ├── MEASUREMENT.md
│   ├── EXECUTION.md
│   └── SUCCESS-CRITERIA.md
├── ssg-project/       # The benchmark project spec
│   └── SPEC.md
├── data/              # Raw results (per run)
│   └── runs/
└── analysis/          # Analysis scripts and reports
```

---

## Running the Benchmark

See [protocol/EXECUTION.md](protocol/EXECUTION.md) for detailed instructions.

**Quick overview:**
1. Set up fresh environment
2. Choose condition (baseline, context-only, workflow-only, both)
3. Run 15 sessions with 4-6 hour gaps
4. Record metrics after each session
5. Repeat 5 times per condition

---

## Why This Matters

Research shows:
- **65% of developers** cite context as #1 pain point with AI tools (Qodo 2025)
- **Persistent context reduces failures** from 54% to 16% (Qodo 2025)
- **Cursor made experienced devs 19% slower** in real tasks (METR RCT 2025)

Current tools may not be helping as much as claimed. SessionBench provides rigorous measurement.

---

## Status

**Current:** Design phase

**Planned:**
- [ ] Finalize 15 session prompts
- [ ] Pilot test (2-3 sessions per condition)
- [ ] Pre-register hypotheses
- [ ] Full benchmark execution (300 sessions)
- [ ] Analysis and publication

---

## Contributors

- David Dinius - Design, implementation
- [Seeking academic collaborator for methodology/publication]

---

## License

MIT License - See [LICENSE](LICENSE) for details.

---

## Related Work

- [SWE-bench](https://www.swebench.com/) - Single-session bug fixing benchmark
- [HumanEval](https://github.com/openai/human-eval) - Function completion benchmark
- [ContextMap](https://github.com/daviddinius/ContextMap) - Context persistence tool (one tool being tested)
