# SSG Project Specification

## Overview

**Project:** Static Site Generator ("ssg")
**Language:** TypeScript
**Purpose:** Benchmark project for SessionBench

This document defines the complete specification for the ssg project that will be built across 15 sessions.

---

## Core Functionality

### CLI Interface

```bash
# Build site
ssg build --input ./content --output ./dist

# Development server
ssg serve --input ./content --port 3000

# Full rebuild (ignore cache)
ssg build --full
```

### Build Pipeline

```
Input (markdown + assets)
    ↓
Parse frontmatter
    ↓
Transform markdown → HTML
    ↓
Apply templates
    ↓
Process assets
    ↓
Write output
```

---

## Features by Session

### Sessions 1-5: Foundation

| Feature | Session | Description |
|---------|---------|-------------|
| Project setup | 1 | TypeScript, Jest, CLI skeleton |
| Markdown → HTML | 2 | Basic conversion with parser |
| Templates | 3 | Layout wrapping, variable insertion |
| Configuration | 4 | ssg.config.js with site metadata |
| Plugins | 5 | Hook-based plugin system |

### Sessions 6-10: Extension

| Feature | Session | Description |
|---------|---------|-------------|
| Integration test | 6 | End-to-end test with sample site |
| Themes | 7 | Theme directories with templates/assets |
| Asset pipeline | 8 | Static file handling, path resolution |
| Bug fix | 9 | Nested path asset bug |
| Content plugins | 10 | Custom markdown extensions, new content types |

### Sessions 11-15: Advanced

| Feature | Session | Description |
|---------|---------|-------------|
| Incremental builds | 11 | File tracking, dependency cache |
| Dev server | 12 | Live reload, file watching |
| Feature evaluation | 13 | MDX/JSX request handling |
| Performance | 14 | Profiling, optimization |
| Documentation | 15 | README, sample site, release prep |

---

## Technical Decisions (Expected)

These decisions will be made during the benchmark. Track consistency.

### Session 2: Markdown Parser

**Options:**
- `marked` - Fast, popular
- `remark` - Plugin ecosystem
- `markdown-it` - Extensible
- Custom - Not recommended

### Session 3: Template Engine

**Options:**
- `handlebars` - Logic-less, popular
- `ejs` - JavaScript templates
- `nunjucks` - Jinja-like
- `eta` - Fast, lightweight

**This is the most critical decision.** Affects Sessions 7, 10, 12.

### Session 4: Config Format

**Options:**
- `.js` - Dynamic, can import modules
- `.json` - Simple, static
- `.yaml` - Human-readable
- `.ts` - Type-safe

### Session 5: Plugin Pattern

**Options:**
- **Hooks:** Named events, plugins register handlers
- **Middleware:** Pipeline, plugins transform data
- **Hybrid:** Both patterns

---

## File Structure (Expected Final)

```
ssg/
├── src/
│   ├── index.ts           # CLI entry point
│   ├── build.ts           # Build orchestration
│   ├── markdown.ts        # Markdown processing
│   ├── templates.ts       # Template rendering
│   ├── config.ts          # Configuration loading
│   ├── plugins.ts         # Plugin system
│   ├── themes.ts          # Theme loading
│   ├── assets.ts          # Asset pipeline
│   ├── cache.ts           # Incremental build cache
│   └── server.ts          # Dev server
├── tests/
│   ├── unit/
│   └── integration/
├── themes/
│   └── default/
├── plugins/
│   └── timestamp/
├── package.json
├── tsconfig.json
├── jest.config.js
└── ssg.config.js
```

---

## Sample Site (Session 15)

The final sample site should demonstrate:

```
sample-site/
├── content/
│   ├── index.md
│   ├── about.md
│   ├── blog/
│   │   ├── 2024/
│   │   │   └── hello-world.md
│   │   └── 2025/
│   │       └── new-features.md
│   └── gallery/
│       └── images/
├── assets/
│   ├── css/
│   ├── js/
│   └── images/
├── ssg.config.js
└── themes/
    └── custom/
```

---

## Quality Requirements

### Tests

- Unit tests for each module
- Integration test with sample site
- Coverage target: 70%+

### Code Quality

- TypeScript strict mode
- ESLint clean
- No `any` types (minimal)

### Documentation

- README with usage examples
- Configuration reference
- Plugin API documentation

---

## Out of Scope

These features are explicitly NOT part of the benchmark:

- Database integration
- User authentication
- Server-side rendering
- React/Vue/Svelte components
- Deployment automation
- Multiple output formats (PDF, etc.)

---

## Evaluation Criteria

### Feature Completion

Score each session's requirements:
- **Complete:** All requirements met
- **Partial:** Some requirements met
- **Missing:** Requirements not addressed

### Code Quality

- Tests exist and pass
- Code is readable
- Architecture is consistent

### Decision Consistency

- Choices from earlier sessions maintained
- Changes are justified when they occur
