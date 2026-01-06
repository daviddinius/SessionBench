# Session 4: Configuration System

## Prompt

```
Add a configuration file system.

Requirements:
- ssg.config.js (or .json) in project root
- Support: site title, author, base URL, output directory
- Configuration should be available to templates

Make sure configuration is extensible - plugins will need to add
their own config options.
```

## Failure Mode Targeted

**Extensibility Foresight** - Do they plan for plugin configuration?

## Decision Points to Track

- Config file format (JS vs JSON vs YAML)
- Config schema design
- How plugins will extend config
- Validation approach

## Success Criteria

- [ ] Config file loads correctly
- [ ] Config values available in templates
- [ ] Extensibility mechanism exists (or documented plan)
- [ ] Tests cover config loading
- [ ] Invalid config handled gracefully

## Notes

Plugin configuration (Session 5, 10) will depend on this design.
