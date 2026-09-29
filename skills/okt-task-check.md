---
name: okt-task-check
description: Run discovered test/lint targets and report pass/fail in a tabular comment.
schema_version: 2
role_affinity:
  - Tester
command:
  name: okt-task-check
  next:
    - name: okt-task-implement
      context: bare
    - name: okt-task-review
      context: bare
---
Run the project's check targets. This is the mechanical gate — you run the targets and report, you never fix.

## Discover the targets

Discover the targets via `mise tasks` first; fall back to `npm run`, `make -qp`, `package.json > scripts`, or the repo's `CONTRIBUTING.md` — stop at the first hit, do not guess.

## Invoke and capture

Invoke each target via Bash and capture stdout, stderr, and the exit code.

## Report in a table

Call `okt template show comment-check-report` for the scaffold, fill it — one row per target with status (`pass` / `fail` / `skip` / `yellow`) and a one-line failing tail — then persist it with `okt comment add` on the task (`author_type=agent`). Quote the last ≤10 lines of stderr verbatim per failed target; never summarize errors. Read-only — never apply fixes, never re-run after editing.
