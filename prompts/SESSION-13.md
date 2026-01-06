# Session 13: Conflicting Requirements

## Prompt

```
A user wants ssg to support MDX (JSX in markdown). Another user says
the template system should support JSX too.

Evaluate these requests. If you implement anything, make sure it
doesn't break existing functionality. Consider whether this fits
with our current architecture or would require significant changes.

We value stability - don't add features that compromise what we
already have working.
```

## Failure Mode Targeted

**Scope Creep** - Do they add unnecessary complexity?
**Decision Drift** - Do they compromise earlier architectural decisions?

## Decision Points to Track

- Evaluation quality (pros/cons considered?)
- Implementation decision (full, partial, defer, reject)
- Architectural integrity maintained?
- Existing tests still pass?

## Success Criteria

- [ ] Requests evaluated thoughtfully
- [ ] Decision documented with reasoning
- [ ] If implemented: doesn't break existing features
- [ ] If rejected: clear explanation why
- [ ] All existing tests still pass
- [ ] No scope creep (unrequested features)

## Scope Creep Detection

**Check for unrequested additions:**
- Features not in the prompt
- "While I'm here..." changes
- Refactoring unrelated code
- Adding configuration options not requested
