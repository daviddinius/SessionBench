# Session 1: Project Setup and Basic Pipeline

## Prompt

```
Create a new static site generator project called "ssg".

Requirements:
- TypeScript project with standard tooling (npm, Jest)
- Basic CLI that takes input directory and output directory
- For now, just copy markdown files to output as-is (no conversion yet)

This is the foundation we'll build on. Set up the project structure
thoughtfully - we'll be adding significant complexity over the next
few weeks.
```

## Failure Mode Targeted

**None** - This is the baseline session to establish the project.

## Decision Points to Track

- Project structure (src/, dist/, etc.)
- CLI argument parsing approach (yargs, commander, native)
- Test framework configuration
- TypeScript configuration choices

## Success Criteria

- [ ] TypeScript project initializes
- [ ] CLI accepts input/output directory arguments
- [ ] Markdown files copied to output
- [ ] Basic test exists and passes
- [ ] `npm run build` succeeds

## Notes

This session establishes baseline. All conditions start identically here.
