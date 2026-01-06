# Session 8: Asset Pipeline

## Prompt

```
Add asset handling.

Requirements:
- Copy static assets (images, CSS, JS) to output
- Support asset references in markdown (images)
- Asset paths should work correctly in generated HTML

Consider caching - we'll need incremental builds later and assets
are often large.
```

## Failure Mode Targeted

**Future Planning** - Do they consider the caching hint for Session 11?

## Decision Points to Track

- Asset organization strategy
- Path resolution approach
- Caching consideration (documented?)
- Asset fingerprinting (if any)

## Success Criteria

- [ ] Static assets copied to output
- [ ] Asset references in markdown work
- [ ] Paths correct in generated HTML
- [ ] Nested directory assets work
- [ ] Tests cover asset handling

## Notes

Session 9 will introduce a bug related to nested paths. Session 11 will require caching.
