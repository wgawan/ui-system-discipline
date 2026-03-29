---
name: ui-system-discipline
description: >-
  Design and enforce UI systems that minimize user effort, reduce cognitive load,
  and translate user intent into clear, structured interfaces. Restructures weak
  UI — not just critiques it. Covers layout, typography, color, spacing, motion,
  accessibility, and component design using structure-first principles.
  TRIGGER when: user is building or reviewing UI, designing interfaces,
  creating dashboards, working on frontend layouts, or asks for UI feedback.
  DO NOT TRIGGER when: user is doing backend-only work with no UI component.
origin: community
metadata:
  author: wally
  version: "1.0.0"
  filePattern:
    - "**/*.tsx"
    - "**/*.jsx"
    - "**/*.css"
    - "**/*.scss"
    - "**/*.vue"
    - "**/*.svelte"
    - "**/components/**"
    - "**/pages/**"
    - "**/layouts/**"
    - "**/styles/**"
---

# UI System Discipline

Design and enforce a UI system that minimizes user effort, reduces cognitive load, and translates user intent into clear, structured interfaces.

This skill must redesign weak UI, not just critique it.

## When to Use

- Designing or reviewing any user interface
- Building dashboards, forms, settings pages, or data-heavy views
- Evaluating component layout, spacing, or visual hierarchy
- Creating or refactoring frontend components (React, Vue, Svelte, etc.)
- User asks for UI feedback, design review, or layout improvements
- Implementing design systems or component libraries

## Hard Constraints

1. UI exists to reduce user effort.
2. If everything is visible, the design is wrong.
3. Clarity always wins over expressiveness.
4. If a design feels clever, it is likely wrong.

---

## Structure-First Rule

Design must work before styling.

Before using:
- color
- shadows
- borders
- icons

The UI must be clear using only:
- layout
- spacing
- typography

---

## Intent → UI

Define:
- **User goal** — what the user is trying to accomplish
- **Fastest path** — minimum steps to reach the goal
- **Required vs optional info** — only show what's needed for the current step

Design around this path. Everything else is noise.

---

## Decision Reduction

One clear next action at a time.

- Reduce the number of choices visible at any moment
- Use progressive disclosure to reveal complexity only when needed
- Default to the most common choice

---

## Feedback

Every action must produce visible feedback.

- Button clicks → loading state or confirmation
- Form submissions → success/error message
- Navigation → visual indicator of current location
- Destructive actions → confirmation dialog

---

## Affordance

UI must visually communicate how it is used.

- Clickable elements look clickable (cursor, underline, color)
- Draggable elements have grab handles
- Editable fields have visible boundaries
- Disabled elements are visually distinct

---

## Cognitive Load

Reduce:
- **Thinking** — make the next action obvious
- **Scanning** — group related items, use visual hierarchy
- **Interpretation** — use familiar patterns, avoid jargon

---

## Typography System

Scale: `12, 14, 16, 20, 24–32, 40+`

Rules:
- Size encodes importance — larger = more important
- No arbitrary sizes — stick to the scale
- Values > labels > metadata — numbers and data are primary, labels secondary, metadata tertiary

---

## Text + Icon System

### Text Rules
- Remove unnecessary labels
- Keep text minimal and scannable
- Layout replaces explanation — position conveys meaning

### Icon Rules
- Icons are secondary signals, not primary content
- No decorative icons — every icon must aid comprehension
- No redundancy with adjacent text
- Consistent size and alignment across the interface

### Scan Test
UI must be understandable in 2–3 seconds. If a user can't identify the primary action and key information in that time, the design needs simplification.

---

## Prioritization

Define three tiers for every view:
- **Primary** — the main action or content (dominates visually)
- **Secondary** — supporting actions or context (visible but subordinate)
- **Tertiary** — metadata, settings, rarely used actions (hidden or minimized)

Primary must dominate visually. If primary and secondary compete for attention, the hierarchy is broken.

---

## Layout Rules

- One dominant element per section
- Group related items before adding visual decoration
- Spacing defines structure — proximity = relationship

---

## Grid System

- Consistent column widths
- Consistent gutters (use spacing scale)
- Predictable alignment — elements snap to the grid

---

## Spacing System

`4, 8, 12, 16, 20, 24, 32, 40, 48, 64`

Use spacing to create visual grouping:
- Tight spacing (4–8) = closely related items
- Medium spacing (12–24) = items in the same group
- Wide spacing (32–64) = separate sections or groups

---

## Color System

- **Neutral-first** — build the interface in grays, then add color
- **One accent** — a single primary accent color for actions and focus
- **Semantic colors only** — red for errors/destructive, green for success, yellow for warnings, blue for info

---

## HSB Palette Construction

- Lock hue for each semantic color
- Step brightness to create light/dark variants
- Adjust saturation — lower for backgrounds, higher for interactive elements

---

## Light / Dark Mode

- No simple inversion — dark mode requires its own surface hierarchy
- Preserve visual hierarchy — same importance relationships in both modes
- Separate surface levels — use distinct background shades for elevation

---

## Border Radius

`4, 8, 12, 16, 24`

- Smaller radius for inputs, badges, tags
- Medium radius for cards, dialogs
- Larger radius for containers, hero sections
- Consistent within component families

---

## Components

- **Consistent** — same component looks and behaves the same everywhere
- **Minimal** — fewest possible variants that cover all use cases
- **Structured** — clear prop API, predictable behavior

---

## Interaction States

Every interactive element must define:
`default → hover → active → focus → disabled`

- Transitions between states should be smooth (150–250ms)
- Focus states must be visible for keyboard navigation
- Disabled states must look distinct but not invisible

---

## Data Density

- Use alignment and grouping to make dense data scannable
- Reduce noise first — remove unnecessary borders, backgrounds, and dividers
- Right-align numbers, left-align text
- Use monospace for tabular numeric data

---

## Empty + Loading States

**Empty states:**
- Explain what will appear here
- Guide the user to the action that populates this view
- Never show a blank screen

**Loading states:**
- Use skeleton screens that match the layout of real content
- Show progress indicators for operations > 1 second
- Maintain layout stability — no content shifts when data loads

---

## Motion

- Subtle and purposeful — motion should guide attention, not distract
- Duration: 150–250ms for micro-interactions, 300–500ms for page transitions
- Ease-out for entrances, ease-in for exits
- Never block interaction with animation

---

## Accessibility

- **Contrast** — minimum 4.5:1 for text, 3:1 for large text and UI elements
- **Focus visibility** — all interactive elements must have visible focus indicators
- **Target size** — minimum 44×44px for touch targets, 24×24px for pointer
- **Semantic HTML** — use proper elements (button, a, input), not divs with click handlers
- **ARIA** — add labels for icon-only buttons, live regions for dynamic content

---

## Anti-Noise Checklist

Before shipping, attempt to remove:
- Borders — can spacing alone define the boundary?
- Labels — does the layout make the meaning obvious?
- Colors — is color used for meaning or just decoration?
- Containers — can grouping be achieved with spacing alone?

If removing it doesn't reduce clarity, it shouldn't be there.

---

## System Thinking

- Reuse patterns — solve a problem once, apply it everywhere
- Repetition creates clarity — consistent patterns reduce learning time
- Fix systems, not instances — if one component is wrong, the system is wrong

---

## Redesign Mode

When reviewing existing UI, the system MUST:
1. **Restructure layouts** — fix information hierarchy and flow
2. **Elevate primary content** — make the most important thing impossible to miss
3. **Demote secondary content** — supporting info should be accessible but not competing
4. **Remove tertiary noise** — if it's not needed now, hide or remove it
5. **Simplify actions** — reduce the number of visible actions to what's relevant

---

## Required Output Format

When applying this skill, produce:

1. **Diagnosis** — what's wrong with the current UI (or requirements to address)
2. **Intent** — what the user is trying to accomplish
3. **Priority map** — primary / secondary / tertiary classification of all elements
4. **Design tokens** — specific typography, spacing, color, and radius values
5. **Layout redesign** — restructured layout with hierarchy corrections
6. **Implementation** — concrete code or markup changes
