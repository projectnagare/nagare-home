# 0020 — Apache Fineract is a completeness benchmark, not the blueprint

**Status:** Accepted

Apache Fineract should be used as a benchmark for domain completeness when building Nagare's core banking capabilities.

Its role is to help answer:

> What mature banking concepts, workflows, accounting behaviors, product features, edge cases, controls or lifecycle states have we failed to account for?

Nagare should periodically compare its core capability map against Fineract's functional coverage, especially across areas such as:

- customer and account lifecycle;
- deposits and savings;
- lending and loan servicing;
- interest, fees, charges and schedules;
- accounting and general-ledger behavior;
- product configuration;
- transaction lifecycle and reversals;
- delinquency and collections-related states;
- operational and administrative controls;
- reporting and audit-relevant behavior.

This comparison is a **gap-analysis exercise**, not an instruction to reproduce Fineract.

Nagare must not inherit Fineract's architecture, coupling, data model, deployment assumptions, UX patterns or implementation choices merely because they already exist.

The intended relationship is:

> **Fineract tells us what mature banking software has learned it must handle. Nagare decides how those capabilities should exist in a digital-only, plugin-first bank.**

Where Nagare deliberately omits a mature banking capability, that omission should be explicit and justified rather than accidental.

This benchmark should be revisited as Nagare's core evolves and before declaring major core milestones complete.
