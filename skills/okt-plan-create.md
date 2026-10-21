---
name: okt-plan-create
description: Author a WBS-style plan grouping child tasks into ordered waves with a goal body.
schema_version: 2
role_affinity:
  - Owner
command:
  name: okt-plan-create
  next:
    - name: okt-plan-show
      context: bare
      when: Verify the assembled plan
    - name: okt-run
      context: bare
      when: The plan is verified
---
Create an execution plan whose waves, assignments, and dependencies are persisted.

1. **Set identity and goal.** Use a unique kebab-case slug, a name, and `okt template show plan-goal` for the outcome, scope, quality attributes, verification, and exclusions.
2. **Create waves and assignments.** Run `okt plan wave-add <slug> "<name>"` in order and `okt plan assign <slug> <wave-id> <task-id>` for every task.
3. **Record dependencies.** Run `okt depend add <task> --on <blocker>` for every ordering edge; waves do not replace the dependency graph.
4. **Map modules.** Post `comment-decomposition` on the plan. Each task owns one cohesive module; parallel work has disjoint files, and interfaces land before dependents.
5. **Record council decisions.** Post `comment-council` on the plan, including a decision and reason for each concern raised.
6. **Verify.** Run `okt plan show <slug>` and `okt depend list <id>`; no wave is empty and no task is unassigned.
