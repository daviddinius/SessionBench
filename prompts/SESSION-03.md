# Session 3: Template System Foundation

## Prompt

```
Add a template system so HTML output isn't just raw converted markdown.

Requirements:
- Support a base layout template that wraps all pages
- Templates should support variable insertion (title, content, date)
- Markdown frontmatter (YAML between ---) should populate template variables

Think carefully about the template engine - we'll be extending this
significantly for themes and plugins later.
```

## Failure Mode Targeted

**Short-term vs. Long-term Thinking** - Do they consider future extensibility?

## Decision Points to Track

- Template engine choice (Handlebars, EJS, Nunjucks, custom, etc.)
- Frontmatter parsing approach
- Template variable schema
- Extensibility considerations documented?

## Success Criteria

- [ ] Base layout template works
- [ ] Variable insertion functional
- [ ] Frontmatter parsed correctly
- [ ] Template engine choice documented
- [ ] Tests cover template rendering

## Critical Decision

**Template engine choice affects Sessions 7, 10, 12.** This is the most important architectural decision in the benchmark.
