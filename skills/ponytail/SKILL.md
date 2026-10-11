---
name: ponytail-lite
metadata:
  version: '4.9.0'
description: 按需使用 Ponytail Lite，在计划、编码或审查中先理解调用链，再选择满足需求的最小实现。
license: MIT
---

# Ponytail Lite

Apply this Skill only to the explicitly assigned coding task. It ends with that task. Do not persist it across later turns or propagate it to subagents unless the dispatch message names this Skill.

Lite means efficient, not careless: build what was requested, preserve necessary consequences, and name a meaningfully simpler valid alternative in one line when the user has a real choice. Never silently replace an explicit requirement merely because a smaller solution exists.

## Understand before minimizing

Read the task and the code it actually touches before choosing a smaller solution. For a bug fix, inspect callers of the function or boundary you may change and locate the shared cause. A small patch at the wrong layer is another bug, not a lazy solution.

Use this ladder after understanding the flow. Stop at the first rung that satisfies the requested result:

1. The capability does not need to exist.
2. The codebase already provides it.
3. The standard library provides it.
4. The platform provides it natively.
5. An already-installed dependency provides it.
6. A small local implementation is necessary.

The ladder is a decision aid, not a new research project. Search only as far as the current choice requires.

## By task mode

### Plan

- Trace the affected flow before proposing components or phases.
- Reuse current modules, conventions and dependencies.
- Leave speculative abstractions, compatibility layers and future configuration out of the plan.
- State one simpler alternative only when it would change the user's decision.

### Change

- Fix the shared root cause when reachable callers show one.
- Change the fewest necessary files after the real boundary is understood.
- Keep input validation at trust boundaries, data-loss prevention, security, accessibility, migrations and compatibility that reachable evidence requires.
- Leave the smallest proportionate runnable check for non-trivial logic; do not add a testing framework or broad suite without a task-specific reason.

### Review

- Report unnecessary abstractions, dependencies, wrappers, speculative flexibility and duplicated platform or standard-library behavior.
- Give each finding a location, what can be removed, and the simpler replacement.
- Do not apply fixes during Review unless the task explicitly authorizes a change.
- Do not treat correctness, security or required compatibility work as bloat.

## Finish

Return the requested result and the evidence that makes it complete. Mention skipped work only when the omission affects the user's decision. Stop when the requested result has enough evidence; do not add another improvement or audit loop for this Skill.
