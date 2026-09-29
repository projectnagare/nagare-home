# Events and Observability

Nagare should be observable by construction.

Banking capabilities should expose meaningful domain events rather than forcing downstream systems to inspect implementation details.

Examples include customer.created, account.opened, payment.created, payment.authorized, payment.settled, payment.failed, loan.disbursed, loan.payment_missed and fraud.alert_created.

Observability should preserve actor attribution, task attribution, plugin attribution, correlation IDs, workflow context, policy decisions, access decisions, external-service interactions and financial references.

The goal is to make the institution reconstructable.
