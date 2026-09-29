---
name: okt-task-debrief
description: Capture learnings from completed work — decisions that held, assumptions that broke.
schema_version: 2
role_affinity:
  - Scribe
  - Reviewer
command:
  name: okt-task-debrief
  next:
    - name: okt-task-document
      context: bare
---
Close the loop on completed work — capture what was learned, not what was done. The debrief makes the next task start smarter.

## Distill the learnings

Distill the decisions that held, the assumptions that broke, and the follow-ups worth carrying forward.

## Record the debrief

Call `okt template show` for any bound lessons scaffold, fill it, and persist the debrief with `okt comment add` on the task or project that owns the completed work. Stay read-only with respect to code.
