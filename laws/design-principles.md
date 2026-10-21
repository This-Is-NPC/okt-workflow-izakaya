---
name: Design principles
severity: warning
---
1. Model repeated stateful logic in one state machine, typed model, or table; do not scatter equivalent conditionals.
2. Parse every untrusted input into a domain type at its outermost boundary; reject what cannot parse, including safely handling the rejection path.
3. Make retried or interrupted operations idempotent and atomic when the project has a retry or crash path.
4. Remove dead code and redundant checks in the area before adding new structure.
5. Name the principle that changed a design decision.
