---
name: address-all-similar-instances-skill
description: "Generalize one proven problem into its broader failure class, map the nearest related surfaces in the code and UX hierarchy, and finish the full high-confidence cluster so the user does not need to ask again."
---

# Address All Similar Instances Skill

Use this skill when the user is signaling:

- "fix all similar cases"
- "don't make me ask again"
- "address all instances"
- "finish the whole thing"
- "read the broader context and fix the rest"
- "you only fixed one example"

The user's seed issue or annoyance is:

`$ARGUMENTS`

## Core Rule

Do not stop at literal duplicates.

The first proven issue is only the seed. Your real job is to infer the broader class of problem, then address the closest related instances across the same hierarchy, workflow, component family, and user journey.

## What Counts As "Similar"

Similarity is not just exact code duplication.

Treat issues as similar when they share one or more of these:

- same user-facing failure class
- same friction archetype
- same root decision pattern
- same component family or wrapper
- same route family or workflow step
- same analytics / validation / feedback blind spot
- same mobile-vs-desktop divergence
- same "user would perceive this as the same kind of annoyance" test

Examples:

- not just one silent disabled CTA, but any nearby CTA that blocks without clear action-point feedback
- not just one copy block, but the same kind of redundant or explanatory wording across sibling flows
- not just one broken event capture, but the same fallback pattern in client/server twins
- not just one posting-form friction point, but the same "buried requirement / late surprise / weak guidance" pattern across adjacent form sections

## Required Workflow

1. Lock onto the first proven issue.
2. Name the broader failure class in general terms, not file-specific terms.
3. Build an adjacency map before editing.
4. Search the code and UI hierarchy for the nearest related surfaces.
5. Split findings into:
   - literal duplicates
   - same-class sibling instances
   - same-workflow adjacent instances
   - lower-confidence lookalikes
6. Fix the full high-confidence set.
7. Verify the important surfaces.
8. Re-ask the completion question from the user's perspective.
9. Only stop when the remaining related inventory is empty, low-confidence, intentionally out of scope, or blocked.

## Adjacency Map Requirement

Before claiming a sweep is complete, inspect the closest related surfaces in at least these dimensions when they exist:

- same file
- same component family
- same route family
- same user workflow
- same shared helper / utility / hook
- same desktop and mobile action surfaces
- same loading / empty / invalid / success / error states
- same client and server instrumentation path

## Discovery Methods

Do not rely on intuition alone. Use direct discovery.

Always combine several of these:

- grep for the same prop, helper, guard, event name, copy string, CSS token, or disabled pattern
- inspect imports and exports around the seed issue
- inspect callers and callees of the implicated helper or component
- inspect sibling routes in the same product cluster
- inspect variants in the same page family
- inspect wrapper components that standardize the behavior
- inspect analytics / tracking twins on client and server
- inspect visible UI states in the running app when feasible

## Hierarchy Rules

When a seed issue is found, walk outward in this order:

1. exact line or function
2. same file
3. same component or hook family
4. same route or feature cluster
5. same end-to-end workflow
6. client/server twin or instrumentation twin

Do not jump to repo-wide cleanup before exhausting the nearest hierarchy.

## Scope Discipline

- Expand by failure class and adjacency, not by vague similarity.
- Stay anchored to the proven user annoyance.
- Do not turn one issue into a random cleanup pass.
- If something is only visually or semantically similar but not the same class, note it and move on.

## Verification Standard

For every important same-class cluster:

- verify the real route when feasible
- verify the real user action point, not only static rendering
- verify desktop/mobile if both can diverge
- verify code-only only when runtime proof is blocked
- verify the neighboring surfaces you explicitly claimed to have swept

## Completion Test

Before finishing, explicitly run this mental checklist:

1. What was the seed issue?
2. What is the broader class of problem?
3. What is the nearest hierarchy around it?
4. Which sibling and adjacent surfaces did I inspect?
5. Which of them had the same class of issue?
6. Which did I fix?
7. What would still make the user say "you only fixed one"?

If item 7 still has a credible answer, keep going.

## Response Behavior

- Tell the user briefly that you are sweeping the broader failure class, not just exact duplicates.
- Keep updates short.
- Prefer execution over theorizing.
- Report the cluster you checked, not just the first file.
- Do not stop with generic next steps if high-confidence related work remains.

## Example Triggers

- One payment CTA looks dead. Check the broader monetization workflow for any action-point blocker with weak or missing feedback.
- One posting requirement is buried. Check the posting flow for other late surprises in the same form hierarchy.
- One analytics fallback is wrong. Check the same exception / event family in client and server twins.
- One category page has browse friction. Check sibling route families using the same chip/search/filter pattern.
