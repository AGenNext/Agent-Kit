# Agent-Kit Migration Policy

Agent-Kit is the canonical home for reusable AGenNext-owned kits.

## Migration rule

Move only AGenNext-owned kit logic, contracts, interfaces, generators, thin wrappers, tests, and documentation into Agent-Kit.

Do not move forked, cloned, vendored, or copied upstream framework code.

## Allowed

```text
- AGenNext-owned SDK interfaces
- AGenNext-owned workflow abstractions
- AGenNext-owned adapter contracts
- thin integration wrappers
- SurrealKit model definitions
- generators and templates owned by AGenNext
- tests that depend on external packages
- documentation describing integration patterns
```

## Not allowed

```text
- copied LangChain source
- copied LangGraph source
- copied CrewAI source
- copied AutoGen source
- copied MCP server implementations
- vendored third-party packages
- forked upstream code without explicit fork-governance approval
- cloned examples treated as platform source
```

## Dependency rule

Upstream frameworks remain external dependencies.

Agent-Kit may define integration contracts for those frameworks, but it must not become a vendor directory.

## Migration from Agent-UI-Kit

The legacy `Agent-UI-Kit` repository contains mixed-scope foundation code. Migration must be done file-by-file.

Before moving any file, confirm:

```text
1. It is AGenNext-owned.
2. It is reusable platform kit logic.
3. It is not UI-only.
4. It is not copied upstream code.
5. It has a clear target kit folder.
```

## Target folders

```text
surrealkit/
sdk-kit/
workflow-kit/
adapter-kit/
```

## Deletion rule

Do not delete `Agent-UI-Kit` until migrated functionality has equivalent coverage and CI in `Agent-Kit`.
