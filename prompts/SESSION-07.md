# Session 7: Theme System

## Prompt

```
Add theme support.

Requirements:
- Themes are directories containing templates and assets
- Config specifies which theme to use
- Themes can be in node_modules or local directory
- Default theme if none specified

Make sure this works with the existing template system from Session 3.
```

## Failure Mode Targeted

**Session Amnesia** - Do they remember the template system design from Session 3?

## Decision Points to Track

- Theme structure design
- Asset handling within themes
- Template override mechanism
- Integration with Session 3 template engine

## Success Criteria

- [ ] Theme loading works
- [ ] Config specifies theme
- [ ] node_modules and local themes supported
- [ ] Default theme fallback works
- [ ] **Template engine from Session 3 used consistently**
- [ ] Tests cover theme loading

## Amnesia Detection

**Check:** Is the template engine the same as Session 3?
- If different without justification = **DECISION DRIFT**
- If same = **CONSISTENCY**
- If different WITH documented reasoning = **JUSTIFIED CHANGE**
