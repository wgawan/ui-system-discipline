# UI System Discipline

A skill for Claude Code and OpenAI Codex for designing and enforcing UI systems that minimize user effort, reduce cognitive load, and translate user intent into clear, structured interfaces.

This skill doesn't just critique UI. It restructures it.

## What It Does

- Enforces structure-first design (layout, spacing, typography before color and decoration)
- Maps user intent to the fastest UI path
- Applies consistent design tokens (typography scale, spacing system, color system, border radius)
- Provides a concrete redesign workflow with required output format
- Covers accessibility, motion, empty/loading states, data density, and dark mode

## Install

### Option 1: Claude Code CLI

```bash
claude skill add --url https://github.com/wgawan/ui-system-discipline
```

### Option 2: OpenAI Codex

Copy this skill into your Codex skills directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills/ui-system-discipline"
cp SKILL.md "${CODEX_HOME:-$HOME/.codex}/skills/ui-system-discipline/SKILL.md"
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills/ui-system-discipline/agents"
cp agents/openai.yaml "${CODEX_HOME:-$HOME/.codex}/skills/ui-system-discipline/agents/openai.yaml"
```

Restart Codex after installing so it reloads the skill list.

To use it in Codex:

- Mention the skill directly in your prompt with `$ui-system-discipline`
- Or let Codex invoke it implicitly on UI-heavy tasks after install

Example prompts:

```text
Use $ui-system-discipline to redesign this dashboard so the primary action is obvious.
```

```text
Use $ui-system-discipline to review this settings page and then implement the layout fixes.
```

### Option 3: Manual Claude Code

Copy `SKILL.md` to your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/ui-system-discipline
cp SKILL.md ~/.claude/skills/ui-system-discipline/SKILL.md
```

## When It Activates

- Building or reviewing any user interface
- Working with component files (`.tsx`, `.jsx`, `.vue`, `.svelte`, `.css`)
- Designing dashboards, forms, settings pages, or data-heavy views
- Asking for UI feedback or design review

## Core Principles

1. **UI exists to reduce user effort.** Not to look impressive.
2. **If everything is visible, the design is wrong.** Use progressive disclosure.
3. **Clarity always wins over expressiveness.** Simple beats clever.
4. **Structure before style.** If the layout doesn't work in grayscale with no borders, it doesn't work.

## Design Tokens

| System | Scale |
|--------|-------|
| Typography | 12, 14, 16, 20, 24-32, 40+ |
| Spacing | 4, 8, 12, 16, 20, 24, 32, 40, 48, 64 |
| Border radius | 4, 8, 12, 16, 24 |
| Color | Neutral-first, one accent, semantic only |
| Motion | 150-250ms micro, 300-500ms transitions |

## Output Format

When the skill activates, it produces:

1. **Diagnosis** of current UI issues
2. **Intent** mapping (what the user is trying to accomplish)
3. **Priority map** (primary / secondary / tertiary classification)
4. **Design tokens** (specific values for typography, spacing, color, radius)
5. **Layout redesign** with hierarchy corrections
6. **Implementation** with concrete code changes

## License

MIT
