---
name: Comment Boundary
description: Input-domain analysis before a task is done.
entity: comment
default: comment-boundary
laws:
  - template-fidelity
---
One row per input class at each boundary the change touches. Start at transport and encoding before domain fields; include the rejection response.

| Boundary | Input class | Handled by | Evidence |
| --- | --- | --- | --- |
| <entry point> | <valid / invalid / edge class> | type (unrepresentable) · parse (rejected at boundary) · test | <type, parser, or test name> |

**Unhandled** — <classes with no handling, as findings; "none">

Write `n/a: <reason>` when the change touches no external input.
