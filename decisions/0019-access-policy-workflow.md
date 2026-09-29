# 0019 — Access, policy and workflow remain separate primitives

**Status:** Accepted

Nagare separates identity, access, policy, workflow and audit.

Access evaluates whether an actor may attempt a task on a resource in context. Policy evaluates institutional rules. Workflow determines sequence and approvals. Audit records authority and outcome.

Maker-checker and delegated authority should be expressed through these primitives rather than duplicated inside domain applications.
