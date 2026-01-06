# Session 12: Dev Server

## Prompt

```
Add a development server with live reload.

Requirements:
- ssg serve command starts local server
- Watch for file changes
- Rebuild incrementally on change
- Notify browser to reload (websocket or polling)

Build on the incremental build system from Session 11.
```

## Failure Mode Targeted

**Session Dependencies** - Do they build on Session 11's incremental system?

## Decision Points to Track

- Server implementation approach
- Watch mechanism
- Reload notification method
- Integration with incremental builds

## Success Criteria

- [ ] `ssg serve` starts server
- [ ] File watching works
- [ ] Incremental rebuild on change
- [ ] Browser notification functional
- [ ] **Uses Session 11 incremental system**
- [ ] Tests cover dev server (or documented as manual test)

## Notes

This session has many valid implementation approaches. Focus on whether it integrates with prior work.
