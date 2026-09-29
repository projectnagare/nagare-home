# Instructions for Coding Agents

Before modifying any Project Nagare repository:

1. Read CONSTITUTION.md.
2. Read docs/architecture/overview.md.
3. Read relevant domain documents.
4. Check decisions/ and rfcs/.
5. Never depend on another plugin's implementation when a contract should be used.
6. Keep financial truth deterministic.
7. Do not give AI actors privileged access paths.
8. Treat authorization as task-level.
9. Keep the kernel small.
10. Use the official Nagare design system for user-facing interfaces.
11. Record major cross-project decisions in nagare-home.

If an implementation appears to violate a constitutional rule, propose an RFC rather than silently working around it.
