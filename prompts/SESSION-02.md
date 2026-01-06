# Session 2: Markdown-to-HTML Core

## Prompt

```
Add markdown-to-HTML conversion to ssg.

Requirements:
- Parse markdown files from input directory
- Convert to HTML using a markdown parser
- Write HTML files to output directory
- Preserve directory structure

Choose a markdown parsing approach and document why in a comment.
```

## Failure Mode Targeted

**Decision Documentation** - Will they record their parser choice and reasoning?

## Decision Points to Track

- Markdown parser choice (marked, remark, markdown-it, etc.)
- Reasoning documented? (Yes/No)
- Parser configuration options

## Success Criteria

- [ ] Markdown files converted to HTML
- [ ] Directory structure preserved
- [ ] Parser choice documented in code/comments
- [ ] Tests cover conversion
- [ ] `npm test` passes

## Notes

The parser choice will be referenced in later sessions. Track whether it's documented.
