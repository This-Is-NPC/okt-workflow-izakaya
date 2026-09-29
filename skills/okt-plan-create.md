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
---
Author a WBS-style plan that groups child tasks into ordered waves. The plan is the execution skeleton; settle its shape and persist the grouping before committing it.

## Settle the identity and goal

Settle the slug (kebab-case, unique per project), a human-readable name, and a markdown `goal_body` stating the plan's intent and acceptance criteria before committing. Call `okt plan create` with the filled fields.

## Build the wave layout

After the shell exists, call `okt plan wave-add` for each ordered wave and `okt plan assign` for every existing task that belongs in that wave. If the plan encodes task ordering, persist each blocker edge with `okt depend add`. Verify with `okt plan show`; a plan with no waves or no assigned tasks is only a shell, not an assembled plan.
