---
name: okt-task-estimate
description: Size each increment with a relative estimate and a one-line basis-of-estimate.
schema_version: 2
role_affinity:
  - Owner
  - Builder
command:
  name: okt-task-estimate
  next:
    - name: okt-task-design
      context: bare
---
Size each increment. Estimates are relative and explicit, not gut feel left unstated.

## Attach a relative estimate

Attach a relative estimate — points or t-shirt size — to every slice, each with a one-line basis-of-estimate so the number can be questioned. Persist the sizing note with `okt comment add` (or `okt progress record` when updating an existing task checkpoint).

## Flag the uncertain slices

Flag the increments whose uncertainty dominates, since those are where the plan is most likely to slip. Stay read-only.
