<p align="center"><img src="assets/readme-banner.svg" alt="Nagare" width="100%"></p>

# Project Nagare

**An open, programmable operating system for a fully digital bank.**

Nagare asks one question:

> If a bank were built from zero today — without branch-era assumptions, legacy core constraints, monolithic banking software, or AI bolted on after the fact — what should the institution look like?

Nagare is not a neobank skin or a conventional CBS rewrite. It is a digital-bank architecture built around a tiny kernel, stable contracts, replaceable plugins, deterministic financial truth, task-level access, modern institutional software, a continuously running synthetic bank, a synthetic financial world, and eventually a hosted bank sandbox.

The long-term goal is to build the complete stack **before** a standalone digital-bank licence exists in India, make it useful as an open banking platform and developer environment, and ensure that a future licensed institution can move from simulation to production by changing composition rather than rebuilding the bank.

## What “Nagare” means

**Nagare (流れ)** is Japanese for **flow** — and more broadly the course or progression of something moving through a system.

That meaning is central to the project.

A bank is, fundamentally, a system of flows: money moves between accounts, obligations move through settlement, applications move through decisions, information moves between institutions, and work moves between human and machine actors.

Nagare is designed around making those flows explicit, composable and observable.

The name also connects directly to the visual system:

- **Paper** is the calm ground on which the institution is recorded.
- **Ink** represents precision, permanence and financial truth.
- **Blossom** is the warm accent — a small moment of arrival or change.
- **Ma** — deliberate space — gives the system room to breathe rather than filling every surface with banking clutter.

The name is therefore not decorative branding. It reflects the architecture: **a bank as a set of governed flows moving through stable contracts and replaceable capabilities.**

## Start here

1. **[The Nagare Thesis](docs/vision/nagare-thesis.md)** — the complete intent behind the project.
2. **[The Nagare Constitution](CONSTITUTION.md)** — the laws that should not change casually.
3. **[Architecture Report](docs/architecture/ARCHITECTURE-REPORT.md)** — how the thesis becomes a system.
4. [What Nagare means by a digital bank](docs/vision/digital-bank.md)
5. [Plugin model](docs/architecture/plugins.md)
6. [Actors, task-level permissions and access](docs/architecture/actors-and-access.md)
7. [AI in Nagare](docs/architecture/ai.md)
8. [Consumer, Business, Institutional and Developer](docs/bank-model/surfaces.md)
9. [The living synthetic bank](docs/simulation/living-bank.md)
10. [Nagare World](docs/simulation/nagare-world.md)
11. [Major decisions](decisions/README.md)
12. [RFC process](rfcs/README.md)
13. [Repository map](docs/project/repository-map.md)

## The architecture in one view

```text
                              NAGARE

                         tiny kernel
                             │
                     stable contracts
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
      plugins             actors             external apps
         │                   │                   │
 ledger / payments      human / system      CRM / ERP / CBS
 identity / lending     AI / institution    vendors / rails
         │                   │                   │
         └───────────────────┼───────────────────┘
                             │
               Consumer · Business · Institutional
                             │
                     one financial reality
                             │
              ┌──────────────┴──────────────┐
              │                             │
         Nagare World                 Production World
       synthetic services             real integrations
```

## Constitutional ideas

- **The bank is the branch.**
- **Everything is a plugin.**
- **Plugins are deployment-shape agnostic.**
- **The kernel stays small.**
- **Depend on contracts, not implementations.**
- **Financial truth is deterministic.**
- **The ledger contract is sacred; its implementation is replaceable.**
- **AI is an actor, and AI actors are plugins.**
- **Authorization is task-level.**
- **Access, policy and workflow are separate primitives.**
- **External apps and financial infrastructure connect through plugins.**
- **Simulation and production share one architecture.**
- **Synthetic activity is seeded, reproducible and time-controllable.**
- **Consumer and Business are independently deployable distributions.**
- **Institutional is the bank's own operating view.**
- **Internal banking software deserves consumer-grade UX.**
- **Work is organized around tasks, decisions, queues, exceptions and outcomes.**
- **Mature banking systems inform the domain, not the UX.**
- **Cost is an architectural concern.**
- **Replaceability beats lock-in.**

## The living bank

Nagare Bank should exist continuously before it exists legally.

Synthetic customers and businesses should open accounts, receive salaries, pay merchants, run payroll, borrow, repay, default, trigger fraud alerts, generate settlement breaks and create real work for treasury, risk, finance and operations.

The simulation should work without AI. AI is evaluated **against** the bank, not required for the bank to function.

The same environment should support real-time operation, accelerated time, deterministic replay, scenario injection and failure injection.

## Nagare World

A bank never exists alone.

Nagare World is the simulated external financial system around the bank: bureaus, KYC systems, payment rails, registries, Account Aggregators, tax systems, card networks, market data and other dependencies.

Each simulated service owns its own state and failure modes and plugs into Nagare through the same contracts a production integration would use.

> **Production is another composition of the same bank.**

## The bank's product surfaces

**Nagare Consumer** — personal banking.

**Nagare Business** — business banking.

**Institutional** — the bank's own view of itself: treasury, ALM, liquidity, capital, finance, risk, compliance, fraud, regulatory reporting, audit, servicing and operations.

**Developer** — the APIs, sandbox, plugin ecosystem and hosted synthetic-bank environment builders use.

Consumer and Business are independently deployable. Institutional still sees one institution and one financial reality.

## Hosted Nagare

The hosted product should give builders a complete fake bank, not mock endpoints.

A sandbox can expose fake customers, businesses, accounts, cards, loans, bureau/KYC, payment rails, employee logins, API keys, webhooks, ledger state, Consumer/Business/Institutional surfaces, reset/replay, accelerated time and controlled failures.

## Central idea home

This repository is the canonical home for Project Nagare's:

- philosophy;
- Constitution;
- architecture;
- terminology;
- decision record;
- RFCs;
- repository map;
- and long-term roadmap.

Implementation code belongs in capability repositories.

**Every major cross-project decision must be recorded here.**

## Design system

Nagare's visual source of truth is [projectnagare/nagare-design-system](https://github.com/projectnagare/nagare-design-system).

User-facing Nagare repositories should consume the official tokens, icons and UI packages rather than recreate visual primitives locally.

The design language is built around **Paper, Ink, Blossom and ma**. The same system spans Consumer, Business, Institutional and Developer experiences.

---

Project Nagare is an experimental open-source banking project. It is not a licensed bank and does not provide real banking services.
