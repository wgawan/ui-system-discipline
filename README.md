# UI System Discipline

A skill for Gemini CLI, Claude Code, and OpenAI Codex for designing and enforcing UI systems that minimize user effort, reduce cognitive load, and translate user intent into clear, structured interfaces.

This skill doesn't just critique UI. It restructures it.

## What It Does

- Enforces structure-first design (layout, spacing, typography before color and decoration)
- Maps user intent to the fastest UI path
- Applies consistent design tokens (typography scale, spacing system, color system, border radius)
- Uses an explicit workflow: inspect, classify, restructure, implement, validate
- Covers accessibility, motion, empty/loading states, interaction states, and data density

## Install

### Option 1: Gemini CLI

Install the skill to your user scope:

```bash
gemini skills install https://github.com/wgawan/ui-system-discipline
```

Or install it only for your current workspace:

```bash
gemini skills install https://github.com/wgawan/ui-system-discipline --scope workspace
```

To use it in Gemini CLI:

- Gemini will autonomously activate the skill when you ask for UI-related tasks (e.g., "Redesign this page" or "Review the layout of this component").
- You can also explicitly ask: "Use the ui-system-discipline skill to review this dashboard."

### Option 2: Claude Code CLI

```bash
claude skill add --url https://github.com/wgawan/ui-system-discipline
```

### Option 3: OpenAI Codex

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

### Option 4: Manual Claude Code

Copy `SKILL.md` to your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/ui-system-discipline
cp SKILL.md ~/.claude/skills/ui-system-discipline/SKILL.md
```

## When It Activates

- Redesigning or reviewing an existing UI
- Building a new screen where hierarchy and user flow matter
- Working on dashboards, forms, settings pages, tables, detail views, navigation, or component libraries
- Asking for UI feedback that should lead to concrete structural fixes

It should not trigger for backend-only work, generic refactors with no user-facing impact, or tiny visual polish requests that intentionally preserve the current layout.

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

## Workflow

For substantial UI review or redesign tasks, the skill guides the agent through:

1. **Diagnosis** of current UI issues
2. **Intent** mapping (what the user is trying to accomplish)
3. **Priority map** (primary / secondary / tertiary classification)
4. **Design system choices** (specific typography, spacing, color, and radius values)
5. **Layout redesign** with hierarchy corrections
6. **Implementation** with concrete code changes
7. **Validation** against hierarchy, states, responsiveness, and accessibility checks

For narrower frontend tasks, the skill is intentionally lighter-weight: it should patch the UI directly instead of forcing every section into the response.

## License

MIT
