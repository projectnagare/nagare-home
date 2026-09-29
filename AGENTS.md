# Instructions for Coding Agents

Before modifying any Project Nagare repository:

1. Read `CONSTITUTION.md`.
2. Read `docs/vision/nagare-thesis.md`.
3. Read `docs/architecture/ARCHITECTURE-REPORT.md`.
4. Read relevant domain documents.
5. Check `decisions/` and `rfcs/`.
6. Never depend on another plugin's implementation when a contract should be used.
7. Treat “plugin” as an architectural relationship, not an in-process requirement.
8. Keep financial truth deterministic.
9. Do not give AI actors privileged access paths.
10. Treat authorization as task-level and keep access, policy and workflow distinct.
11. Keep the kernel small.
12. Synthetic activity must not require AI.
13. Prefer simulation/production parity: synthetic and real providers should implement the same contracts.
14. Use the official Nagare design system for every user-facing interface.
15. Do not recreate Nagare tokens, colors, typography, icons or core UI primitives locally.
16. Institutional UX should organize around work, decisions, queues, exceptions and outcomes rather than backend modules.
17. Record every major cross-project decision in `nagare-home/decisions`.

If an implementation appears to violate a constitutional rule, propose an RFC rather than silently working around it.
