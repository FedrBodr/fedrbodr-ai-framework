# Roadmap

This roadmap expresses direction without delivery dates. Movement between committed scope, exploration, and long-term ideas requires evidence and review.

## Phase 0 — Foundation

- Manifesto, terminology, architecture, governance, and initial ADRs.
- Engineering lifecycle and cross-cutting dimensions.
- Provider-neutral project template with specification and review gates.
- Honest notes for optional, independently owned integration targets.

## Phase 1 — Project Standard

- Validate and stabilize the `docs/ai` convention in real repositories.
- Define the Engineering Knowledge Lifecycle: creation, validation, approval, use, update, deprecation, archival, retrieval, and reconstruction of derived indexes.
- Refine provider-neutral agent instructions and risk classification.
- Publish adoption and migration guidance.

Git-tracked durable knowledge remains authoritative throughout this lifecycle. RAG systems, vector stores, summaries, caches, and indexes may be derived and reconstructable layers; they do not become the sole source of truth.

## Phase 2 — Reference Workflows

- Discovery and requirements.
- Specification, engineering review, and human approval.
- Planning and TDD implementation.
- Specification compliance, code quality, and security review.
- Verification, release, documentation update, and model handoff.

Reference workflows become recommendations only after evidence from real use.

## Phase 3 — Tooling Experiments

- Documentation-structure and link validation.
- Optional CLI experiments where manual work demonstrates repeated friction.
- Thin provider-adapter and MCP compatibility experiments.
- Retrieval and RAG experiments with rebuildable derived state.
- Evaluation of optional workflow, skill, and context-efficiency integrations.

Experiments are not committed product features and may be discarded. No CLI, MCP server, adapter runtime, retrieval implementation, or skills package manager exists in version 0.1.

## Phase 4 — Reference Implementations

- Evaluate adoption by the separate FedrBodr OS project.
- Adopt the methodology in real software projects.
- Publish provider migration and risk-proportional workflow examples.
- Incorporate measured lessons and stabilize proven conventions.

Reference implementations provide evidence; they do not silently redefine the specification.
