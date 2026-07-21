# Contribution 2: Use j/k instead of arrow keys for page navigation
 #2648


**Contribution Number:** 2  
**Student:** Damnarcos Estevez 
**Issue:**   ](https://github.com/npmx-dev/npmx.dev/issues/2648)
**Status:** Phase III in progress

---

## Why I Chose This Issue

This seems like a remapping issue, where the focus is to remap snavigationinto j/k, which seems something I would be able to implement easily while written on languages im familiar with.

---

## Understanding the Issue

### Problem Description

Remap scrolling to j/k to enable better arrow key customization

### Expected Behavior

J/K navigates the page

### Current Behavior

Only arrow keys navigate the page.

### Affected Components

Anywhere where navigation would be used

---

## Reproduction Process

### Environment Setup

install node.js and pnpm. 
Problematic in windows due to antivirus, install pnpm through npm as the guide states.

### Steps to Reproduce

Simply navigate the page, it is done with arrow keys

### Reproduction Evidence

https://github.com/elracing/npmx.dev/tree/fix-issue-2648

running the app through pnpm run dev opens up the app, the issue wants to make navigation through j/k instead of keys. 

---

## Solution Approach

### Analysis

Navigation is bound to arrow keys

### Proposed Solution

change navigation bindings related to arrow keys to j/k

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** 
Navigation is bound to arrow keys, want to change to j/k

**Match:** Binding is done through codebase, just change keys

**Plan:** 
modify key bindings to j/k while allowing certain requested features bound to arrow keys.

**Implement:** https://github.com/elracing/npmx.dev/tree/fix-issue-2648

**Review:** Y

**Evaluate:** Check that j/k can be used, while keeping arrow keys for other purposes

---

## Testing Strategy

IN PROGRESS: currently evaluating test options and understanding overall the structure of the keyboard binds, usually I struggle with tests.

The following high level plan seems to most of what is asked, this is what I have so far.

## Plan: search result keyboard navigation

Update the search results page so result navigation uses j/k instead of arrow keys, while preserving Enter-based activation and keeping editable fields unaffected. Add a focused regression test around the navigation mapping and verify it with the relevant unit test run.

### What to change
1. In app/pages/search.vue, replace the current result-navigation handling so:
   - j moves to the next result
   - k moves to the previous result
   - Enter still activates the focused result
   - arrow keys no longer hijack this flow for page-level result navigation

2. Keep the behavior safe for editable fields by reusing the existing guard logic in app/utils/input.ts, so typing in an input, textarea, or contenteditable element is not disrupted.

3. Add a regression test around the new keyboard mapping in test/unit/app/utils/search.spec.ts (or a nearby app-utils test file) so this stays covered.

### Scope boundaries
- This is scoped to the search results experience.
- Do not change arrow-key behavior in accessibility-critical controls such as app/components/VersionSelector.vue or app/components/UserCombobox.vue, since those are intentionally keyboard-driven UI patterns.

### Verification
- Run the targeted unit test for the new keyboard mapping.
- Manually verify on the search page that:
  - j/k move between results
  - arrow keys scroll the page normally
  - Enter still opens/selects the focused item

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
