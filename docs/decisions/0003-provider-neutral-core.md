# ADR 0003: Provider-Neutral Core

## Status

Accepted

## Context

AI tools differ in startup files, tool APIs, context behavior, model capabilities, and proprietary memory. Embedding project architecture, requirements, or process definitions in one provider's configuration creates migration cost and conflicting sources of truth.

## Decision

Durable knowledge, process definitions, skills contracts, and core project templates must remain understandable and usable without depending on a specific AI provider.

Provider- or agent-specific files are thin adapters only. They may locate the provider-neutral entry point, explain supported integration mechanisms, and map unavoidable tool behavior. They must not duplicate business context, requirements, specifications, architecture, decisions, or roadmap content.

Optional third-party integrations do not become architectural foundations merely by being documented. Adoption, official compatibility, and maturity must be stated accurately.

## Consequences

Benefits:

- Projects can change providers without migrating authoritative engineering knowledge.
- Humans and multiple tools can review the same project contracts.
- Provider-specific changes stay isolated and replaceable.
- Conflicting copies of architecture and requirements are less likely.

Costs and limitations:

- Some provider capabilities require localized adapter notes.
- A neutral contract may not expose every vendor-specific optimization.
- Portability must be tested in real projects rather than assumed.
- Thin adapters still require maintenance as tools evolve.
