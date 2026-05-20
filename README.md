# Agent-Kit

Agent-Kit contains reusable implementation kits for the AGenNext platform.

Kits are shared developer/runtime utilities used across Agent-* repositories. They do not own domain artifacts directly; they provide standardized ways to define, generate, validate, migrate, test, and operate platform components.

## Included kits

```text
surrealkit/
  SurrealDB model, migration, seed, and validation kit
```

## SurrealKit

SurrealKit is the source-of-truth layer for SurrealDB object modeling in AGenNext.

Instead of hand-writing large SurrealQL files in every repository, repositories should define native object models using SurrealKit model definitions. SurrealKit then generates SurrealQL, runs migrations, loads seed data, and executes database-level validation.

## Platform relationship

```text
Agent-Grammar
  owns grammar and validation concepts

Agent-Seed
  owns canonical seed data

Artifact repositories
  own artifact/object models

Agent-Graph
  owns graph ingestion and mapping

Agent-Kit / SurrealKit
  generates and runs SurrealDB schemas, migrations, seeds, and tests
```

## Rule

SurrealQL may exist as generated output, but the long-term source of truth should be SurrealKit model definitions.
