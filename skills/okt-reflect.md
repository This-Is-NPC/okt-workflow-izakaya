---
name: okt-reflect
description: Turn recorded corrections and guard friction into proposed rule changes.
schema_version: 2
command:
  name: okt-reflect
  parameters:
    - name: period
      type: string
      required: false
  next:
    - name: okt-task-create
      context: bare
      when: The user approved a change to implement
---
Propose rule changes from recorded failures. Read-only: propose; the user decides.

1. **Collect corrections.** Run `okt error list --tag agent-correction`, search recorded solutions, and rank them with `okt solution list-top`.
2. **Collect friction.** Run `okt insights summary`, guard logs for the requested period (default `7d`), and `okt metrics summary --period <period>`.
3. **Group each cause** as a missing rule, ambiguous rule, contradictory rule, or a product gap no rule can fix.
4. **Propose the smallest change** in a preset law, command, guard, project `AGENTS.md`, or an Omakiten issue. Prefer a guard, template, or check over more prose.
5. **Present evidence and exact text** for every proposal. Apply nothing without approval.
