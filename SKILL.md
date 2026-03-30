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

Treat this skill as a facelift, not a cosmetics pass. If the interface is confusing, noisy, or visually flat, change the structure hard enough that the result feels noticeably clearer within seconds.

## Core Objective

Reduce user effort.

Translate the user's goal into the shortest clear path through the interface, then implement the layout, component, and styling changes needed to support that path.

The desired effect is obvious improvement, not subtle rearrangement. Users should feel that the screen became cleaner, faster, and more decisive.

## Operating Rules

1. Make one next action obvious.
2. Show only what is needed for the current step.
3. Make structure work before adding decoration.
4. Let spacing, alignment, and typography carry hierarchy first.
5. Treat color, borders, shadows, and icons as supporting signals.
6. Preserve consistency across similar components and states.
7. Prefer familiar patterns over clever ones.
8. If the current screen feels bloated, cut harder.
9. If two elements compete for attention, pick a winner.
10. If decoration is carrying comprehension, remove the decoration and fix the structure.

## Non-Negotiables

- Do not preserve clutter just because it already exists.
- Do not keep tertiary controls in the main scan path without a strong reason.
- Do not add visual styling to avoid making hierarchy decisions.
- Do not describe a better UI when you can implement one.
- Do not accept "more visible" as automatically "more usable."
- Do not let secondary actions look equal to the primary action.

## Face-Lift Standard

Aim for a before-and-after difference that is immediately visible.

The result should typically feel like:
- fewer things competing for attention
- a stronger focal point
- cleaner grouping
- less explanatory text
- more deliberate spacing
- more confident typography
- fewer low-value surfaces, borders, and wrappers

If the revised UI still feels like the same screen with slightly better spacing, push further.

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

When deciding whether to keep or remove something, default to removal until it earns its place.

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

Be willing to:
- collapse noisy toolbars
- merge fragmented cards into clearer sections
- move weak secondary actions out of the hero area
- reduce label density when layout already conveys meaning
- replace "everything is important" layouts with a single dominant story

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
- Make primary content hard to miss and secondary content easy to ignore until needed.

### Affordance

- Make clickable elements look clickable.
- Make editable fields visibly editable.
- Make disabled controls distinct without making them disappear.
- Add labels to icon-only controls.

### Data-Dense Views

- Align repeated structures consistently.
- Right-align numeric columns and use monospace when tabular values need precise scanning.
- Remove borders and dividers that do not improve comprehension.
- Increase density through alignment and rhythm, not visual noise.

### Motion

- Use motion to guide attention, not decorate.
- Keep transitions short and non-blocking.

### Accessibility

- Preserve visible keyboard focus.
- Avoid `div` or `span` click targets when a semantic control exists.
- Maintain reasonable contrast and readable text sizes.
- Treat accessibility fixes as part of the redesign, not optional cleanup.

## Escalation Rule

Escalate the redesign when you see any of these patterns:
- more than one main CTA presented as equally important
- every card, panel, or widget styled to shout at the same volume
- controls displayed preemptively instead of contextually
- long labels compensating for weak layout
- repeated borders, boxes, and iconography doing the work of structure
- key information buried below metadata or chrome

In those cases, make bolder changes. Reorder, merge, hide, simplify, and delete until the interface tells a clear story.

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
