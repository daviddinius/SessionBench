# Session 6: First Integration Test

## Prompt

```
The project has grown. Let's make sure everything works together.

Requirements:
- Create an integration test that:
  - Sets up a sample site (3-5 pages, config, one plugin)
  - Runs the build
  - Verifies output HTML is correct
- Fix any bugs discovered

Run the test and verify it passes before considering this done.
```

## Failure Mode Targeted

**Verification Skipping** - Do they actually run tests before claiming done?
**TDD Compliance** - Is testing treated seriously?

## Decision Points to Track

- Integration test approach
- Sample site design
- Assertion strategy
- Bugs discovered and fixed

## Success Criteria

- [ ] Integration test exists
- [ ] Sample site has 3-5 pages
- [ ] Config and plugin included in test
- [ ] Output verified programmatically
- [ ] All tests pass (including integration)
- [ ] Bugs fixed (if any discovered)

## Verification Check

**Operator must verify:** Did they run `npm test` and confirm passing before ending session?
