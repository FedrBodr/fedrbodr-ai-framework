# Manifesto

[English](MANIFESTO.md) | [Русский](ru/MANIFESTO.md)

FedrBodr AI Framework starts from a change in economics: AI can produce implementation quickly, but it does not make engineering consequences cheap.

## Durable foundations

> AI providers are temporary.
>
> Knowledge is permanent.
>
> Git is the source of truth.
>
> Architecture outlives every model.

Models, vendors, interfaces, and costs change. Requirements, constraints, accepted decisions, and operational lessons must remain accessible when they do. Git-tracked artifacts provide a portable, reviewable history; derived memory systems may help retrieval but do not replace that authority.

## Engineering commitments

**AI makes implementation cheap; engineering remains essential.** Code generation addresses one stage. Requirements, design, security, testing, operations, and maintenance retain their cost and importance.

**No implementation before sufficient specification.** The specification may be brief for low-risk work, but intent, constraints, assumptions, acceptance criteria, and approval must be explicit enough to prevent hidden design by generation.

**Review before generation.** Engineering review challenges design, security, load, operability, and acceptance while change is inexpensive. Required decision owner approval follows.

**Security begins with design.** Data classification, trust boundaries, abuse cases, authentication, authorization, secrets, and impact influence requirements and architecture before implementation.

**Expected load shapes architecture.** Capacity, latency, availability, growth, environment, and cost assumptions are stated or marked unknown before architecture approval. They are never silently invented.

**Generated output requires evidence.** Plausibility is not verification. Tests, review, inspection, and acceptance evidence establish whether an output is fit for use.

**Human owners remain accountable.** AI may research, propose, draft, implement, and review. People retain responsibility for business intent, risk acceptance, material design choices, cost commitments, and consequential releases.

**Tests, documentation, and decisions are first-class artifacts.** They are part of the product's maintainability and operational behavior, not optional residue after code generation.

**Reliable AI collaboration requires process, not model loyalty.** AI must adapt to project governance and durable knowledge. The project must not depend on proprietary model memory.

**Preserve signal and reduce context waste.** Relevant evidence should be easy to inspect without flooding human or model attention with repetition and boilerplate.

> Compress noise, not evidence.

Output optimization must never hide failures, security findings, meaningful warnings, behavioral changes, unresolved errors, or acceptance evidence. Raw evidence remains retrievable whenever compression can remove relevant detail.
