# SurrealKit

SurrealKit standardizes SurrealDB modeling, migration, seed loading, and validation for the AGenNext platform.

## Responsibilities

```text
- object model definitions
- SurrealQL generation
- migration execution
- seed loading
- database-level validation
- schema drift checks
- pinned SurrealDB CI execution
```

## Philosophy

Repositories should define high-level object models.

SurrealKit should generate:

```text
DEFINE TABLE
DEFINE FIELD
DEFINE INDEX
DEFINE FUNCTION
```

instead of requiring every repository to hand-maintain large SurrealQL files.

## Example

Model definition:

```yaml
object: skill_source_v1
kind: native_artifact
owner: Agent-Skills
context: grammar_context:agent_graph_content
semantic_class: CreativeWork
fields:
  skill_id:
    type: string
    required: true
  version:
    type: semver
```

Generated output:

```surql
DEFINE TABLE skill_source_v1 SCHEMAFULL;
DEFINE FIELD skill_id ON TABLE skill_source_v1 TYPE string;
```

## Long-term direction

```text
SurrealKit models
  → generate SurrealQL
  → generate migrations
  → generate validation tests
  → generate CI database checks
```
