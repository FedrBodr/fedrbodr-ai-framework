# Instructions for AI Agents

These rules govern AI agents changing FedrBodr AI Framework itself.

## Sources of truth

- Git-tracked Markdown is authoritative for the specification, decisions, terminology, templates, and roadmap.
- Treat chat history and model memory as ephemeral. Verify material claims against repository content and original external sources.
- Keep durable knowledge, process definitions, and core templates provider-neutral.

## Engineering gates

- Classify work as Low, Medium, or High Risk using `docs/GOVERNANCE.md`.
- Do not begin meaningful implementation before a sufficient written specification and required human approval exist. A compact design note is sufficient for a low-risk documentation change.
- Review applicable engineering dimensions before approving a design. Security and expected load are design inputs, not late checklists.
- Treat generated output as untrusted until acceptance criteria and relevant checks provide fresh evidence.
- Preserve raw failures, security findings, meaningful warnings, and other evidence when optimizing context.

## Change rules

- Do not silently turn a proposal, experiment, or roadmap item into an accepted standard.
- Record architecturally significant decisions as ADRs under `docs/decisions/`.
- Keep changes small, reviewable, and connected to a roadmap item or documented use case.
- Add framework-level terms to `docs/GLOSSARY.md`; keep relative links working.
- Do not add empty abstractions, speculative tooling, or duplicated concepts.
- Do not imply that planned tooling or optional integrations are implemented, tested, official, or mandatory.

## Boundaries and safety

- Never add secrets, credentials, sensitive personal data, biographies, resumes, or personal records.
- Keep FedrBodr AI Framework separate from FedrBodr OS, which may be mentioned only as a separate future reference implementation.
- Provider-specific adapters must remain thin and must not duplicate project knowledge.
- Third-party projects require accurate attribution, provenance, version or revision where relevant, and license review before vendoring. Do not copy third-party content by default.
- Before completion, inspect the diff, validate links and diagrams, verify terminology and scope claims, and report evidence honestly.
