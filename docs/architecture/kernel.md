# The Nagare Kernel

The Nagare kernel should remain intentionally small.

Its job is to make a composable bank possible, not to implement banking products.

Likely responsibilities include plugin discovery and lifecycle, capability registration, dependency resolution, configuration, actor context, access-control integration, event routing, observability hooks, plugin health, version compatibility, failure semantics and distribution loading.

The kernel should not directly implement deposits, loans, payments, KYC, bureau integration, fraud, treasury, risk or AI.

A recurring architecture review question should be:

> Does this genuinely belong in the kernel, or is it another capability that should be a plugin?
