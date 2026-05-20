# SDK Kit

SDK Kit is the canonical home for reusable agent SDK concepts previously mixed into `Agent-UI-Kit`.

## Migrated scope

The following belong in Agent-Kit, not Agent-UI-Kit:

- Python SDK package direction
- agent development primitives
- tool abstraction
- workflow abstraction
- identity provisioning client
- CLI patterns
- framework adapters

## Current source being migrated

The legacy implementation currently lives in:

```text
AGenNext/Agent-UI-Kit
  pyproject.toml
  src/autonomyx/
```

Its package metadata identifies the package as:

```text
autonomyx-adk
```

## Target direction

```text
Agent-Kit/sdk-kit/
  models/
  cli/
  adapters/
  workflows/
  identity/
  docs/
```

This kit should become the stable, reusable SDK layer used by platform repos.

## Migration rule

Move in small slices. Do not delete `Agent-UI-Kit` until equivalent SDK functionality is present and CI is passing in `Agent-Kit`.
