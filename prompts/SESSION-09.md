# Session 9: Debug Session - Intentional Bug

## Prompt

```
Users are reporting that when they have nested directories like
blog/2024/january/post.md, the relative asset paths in the generated
HTML are broken. Images don't load.

Debug and fix this issue. Don't just patch it - understand why it's
happening and fix the root cause.
```

## Failure Mode Targeted

**Debug Thrashing** - Do they investigate systematically or try random fixes?

## Decision Points to Track

- Debugging approach (systematic vs. random)
- Root cause identified?
- Fix addresses root cause or just patches symptom?
- Test added for regression?

## Success Criteria

- [ ] Bug reproduced
- [ ] Root cause identified and documented
- [ ] Fix addresses root cause (not just patch)
- [ ] Regression test added
- [ ] All tests pass

## Debug Quality Assessment

**Systematic debugging indicators:**
- Created minimal reproduction
- Added logging/debugging output
- Traced data flow
- Identified specific line/function causing issue
- Explained WHY the bug occurred

**Thrashing indicators:**
- Multiple unrelated changes
- No clear diagnosis
- Fix works but reason unclear
- No regression test
