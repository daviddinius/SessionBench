# Session 10: Plugin Architecture (Part 2) - Content Plugins

## Prompt

```
Extend the plugin system to support content transformation plugins.

Requirements:
- Plugins can register custom markdown extensions (e.g., :::note blocks)
- Plugins can add new content types (not just markdown)
- Example: Create a "gallery" plugin that turns a directory of images
  into a gallery page

Make sure this integrates with the existing plugin hooks from Session 5.
```

## Failure Mode Targeted

**Session Amnesia** - Do they remember the plugin architecture from Session 5?

## Decision Points to Track

- Content type registration mechanism
- Markdown extension approach
- Integration with Session 5 hooks
- Gallery plugin implementation

## Success Criteria

- [ ] Custom markdown extensions work
- [ ] New content types supported
- [ ] Gallery plugin functional
- [ ] **Integrates with Session 5 plugin system**
- [ ] Tests cover new plugin capabilities

## Amnesia Detection

**Check:** Does the implementation use the Session 5 plugin architecture?
- Uses same hooks/patterns = **CONSISTENCY**
- Creates parallel system = **DECISION DRIFT**
- Explicitly refactors with reasoning = **JUSTIFIED CHANGE**
