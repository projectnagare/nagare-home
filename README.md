# Project Nagare

**Nagare is an open, programmable operating system for a fully digital bank.**

Nagare asks a simple question:

> If a bank were built from zero today — without branch-era assumptions, legacy core constraints, monolithic banking software, or AI bolted on after the fact — what would it look like?

Nagare is not a neobank skin or a conventional CBS rewrite. It is a complete digital-bank architecture built around a tiny kernel, stable contracts, replaceable plugins, deterministic financial truth, modern institutional software, a continuously running synthetic bank, and a synthetic financial world around it.

The long-term objective is to build the complete stack before a standalone digital-bank licence exists in India, make it useful as an open-source banking platform and hosted sandbox, and ensure that a future licensed bank can move from simulation to production by changing composition rather than rebuilding the institution.

## Start here

1. [The Nagare Constitution](CONSTITUTION.md)
2. [Why Nagare exists](docs/vision/why-nagare.md)
3. [What Nagare means by a digital bank](docs/vision/digital-bank.md)
4. [Architecture overview](docs/architecture/overview.md)
5. [Plugin model](docs/architecture/plugins.md)
6. [Actors, task-level permissions and access](docs/architecture/actors-and-access.md)
7. [AI in Nagare](docs/architecture/ai.md)
8. [Consumer, Business, Institutional and Developer](docs/bank-model/surfaces.md)
9. [The living synthetic bank](docs/simulation/living-bank.md)
10. [Nagare World](docs/simulation/nagare-world.md)
11. [Major decisions](decisions/README.md)
12. [RFC process](rfcs/README.md)
13. [Repository map](docs/project/repository-map.md)

## Constitutional ideas

- The bank is the branch.
- Everything is a plugin.
- The kernel stays small.
- Depend on contracts, not implementations.
- Financial truth is deterministic.
- The ledger contract is sacred; its implementation is replaceable.
- AI is an actor, and AI actors are plugins.
- Authorization is task-level.
- External apps and external infrastructure connect through plugins.
- Simulation and production share one architecture.
- Consumer and Business are independently deployable distributions.
- Institutional is the bank's own operating view.
- Internal banking software deserves consumer-grade UX.
- Work is organized around tasks, decisions, queues, exceptions and outcomes.
- Cost is an architectural concern.
- Replaceability beats lock-in.

## What belongs here

This repository is the **central idea home** for Project Nagare.

It contains the project's philosophy, constitution, architecture, vocabulary, decision log, RFCs, repo map and long-term roadmap. Implementation code belongs in domain repositories.

**All major cross-project decisions should be recorded here.**

## Design system

Nagare's visual source of truth lives in [projectnagare/nagare-design-system](https://github.com/projectnagare/nagare-design-system).

Nagare applications should consume the official design-system packages rather than recreate visual primitives locally.

---

Project Nagare is an experimental open-source banking project. It is not a licensed bank and does not provide real banking services.
