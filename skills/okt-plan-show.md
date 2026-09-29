---
name: okt-plan-show
description: Inspect one plan — wave layout, done/total counts, percent, and the active wave.
schema_version: 2
role_affinity:
  - Owner
  - Concierge
command:
  name: okt-plan-show
  next:
    - name: okt-plan-continue
      context: bare
    - name: okt-plan-claim
      context: bare
---
Inspect one plan's structure. This is a read-only snapshot — you surface the state, you do not mutate it.

## Report the structure

Call `okt plan show` for the slug and report the wave layout, the per-wave and overall done/total counts, the integer percent complete, and the active wave — the lowest-position wave with pending work.
