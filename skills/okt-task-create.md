---
name: okt-task-create
description: PLAN → DO handoff — author the task with an INVEST-checked story; record prioritization when alternatives exist.
schema_version: 2
role_affinity:
  - Ideator
  - Owner
command:
  name: okt-task-create
  next:
    - name: okt-task-implement
      context: bare
      when: The task is in development
---
Author a task; creation only.

1. **Check feasibility.** Stop and report an infeasible request; do not create a task.
2. **Fill the story.** Use `okt template show user-story` (or `task-bugfix`), with INVEST checks and a SMART success definition.
3. **Create it.** Run `okt task create -t "<title>" --file -` with the filled body.
4. **Resolve duplicates.** Show returned `similar_tasks` and wait for confirmation before using `--confirm`.
5. **Prepare development.** Post `#scope` from `okt template show comment-scope`, then `#self-branch`, before moving to development.
