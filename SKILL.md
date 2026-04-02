---
name: address-all-similar-instances-skill
description: "Expand a fix beyond the first discovered example and address the full same-class issue across the real affected surface. Use when the user is frustrated that the agent fixed one instance but left sibling instances, related routes, or the same failure pattern elsewhere."
---

# Address All Similar Instances Skill

Use this skill when the user is signaling:

- "fix all similar cases"
- "don't make me prompt again"
- "address all instances, not just one"
- "finish the task completely"
- "read more previous messages and understand it globally"

The user's concrete same-class issue is:

`$ARGUMENTS`

## Core Rule

Do not stop after fixing the first visible example.

When a real bug, friction point, copy issue, layout defect, analytics mistake, or logic failure is found, treat that first example as a pattern candidate. Then verify whether the same pattern exists in sibling files, related routes, related states, adjacent flows, mobile/desktop variants, and parallel components that share the same user journey.

## What This Skill Is For

Use it when the user clearly wants:

- global completion instead of one-off spot fixes
- the same class of issue removed everywhere relevant
- fewer repeated correction turns
- the task closed in the most complete practical way

Do not use it to justify random repo-wide cleanup. The sweep must stay anchored to the proven issue pattern.

## Required Workflow

1. Lock onto the first proven issue.
2. Define the exact failure pattern in one sentence.
3. Find all high-confidence sibling instances of that same pattern.
4. Rank them by user impact and likelihood of being the same root problem.
5. Fix the highest-confidence full set, not just the first file.
6. Verify each important surface with the fastest real proof available.
7. Before closing, ask: "If I were the user, what similar thing would I be annoyed is still unfixed?"
8. Only stop when the remaining same-class inventory is empty, low-confidence, or blocked by real constraints.

## Pattern Expansion Rules

When you fix one issue, automatically check for:

- same component reused elsewhere
- same CTA pattern on nearby pages
- same disabled-state behavior in related payment flows
- same copy or helper-text defect in other variants
- same analytics event or capture bug in client and server twins
- same mobile and desktop action surfaces
- same route in logged-in, guest, empty, loading, and success/error states

## Scope Discipline

- Expand by pattern, not by boredom.
- Do not turn one bug into a vague cleanup marathon.
- Only include instances that are meaningfully the same class of issue.
- If an instance looks similar but has a different root cause, treat it separately and say so.

## Verification Standard

For every major same-class fix:

- verify the real route or runtime surface when feasible
- verify both desktop and mobile if both are user-facing
- verify code paths only when runtime proof is blocked
- do not claim "all addressed" unless you actually checked the sibling surfaces

## Completion Test

Before you finish, explicitly run this check:

1. What was the first proven issue?
2. What other surfaces could reasonably share it?
3. Which of those did I actually inspect?
4. Which of those did I actually fix?
5. What same-class issue would still make the user say "you only fixed one"?

If you still have a credible answer to item 5, keep going.

## Response Behavior

- Tell the user briefly that you are sweeping the same-class pattern across the broader affected surface.
- Keep updates short.
- Prefer execution over theorizing.
- Do not end with generic "next steps" if more same-class execution is still possible.

## Example Triggers

- One silent disabled payment button was found. Check all monetization flows for the same silent dead-end.
- One helper copy block is too wordy. Check the sibling posting surfaces using the same copy style.
- One analytics capture fallback is broken. Check client/server twins and similar exception paths.
- One category page has filter-chip friction. Check sibling category or promote flows using the same chip/CTA pattern.
