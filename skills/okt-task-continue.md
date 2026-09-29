---
name: okt-task-continue
description: Read a task's checkpoint before resuming work.
schema_version: 2
role_affinity:
  - Builder
command:
  name: okt-task-continue
  next:
    - name: okt-task-implement
      context: bare
---
Read a task's checkpoint — understand where the task stopped, do not start coding. This is orientation, not execution.

## Read the checkpoint

Call `okt task continue` for the task id, then summarize the last decision, the open questions, and the immediate next increment so you resume the thread rather than restarting it.
