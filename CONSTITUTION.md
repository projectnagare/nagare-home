# The Nagare Constitution

The Constitution records the architectural laws of Project Nagare. Implementations may change. These principles should not change casually.

## 1. The bank is the branch

Nagare does not treat the physical branch as a core primitive. Customers, accounts, workflows and financial state belong to the bank. Branch identifiers may exist for regulation or compatibility, but they must not define the internal architecture.

## 2. Everything is a plugin

Every meaningful banking capability should be replaceable behind a stable contract. A plugin may run in-process, as a sidecar, as an independent service, as a remote API, or as an adapter to a third-party system.

## 3. The kernel stays small

The kernel coordinates the ecosystem. It does not become the bank. It should primarily own plugin lifecycle, capability registration, dependency resolution, configuration, actor context, access hooks, events, observability, compatibility and failure semantics. Deposits, lending, payments, cards, KYC, bureau access, fraud, treasury, risk and AI are capabilities, not kernel responsibilities.

## 4. Depend on contracts, not implementations

A Nagare plugin may depend on a contract. It must not depend on another plugin's implementation.

## 5. Financial truth is deterministic

Money, balances, journals, holds, settlement state and accounting truth must be deterministic, reconstructable and auditable. AI may investigate, recommend, explain or execute delegated tasks. AI never decides whether money exists.

## 6. The ledger contract is sacred; the implementation is not

Nagare requires strong financial semantics: double entry, immutability, idempotency, reversals, effective time, pending/posted states and auditability. The native Nagare ledger is one implementation of that contract, not the only possible implementation.

## 7. AI is an actor

Nagare is AI-native because machine actors are first-class participants in the institution. An AI actor has identity, permissions, capabilities, limits, policies, tools, supervision and an audit trail.

## 8. AI actors are plugins

The bank must not depend on any specific AI implementation. A task may be fulfilled by a human actor, deterministic system actor, Nagare AI actor, third-party AI actor, or no AI at all. Removing every AI plugin must not make financial correctness impossible.

## 9. Authorization is task-level

Authorization evaluates **actor + task + resource + context + policy**. Access is not equivalent to seeing a screen or belonging to a module.

## 10. External systems are plugins too

External CRMs, ERPs, CBS platforms, loan systems, treasury systems, payment networks, bureaus, government systems and other applications should integrate through contracts and adapters rather than implementation leakage.

## 11. Simulation and production share one architecture

A synthetic bureau and a real bureau are alternative implementations of the same contract. A synthetic payment rail and a production rail are alternative implementations of the same contract. Production should be a different composition of plugins, not a rewrite.

## 12. The external world maintains independent state

Nagare World should behave like an ecosystem, not a set of hard-coded mocks. External simulated services own their state, timing, failures and information boundaries.

## 13. Consumer and Business are distributions

Nagare Consumer and Nagare Business are independently deployable compositions of banking capabilities. Neither should require the other.

## 14. Institutional is the bank's view

Institutional is the bank's internal operating surface: treasury, ALM, liquidity, finance, risk, compliance, fraud, regulatory reporting, audit, operations, servicing and internal approvals.

## 15. The institution has one financial reality

Consumer and Business may be separate business units, but treasury, finance, capital, liquidity and institutional risk must see the whole bank.

## 16. Internal software deserves consumer-grade UX

A treasurer, credit analyst, fraud investigator, operations executive or compliance officer deserves software as carefully designed as the retail customer.

## 17. Work, not modules

Institutional interfaces should prioritize tasks, decisions, queues, exceptions and outcomes rather than exposing backend module boundaries.

## 18. Cost is an architectural concern

Nagare exists partly to ask how cheaply a bank can operate. Cost per customer, transaction, loan, asset base, operational case and AI action should eventually be measurable.

## 19. Replaceability beats lock-in

No implementation becomes sacred merely because it was built first.

## 20. The system should be launchable before it is licensed

Nagare should run continuously as a synthetic bank before a standalone digital-bank licence exists. If a suitable licence later becomes available, the objective is to replace synthetic integrations with production integrations and complete certification, not rebuild the bank.
