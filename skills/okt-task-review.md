---
name: okt-task-review
description: Walk the diff through Fowler/Beck/Martin/Feathers lens and surface findings + refactor opportunities.
schema_version: 2
role_affinity:
  - Reviewer
command:
  name: okt-task-review
  next:
    - name: okt-task-implement
      context: bare
      when: Findings need fixes
---
Review the diff. Read-only: post findings; do not edit or commit.

1. **Read every hunk.** Run `git diff <base>..HEAD` (`main` unless named).
2. **Review in order.** Check correctness, security, smells, refactoring opportunities, and performance; name the method where useful and severity-tag each finding.
3. **Probe boundaries.** For each external input, derive valid, invalid, and edge classes. Record each as unrepresentable by type, rejected at parsing, or tested in `#boundary` from `comment-boundary`.
4. **Post artifacts.** Fill `comment-review-findings` and, where needed, `comment-refactor-opportunities`; add them as task comments.
