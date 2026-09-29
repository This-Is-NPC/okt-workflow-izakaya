---
name: okt-plan-continue
description: Preview a plan plus the next claimable task before committing to a claim.
schema_version: 2
role_affinity:
  - Owner
  - Concierge
command:
  name: okt-plan-continue
  next:
    - name: okt-plan-claim
      context: bare
---
Preview a plan before committing to a claim. Nothing is reserved here — this is the look-before-you-leap step.

## Preview the aggregate and the candidate

Call `okt plan continue` for the slug: it returns the full plan aggregate — waves, done/total, active wave — plus a non-mutating preview of the task `okt plan claim` would reserve next. Inspect the goal_body, the wave layout, and the candidate task, then report them. Read-only — nothing is reserved here.
