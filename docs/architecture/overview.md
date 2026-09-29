# Architecture Overview

Nagare is built as a small coordination kernel surrounded by contracts and replaceable capabilities.

## Layers

### Kernel
The minimum runtime required to assemble and govern a bank.

### Contracts
Stable definitions of capabilities and events.

### Plugins
Replaceable implementations of contracts.

### Distributions
Curated compositions of plugins, policy, configuration and interfaces for a particular bank or environment.

### Surfaces
Consumer, Business, Institutional and Developer experiences.

### World
Independent synthetic third parties and financial infrastructure.

### Simulator
Deterministic population and behaviour engines that keep the synthetic bank alive.

### Production adapters
Implementations that connect Nagare contracts to real financial infrastructure.

The architecture should allow the same banking capability to run against native plugins, external applications or simulated World plugins without leaking implementation details.
