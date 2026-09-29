# Nagare Architecture Report

This document translates the Nagare Constitution into a system model. It is an architecture direction, not a frozen implementation specification.

## 1. System model

Nagare is best understood as four layers:

1. **Kernel and contracts** — the minimal runtime and canonical interfaces.
2. **Bank capabilities** — ledger, identity, payments, lending, deposits, workflow, policy, risk, treasury and other replaceable plugins.
3. **Bank distributions and surfaces** — Consumer, Business, Institutional and Developer experiences composed from capabilities.
4. **External world** — real or simulated third parties connected through the same plugin contracts.

A bank is therefore:

> **contracts + plugins + configuration + state + policy**

not one monolithic application.

## 2. Kernel responsibilities

The kernel should remain intentionally small.

It may own:
- plugin registration and lifecycle;
- capability discovery;
- dependency resolution;
- actor context propagation;
- task authorization hooks;
- policy evaluation hooks;
- configuration and environment profiles;
- typed events;
- observability and tracing;
- plugin health/status;
- compatibility and version negotiation;
- failure boundaries.

It should not own banking products.

## 3. Contracts

Contracts define stable banking vocabulary.

Likely early contract families include:
- Ledger;
- Account;
- Identity;
- KYC/KYB;
- CreditBureau;
- PaymentRail;
- CardNetwork;
- Workflow;
- Policy;
- Access;
- Notification;
- Risk;
- MarketData;
- Treasury;
- Document;
- Audit;
- ActorProvider.

Contracts should be versioned and implementation-agnostic.

## 4. Plugin model

A Nagare plugin declares:
- identity and version;
- contracts implemented;
- capabilities;
- dependencies;
- events consumed/emitted;
- permissions requested;
- runtime/deployment shape;
- health interface;
- configuration schema.

A plugin may be local or remote. “Plugin” describes the architectural relationship, not the process boundary.

The hard dependency rule is:

> A plugin may depend on a contract. It must not depend on another plugin's implementation.

## 5. Actors, access, policy and workflow

These are separate concerns.

**Identity** answers: who/what is acting?

**Access** answers: may this actor attempt this task on this resource in this context?

**Policy** answers: under what institutional rules may the action occur?

**Workflow** answers: what sequence of work, approvals and state transitions must happen?

**Audit** answers: who did what, under which authority, and what changed?

This separation prevents maker-checker, role logic and AI-specific exceptions from being hard-coded into domain services.

## 6. AI

AI enters Nagare through ActorProvider and capability plugins.

An AI actor must declare what tasks it can perform and receives only the tools/data permitted by its actor identity and policy.

Examples:
- credit review;
- fraud investigation;
- AML investigation;
- treasury analysis;
- operational risk review;
- collections;
- customer support.

AI does not receive privileged database access and does not bypass normal controls.

## 7. Ledger

The ledger provides deterministic financial truth.

Required semantics should include:
- double entry;
- immutable journal;
- idempotency;
- holds/reservations;
- pending and posted states;
- reversals;
- effective and transaction time;
- reconciliation support;
- account/subledger separation;
- multi-currency-ready semantics.

The native Nagare ledger is an implementation of the Ledger contract. Existing cores may be connected through adapters.

## 8. External applications

Nagare must be able to coexist with existing bank technology.

Examples of external plugins:
- Finacle/Temenos/Fineract adapters;
- external LOS;
- Salesforce/CRM;
- SAP/ERP;
- treasury applications;
- card processors;
- document systems.

This makes Nagare usable as a greenfield bank stack or as an overlay/modernization substrate.

## 9. Bank distributions

### Consumer

A composition oriented around personal banking capabilities.

### Business

A composition oriented around business accounts, payments, payroll, working capital and business financial operations.

Consumer and Business are independently deployable.

### Institutional

Institutional is the internal operating surface of the bank. It composes shared capabilities to give bank employees and machine actors a whole-institution view.

It includes treasury, ALM, liquidity, capital, finance, risk, compliance, fraud, regulatory reporting, audit, servicing and operations.

## 10. Nagare World

Nagare World is a monorepo of independent synthetic external services.

A likely structure is:

```text
nagare-world/
  services/
    credit-bureau/
    ckyc/
    pan/
    digilocker/
    gstn/
    account-aggregator/
    upi/
    imps/
    neft/
    rtgs/
    card-network/
    sanctions/
    market-data/
    property-registry/
  packages/
    world-sdk/
  scenarios/
```

Services should be added when the bank needs them, not prebuilt speculatively.

The world SDK can provide seeded randomness, synthetic time, identity resolution, latency simulation, failure injection, event publication and common fixture utilities.

## 11. Simulation

The simulator creates persistent economic activity.

It should support synthetic:
- people;
- businesses;
- employers;
- merchants;
- payments;
- savings;
- loans;
- repayments;
- defaults;
- fraud;
- disputes;
- reconciliation breaks;
- liquidity events;
- regulatory events.

The simulator should be deterministic under a given seed.

Time should be controllable so one environment can run in real time while another can simulate years of banking activity quickly.

## 12. Hosted Nagare

Nagare Cloud/Sandbox should allow a user to provision a complete synthetic institution.

The developer experience should include:
- isolated sandbox bank;
- synthetic customer/business identities;
- customer and employee login credentials;
- API keys;
- webhooks/events;
- seed/reset/replay;
- accelerated time;
- scenario/failure injection;
- ledger inspection;
- Consumer, Business and Institutional UIs;
- developer console and API documentation.

The sandbox should exercise the same contracts used by production distributions.

## 13. Production transition

A production bank should be assembled by changing configuration and implementations, not by changing the conceptual architecture.

For example:

```text
CreditBureauProvider
  sandbox  -> nagare-world-credit-bureau
  prod     -> production-bureau-adapter

PaymentRail
  sandbox  -> nagare-world-upi
  prod     -> production-upi-adapter
```

Certification, operational controls, security hardening and regulatory requirements will differ materially in production, but domain consumers should still depend on the same contracts.

## 14. User experience

The backend architecture must not dictate the UI information architecture.

Institutional products should organize around work:
- needs attention;
- queues;
- exceptions;
- approvals;
- investigations;
- decisions;
- outcomes.

The design system is the visual source of truth. Nagare UI should remain modern, young and highly polished even where the underlying domain was informed by mature systems such as Apache Fineract.

## 15. Architecture evolution

Major cross-project architecture decisions belong in `decisions/`.

Proposals that would change the Constitution, contracts or multi-repo architecture should go through the RFC process.

The central rule is simple:

> Keep the kernel small, keep contracts stable, keep implementations replaceable, and keep money deterministic.
