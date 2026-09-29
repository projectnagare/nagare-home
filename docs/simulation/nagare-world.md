# Nagare World

A bank never exists alone.

Nagare World is the simulated financial ecosystem surrounding Nagare Bank.

It should live as one monorepo containing independently stateful services such as credit bureau, KYC/KYB, CKYC, PAN, DigiLocker, GSTN, Account Aggregator, UPI, IMPS, NEFT, RTGS, card network, sanctions, fraud intelligence, market data, property registry and vehicle registry.

Each simulated service should behave like an external institution: it owns its state, exposes only its information, can be unavailable, can be slow, can return stale or partial data, and can disagree with another system.

Nagare World should grow only when the bank needs a new dependency.

Every World service should implement the same Nagare contract that a future production integration would implement.
