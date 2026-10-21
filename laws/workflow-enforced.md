---
name: Workflow enforced
severity: error
---
1. Move tasks only through explicit workflow transitions; never route around a guard.
2. Run `okt move <id> --to <bucket> --dry-run` before a move to see every required artifact.
3. When a move fails, run the `fix` command from its error details instead of guessing syntax.
4. Move to done only after the change is integrated on the integration branch (`git branch --contains <commit>`).
