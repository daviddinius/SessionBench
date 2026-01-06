# Execution Protocol

## Overview

This document defines how to run SessionBench experiments.

---

## Experimental Design

### Conditions

| Condition | Context Tool | Workflow Tool |
|-----------|--------------|---------------|
| **Baseline** | None | None |
| **Context-Only** | ContextMap | None |
| **Workflow-Only** | None | Superpowers |
| **Combined** | ContextMap | Superpowers |

### Runs Per Condition

- **Minimum:** 3 runs per condition
- **Recommended:** 5 runs per condition
- **Total sessions:** 4 conditions × 5 runs × 15 sessions = 300 sessions

---

## Schedule: Latin Square Design

To avoid learning bias, randomize condition order across weeks:

```
Week 1: Baseline → Context → Workflow → Combined
Week 2: Combined → Workflow → Context → Baseline
Week 3: Workflow → Baseline → Combined → Context
Week 4: Context → Combined → Baseline → Workflow
Week 5: (Repeat with new random order)
```

Each week: Complete Run N of each condition before starting Run N+1.

---

## Session Timing

### Gap Between Sessions

**Recommended:** 4-6 hours minimum between sessions within a run.

This simulates realistic multi-session development where context is lost.

### Gap Between Runs

**Recommended:** Start new run at least 24 hours after completing previous run.

---

## Pre-Session Setup

### 1. Fresh Environment

```bash
# Create clean working directory
cd /tmp
rm -rf ssg-benchmark-workspace
mkdir ssg-benchmark-workspace
cd ssg-benchmark-workspace

# For Session 1: Start fresh
# For Sessions 2-15: Clone from previous session snapshot
git clone /path/to/snapshots/run-XXX/after-session-YY .
```

### 2. Tool Configuration

**Baseline:**
- No ContextMap files
- No Superpowers plugin
- Vanilla Claude Code

**Context-Only:**
- Initialize ContextMap: `Tell Claude: "Set up ContextMap for this project"`
- No Superpowers plugin

**Workflow-Only:**
- No ContextMap files
- Superpowers plugin active

**Combined:**
- ContextMap initialized
- Superpowers plugin active

### 3. Start New Claude Session

**Critical:** Each session must be a NEW Claude Code conversation.

```bash
# Verify no prior context
# Start Claude Code fresh
claude

# Do NOT continue previous conversations
```

---

## Running a Session

### 1. Record Start Time

```bash
echo "Session start: $(date -u +"%Y-%m-%dT%H:%M:%SZ")"
```

### 2. Read Prompt from File

**Do not paraphrase or add information.**

```bash
cat /path/to/SessionBench/prompts/SESSION-XX.md
```

Copy the prompt text exactly into Claude.

### 3. Let Claude Work

- Do not provide hints not in the prompt
- Do not correct Claude unless asked
- Do not reference prior sessions (that's the test)
- Record any observations in operator notes

### 4. Session End

Wait for Claude to indicate completion, then:

```bash
# Record end time
echo "Session end: $(date -u +"%Y-%m-%dT%H:%M:%SZ")"

# Run quality checks
npm test
npm run lint
npm run build

# Create git snapshot
git add -A
git commit -m "After session XX"
```

### 5. Record Metrics

Fill out session data file (see MEASUREMENT.md).

---

## Operator Protocol

### Do's

- Follow prompts exactly as written
- Record all metrics immediately after session
- Note any unusual circumstances
- Create git snapshot after each session
- Take breaks to avoid fatigue

### Don'ts

- Don't provide hints beyond the prompt
- Don't continue previous Claude conversations
- Don't skip quality checks
- Don't review aggregate results during experiment
- Don't discuss results between runs

### Handling Edge Cases

**If Claude gets stuck:**
- Allow it to work through the problem
- Do not provide hints
- Record "stuck" event in operator notes
- If completely blocked after 30 minutes, note as "incomplete" and proceed

**If Claude produces errors:**
- Allow it to debug
- Record debugging approach
- Note outcome

**If session runs very long:**
- 90-minute soft cap
- 120-minute hard cap
- Note early termination reason

---

## Post-Run Processing

After completing all 15 sessions in a run:

### 1. Verify Data Completeness

```bash
# Check all session files exist
ls data/runs/run-XXX/sessions/

# Verify git snapshots
ls data/runs/run-XXX/git-snapshots/
```

### 2. Calculate Summary Metrics

Run analysis script:

```bash
python analysis/summarize-run.py data/runs/run-XXX/
```

### 3. Archive Raw Logs

```bash
tar -czvf run-XXX-logs.tar.gz data/runs/run-XXX/
```

---

## Quality Assurance

### Before First Run

- [ ] Pilot test 2-3 sessions to verify protocol
- [ ] Confirm all tools work correctly
- [ ] Verify measurement scripts function
- [ ] Review prompts for clarity

### During Execution

- [ ] Daily backup of data directory
- [ ] Spot-check session data files
- [ ] Monitor for operator fatigue

### After All Runs

- [ ] Verify all data collected
- [ ] Check for missing sessions
- [ ] Review operator notes for issues
- [ ] Second operator verification (if available)
