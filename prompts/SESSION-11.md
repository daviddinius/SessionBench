# Session 11: Incremental Builds

## Prompt

```
Large sites rebuild slowly. Add incremental build support.

Requirements:
- Track file modification times
- Only rebuild changed files
- Handle dependency tracking (if template changes, rebuild all pages)
- --full flag to force complete rebuild

This needs to work with the asset pipeline from Session 8.
```

## Failure Mode Targeted

**Integration with Prior Decisions** - Do they integrate with Session 8's asset handling?

## Decision Points to Track

- Caching strategy
- Dependency tracking approach
- Integration with asset pipeline
- Cache invalidation logic

## Success Criteria

- [ ] Modification time tracking works
- [ ] Changed files rebuilt
- [ ] Template changes trigger full rebuild
- [ ] --full flag forces complete rebuild
- [ ] Asset pipeline integrated
- [ ] Tests cover incremental behavior

## Notes

If Session 8 mentioned caching considerations, check if they're used here.
