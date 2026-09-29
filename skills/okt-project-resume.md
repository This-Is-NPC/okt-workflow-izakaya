---
name: okt-project-resume
description: Scan likely-next work across the active project.
schema_version: 2
role_affinity:
  - Concierge
command:
  name: okt-project-resume
  next:
    - name: okt-task-continue
      context: bare
---
Scan for the next work to pick up. This is the cold scan across the project, not a warm hand-back of a known thread.

## Scan and report

Call `okt project resume` and report the top candidates, each with a one-line rationale so the user can choose with context rather than guessing.
