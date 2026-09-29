# Plugin Model

Everything meaningful in Nagare should be replaceable behind a stable contract.

A plugin may be an in-process package, sidecar, independently deployed service, remote API or adapter to a third-party system. The transport does not define the plugin.

A Nagare plugin should declare identity and version, contracts implemented, capabilities, dependencies, events emitted and consumed, required permissions, configuration schema, health information and compatibility range.

## Dependency rule

A plugin may depend on contracts and capabilities. It must not import another plugin's implementation.

The same model applies to native banking capabilities, external applications, external financial infrastructure, simulated services and AI actors.
