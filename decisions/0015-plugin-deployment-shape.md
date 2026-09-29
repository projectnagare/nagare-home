# 0015 — Plugins are deployment-shape agnostic

**Status:** Accepted

A Nagare plugin is defined by the contract/capability relationship, not by whether it runs in-process.

A plugin may run in-process, as a sidecar, as an independent service, as a remote API, or as an adapter to an existing system.

This allows internal capabilities, third-party infrastructure and external bank applications to participate in the same architecture without forcing one deployment model.
