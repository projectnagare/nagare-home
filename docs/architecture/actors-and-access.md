# Actors, Access and Task-Level Permissions

Nagare treats humans, systems and machine actors through a common authorization model.

An actor may be a human, deterministic system process, AI actor, external institution or another authorized machine identity.

Authorization is evaluated at the level of a task, not a screen or module.

**Actor + Task + Resource + Context + Policy = Authorization decision**

Examples include loan.read, loan.review, loan.approve, loan.disburse, payment.create, payment.authorize, payment.release, payment.reverse, ledger.post, funding.propose and funding.execute.

This enables delegated authority, amount limits, maker-checker, contextual controls and AI governance to be expressed consistently.

AI actors must pass through the same authorization system as humans. No AI plugin receives implicit privilege.
