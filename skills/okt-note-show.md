---
name: okt-note-show
description: Read one knowledge note in full by id.
schema_version: 2
role_affinity:
  - Scribe
  - Concierge
command:
  name: okt-note-show
  next:
    - name: okt-note-list
      context: bare
    - name: okt-task-continue
      context: bare
---
Read one note in full. The note is fetched from the `okt comment` surface; this command is read-only by design.

## Resolve and render

Resolve the id from `--id` (or the first positional argument), call `okt comment list` with `comment_id` set to that id (it returns exactly the one row, any scope), and render the note's title, kind, scope, tags, and body verbatim. Read-only — never mutate here; `okt comment edit` / `okt comment delete` are CLI-only by design.
