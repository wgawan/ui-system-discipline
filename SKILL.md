---
name: ui-system-discipline
description: >-
  Restructure and implement clearer frontend UI when Codex is asked to redesign,
  review, simplify, or systematize an existing interface, or build a new screen
  where hierarchy and user flow matter. Use for dashboards, forms, settings
  pages, tables, detail views, navigation, component libraries, and frontend
  layouts that need a clearer primary action, lower cognitive load, stronger
  spacing and typography, better interaction states, or accessibility fixes. Do
  not use for backend-only work, non-UI refactors, or requests that are limited
  to tiny visual polish while intentionally preserving the current structure.
---

# UI System Discipline

Redesign weak UI by changing structure, hierarchy, and implementation. Do not stop at critique when code changes are appropriate.

## Core Objective

Reduce user effort.

Translate the user's goal into the shortest clear path through the interface, then implement the layout, component, and styling changes needed to support that path.

## Operating Rules

1. Make one next action obvious.
2. Show only what is needed for the current step.
3. Make structure work before adding decoration.
4. Let spacing, alignment, and typography carry hierarchy first.
5. Treat color, borders, shadows, and icons as supporting signals.
6. Preserve consistency across similar components and states.
7. Prefer familiar patterns over clever ones.

## Execution Workflow

### 1. Inspect the Current UI

Read the relevant component, layout, and style files before proposing changes.

Identify:
- the user goal
- the primary task on the screen
- the current primary, secondary, and tertiary elements
- points of friction: scanning, choice overload, weak hierarchy, noisy controls, missing states, inaccessible patterns

If the user only provides requirements and no existing UI, infer the intended task flow first.

### 2. Define Intent Before Design

Write down:
- **User goal**: what the user wants to complete
- **Fastest path**: the minimum clear sequence of steps
- **Required now vs later**: what must be visible immediately and what should be deferred

Use this to decide what stays visible, what gets grouped, and what gets hidden or demoted.

### 3. Classify Every Element

Assign each meaningful element to one tier:
- **Primary**: the main content or action
- **Secondary**: supporting context or actions needed soon
- **Tertiary**: metadata, advanced controls, infrequent actions

If primary and secondary compete visually, fix the hierarchy.

If tertiary content is always visible without helping the main flow, hide, collapse, move, or remove it.

### 4. Restructure Before Styling

First fix:
- information order
- grouping
- spacing
- alignment
- heading levels
- component placement
- action count

Do not rely on color, shadows, borders, or icons to explain a weak layout.

Use progressive disclosure when complexity is real but not immediately necessary.

### 5. Apply a Small System

Use explicit, reusable tokens rather than arbitrary values.

Preferred scales:
- Typography: `12, 14, 16, 20, 24, 32, 40+`
- Spacing: `4, 8, 12, 16, 20, 24, 32, 40, 48, 64`
- Radius: `4, 8, 12, 16, 24`
- Motion: `150-250ms` for micro-interactions, `300-500ms` for larger transitions

Typography rules:
- Use size to encode importance.
- Keep numbers and key values more prominent than labels and metadata.
- Avoid arbitrary font-size jumps.

Spacing rules:
- Use tight spacing for items with a direct relationship.
- Use medium spacing within a group.
- Use wide spacing to separate sections.

Color rules:
- Start neutral-first.
- Use one accent color for key actions and focus.
- Use semantic colors only for status and meaning.

### 6. Implement, Not Just Describe

When the task allows edits, patch the UI directly.

Typical changes include:
- moving or removing low-value controls
- making one CTA dominant
- grouping related fields
- replacing decorative wrappers with spacing-based structure
- normalizing typography and spacing tokens
- improving empty, loading, error, hover, focus, active, and disabled states
- replacing non-semantic clickable containers with proper elements

When the user asks only for review, provide the redesign plan without editing files.

### 7. Verify the Result

Check the modified UI against this list before finishing:
- The primary action is identifiable within 2-3 seconds.
- Related items are grouped without extra explanation.
- Secondary actions do not compete with the primary path.
- Tertiary information is minimized or deferred.
- Interactive elements have visible `hover`, `focus`, `active`, and `disabled` states.
- Forms and async actions show feedback.
- Empty and loading states preserve structure.
- Text contrast and focus visibility are acceptable.
- Touch targets are usable.
- Semantic HTML is used where practical.
- The layout still works on narrow screens.

If a requested design choice conflicts with clarity or accessibility, say so directly and implement the safest strong version available.

## Design Heuristics

### Hierarchy

- Use one dominant element per section.
- Put the most important content first in both layout and reading order.
- Demote support content with size, weight, position, and spacing before reaching for muted colors.

### Affordance

- Make clickable elements look clickable.
- Make editable fields visibly editable.
- Make disabled controls distinct without making them disappear.
- Add labels to icon-only controls.

### Data-Dense Views

- Align repeated structures consistently.
- Right-align numeric columns and use monospace when tabular values need precise scanning.
- Remove borders and dividers that do not improve comprehension.

### Motion

- Use motion to guide attention, not decorate.
- Keep transitions short and non-blocking.

### Accessibility

- Preserve visible keyboard focus.
- Avoid `div` or `span` click targets when a semantic control exists.
- Maintain reasonable contrast and readable text sizes.
- Treat accessibility fixes as part of the redesign, not optional cleanup.

## Response Shape

Use the full structure below for reviews or substantial redesigns:

1. **Diagnosis**
2. **Intent**
3. **Priority map**
4. **Design system choices**
5. **Layout redesign**
6. **Implementation**
7. **Validation**

For narrow implementation tasks, compress the response and patch the code directly instead of forcing every section.
