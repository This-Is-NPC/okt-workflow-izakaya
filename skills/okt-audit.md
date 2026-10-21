---
name: okt-audit
description: Independently audit completed work against its real-artifact evidence.
schema_version: 2
role_affinity:
  - Reviewer
command:
  name: okt-audit
  next:
    - name: okt-task-create
      context: bare
      when: A blocking finding needs a follow-up task
---
Audit completed work once. Read-only for code: post findings; do not fix.

1. **Read the target.** For a plan, read its goal, decomposition, task scopes, and integrated diff. For a task, read its task artifacts and diff.
2. **Verify independently.** Exercise the delivered artifact under its promised conditions, run the full suite once, and re-read state through a separate request, connection, or process.
3. **Probe boundaries.** Check transport, encoding, domain parsing, and rejection responses from the outside inward.
4. **Separate findings.** A user-visible defect or unmet quality attribute is blocking; create one follow-up task per blocker. Put non-blocking findings in one follow-up comment.
5. **Record a verdict.** State the target, evidence, findings, opened tasks, and whether the work is ready.
