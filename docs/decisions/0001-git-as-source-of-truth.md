# ADR 0001: Git as the Source of Truth

## Status

Accepted

## Context

The framework needs a portable, reviewable home for engineering knowledge that does not depend on an AI provider's chat history, proprietary memory, or availability. The initial repository is documentation-first and must remain usable with common engineering tools.

## Decision

Git-tracked Markdown is the primary portable source of truth for framework specifications, architecture, decisions, terminology, plans, and provider-neutral project guidance. Product repositories adopting the framework should keep their authoritative AI-facing engineering knowledge alongside their code where practical.

Provider sessions, generated summaries, caches, and retrieval indexes may assist workflows but are not authoritative. Material validated outcomes must be written back to Git-tracked artifacts.

## Consequences

Benefits:

- Versioning makes change and rollback visible.
- Portable text works across providers and tools.
- Pull requests make knowledge reviewable.
- Provider independence reduces process lock-in.
- History preserves how authoritative knowledge evolved.

Limitations:

- Git is not a complete semantic memory system.
- Large binary data requires other storage solutions and durable references.
- Retrieval indexes may exist, but must be derived and rebuildable from authoritative sources.
- Secrets must never be stored in project documentation or Git history.
