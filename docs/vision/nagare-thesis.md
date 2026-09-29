# The Nagare Thesis

Project Nagare asks one question:

> If a bank were built from zero today, without branch-era assumptions, legacy core constraints, monolithic banking software, or AI bolted on after the fact, what should the institution look like?

Nagare is an open, programmable operating system for a fully digital bank, a continuously running synthetic bank, a synthetic financial world around it, and eventually a hosted development platform where anyone can build against the capabilities of a complete bank.

Nagare is not a neobank skin. It is not a prettier CBS. It is not an AI wrapper around traditional banking software.

It is an attempt to rethink the institution itself.

## Why digital-only matters

A digital-only bank is not simply a bank that has an app and no branches. It is a bank designed around the assumption that the physical branch is not an architectural primitive.

Nagare therefore adopts a constitutional rule:

> **The bank is the branch.**

Customers, accounts, workflows, permissions, products and financial state belong to the institution. Branch identifiers may exist where regulation or interoperability requires them, but branch-era concepts should never shape the internal architecture.

This is what makes it possible to design the bank as one coherent software-defined institution.

## Why Nagare exists

Nagare has four simultaneous purposes.

### 1. A bank-in-waiting

India does not currently operate a standalone digital-bank licensing regime. Nagare should nevertheless build the complete technology and operating architecture now.

If India later creates a viable licence for a Digital Consumer Bank, Digital Business Bank, or equivalent category, the goal is not to begin a multi-year CBS programme. The goal is to instantiate the appropriate Nagare distribution, replace synthetic integrations with production integrations, certify the environment, capitalise the institution and launch.

### 2. A real banking laboratory

Developers rarely get access to an entire bank. Nagare should provide one.

Nagare Bank should exist continuously with synthetic customers, businesses, accounts, cards, loans, merchants, employers, payments, defaults, fraud, treasury positions, risk events, regulatory events, balance sheets and P&Ls.

The bank should behave even when no human or AI is interacting with it.

### 3. A hosted bank sandbox

Nagare should eventually be available as a hosted service.

A builder should be able to create a sandbox bank, receive fake customer credentials, API keys and webhooks, log in as a synthetic customer or bank employee, generate activity, inject failures, accelerate time, replay a scenario and inspect the resulting ledger and institutional state.

This is not a collection of mock APIs. It is a programmable synthetic financial institution.

### 4. A lower-cost model for financial intermediation

Nagare should continuously ask how much banking cost is structural and how much is inherited from historical operating models.

The project should make cost measurable at the architecture level: cost per active customer, transaction, loan originated, operational case, crore of assets, AI action and unit of regulatory work.

The ambition is to make financial intermediation materially cheaper, creating room for better depositor returns, cheaper borrower pricing and a healthy spread.

## Everything is a plugin

Nagare's deepest engineering primitive is:

> **Everything is a plugin.**

This does not mean “a monolith with extension points.”

It means the bank is a composition of stable contracts and replaceable implementations.

A plugin may run:
- in-process;
- as a sidecar;
- as an independent service;
- as a remote hosted API;
- or as an adapter to an existing third-party system.

The deployment shape does not change the architectural idea.

The bank should depend on capabilities, never implementation details.

A payment plugin depends on the Ledger contract, not on the native Nagare ledger database. A lending workflow depends on an Identity capability, not on a particular KYC vendor. A treasury product depends on market-data contracts, not on one market-data supplier.

External applications are plugins too. CRM, ERP, LOS, treasury software, existing CBS platforms, card processors and financial infrastructure should attach through the same contract model.

## The core should stay extremely small

Nagare is inspired by plugin-first systems such as DeepSeek Harness: the core coordinates, it does not become the product.

The Nagare kernel should primarily own:
- plugin lifecycle;
- capability registration;
- dependency resolution;
- configuration;
- actor context;
- task-level access hooks;
- policy hooks;
- typed events;
- observability;
- compatibility/version semantics;
- and failure semantics.

Deposits, lending, cards, payments, KYC, bureau access, treasury, risk, finance, compliance, fraud, workflow engines and AI are not kernel responsibilities.

They are capabilities mounted into the bank.

## Financial truth must remain deterministic

Nagare is AI-native, but it must never be AI-dependent for financial correctness.

Money must be boring.

Balances, journals, holds, settlement state, reversals and accounting truth must be deterministic, reconstructable and auditable.

The ledger contract therefore requires strong semantics such as:
- double entry;
- immutable journals;
- idempotency;
- pending and posted states;
- reversals through compensating entries;
- effective time and transaction time;
- holds/reservations;
- and reconciliation.

The native Nagare ledger is only one implementation of this contract.

> **The ledger contract is sacred. The ledger implementation is not.**

## AI is an actor, and actors are pluggable

Nagare is AI-native because machine actors are first-class participants in the institution.

An actor may be:
- a human;
- a deterministic system;
- an external institution;
- or a machine/AI actor.

Every actor has identity, capabilities, permissions, limits, policy, tools, supervision and an audit trail.

An AI Credit Reviewer, AI Treasury Analyst, AI Fraud Investigator or AI Collections Officer is not a privileged system path. Each is a plugin-backed actor implementation that must pass through the same authorization and policy controls as everyone else.

A bank should remain financially correct if every AI plugin is removed.

## Task-level access is a core primitive

Traditional banking software often treats access as “which screen can this role see?”

Nagare should reason at task level:

> **actor + task + resource + context + policy = authorization decision**

Examples include:
- loan.read;
- loan.review;
- loan.approve;
- loan.disburse;
- payment.create;
- payment.authorize;
- payment.release;
- payment.reverse;
- liquidity.read;
- funding.propose;
- funding.execute.

Maker-checker is therefore a policy/workflow pattern, not hard-coded UI logic.

Human users, AI actors and system processes all pass through the same access layer.

## Consumer, Business and Institutional

Nagare has three primary product surfaces.

### Nagare Consumer

The individual's bank: onboarding, accounts, deposits, cards, payments, savings, lending and servicing.

### Nagare Business

The business customer's bank: KYB, current accounts, payments, receivables, payables, payroll, cards, cash management, working capital, credit and business treasury.

Consumer and Business must be independently deployable bank distributions. A licence for one must not require deploying the other.

### Institutional

Institutional is not another customer bank.

It is **the bank's own view of itself**: treasury, ALM, liquidity, capital, finance, risk, compliance, fraud, audit, regulatory reporting, servicing, operations and approvals.

Consumer and Business can be separate business units while Institutional still sees one bank and one financial reality.

## Nagare World

A bank never exists alone.

Nagare World is the synthetic external financial ecosystem around Nagare Bank.

It should grow organically as the bank encounters dependencies: credit bureaus, KYC registries, payment rails, Account Aggregators, tax systems, government registries, card networks, market data, sanctions data, property registries and more.

Nagare World should live as a monorepo of many independently running simulated services, one service per folder/codebase.

Each service:
- owns its own state;
- exposes realistic APIs and events;
- has realistic latency and failure modes;
- respects information boundaries;
- and implements a Nagare contract.

A synthetic bureau must behave like an external bureau, not like an object inside Nagare Bank.

## The living synthetic bank

Synthetic activity should not require AI.

Customers and businesses should behave through deterministic seeded routines, distributions, schedules and state machines.

A customer can receive salary, pay rent, save, spend, borrow, repay and occasionally miss an EMI. A business can invoice, run payroll, pay suppliers, draw working capital and experience seasonality.

The system should support:
- reproducible seeded runs;
- real-time mode;
- accelerated synthetic time;
- scenario injection;
- failure injection;
- and replay.

This allows the same bank state and transaction history to be reproduced exactly for testing and benchmarking.

## Production is another composition

A key Nagare rule is:

> **Production is not a different architecture. It is a different composition of plugins.**

A synthetic bureau plugin can be replaced with a production bureau adapter.

A synthetic UPI rail can be replaced with a production payment-rail integration.

A synthetic KYC implementation can be replaced with a real KYC integration.

The banking domain logic should not be rewritten.

This is what makes Nagare a credible bank-in-waiting rather than merely a simulator.

## Apache/Fineract inspiration without legacy UX

Nagare should study mature open-source banking systems such as Apache Fineract for domain lessons: ledgers, products, loans, deposits, accounting concepts and the accumulated edge cases of real banking.

But inspiration is not inheritance.

Nagare must not copy mature systems' architecture blindly, and it should never inherit legacy enterprise UX simply because the domain model came from banking software.

The design principle is:

> **Learn from mature banking systems at the domain layer. Reimagine the architecture and interaction model for a digital bank.**

## UX is part of the architecture

Nagare's interfaces should be exceptional.

Consumer should feel young, calm and desirable.

Business should be powerful without becoming enterprise clutter.

Institutional software should be as carefully designed as customer software.

A treasurer, credit analyst, fraud investigator, compliance officer or operations user should work through tasks, decisions, queues, exceptions and outcomes, not through an exposed map of backend modules.

All Nagare applications should consume the official design system rather than recreating visual primitives locally.

## Open by default where practical

Nagare should become a useful public technical project for engineers, fintechs, researchers, universities, financial institutions and regulators.

The project should publish stable contracts, core infrastructure, simulation tools and banking capability implementations where practical, while preserving brand/trademark assets and any commercial components that need different treatment.

The goal is not merely to publish source code. It is to create a banking environment others can genuinely build with.

## The test

Every major architecture choice should survive a few questions:

1. Can this capability be replaced without rewriting its consumers?
2. Could it run against Nagare World today and production infrastructure later?
3. Does financial truth remain deterministic?
4. Does every actor go through the same access and policy boundaries?
5. Does the kernel remain small?
6. Can Nagare Consumer or Business be removed without breaking the other?
7. Does Institutional still see one bank?
8. Can the synthetic bank run without AI?
9. Is the internal UX as intentional as the customer UX?
10. Does this reduce, or at least make measurable, the cost of operating the bank?

That is the intent behind Project Nagare.
