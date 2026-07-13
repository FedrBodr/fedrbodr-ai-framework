# Project Adoption Template

This template gives a product repository a provider-neutral entry point, durable engineering context, and proportionate specification and review gates. It does not install a runtime or require a particular AI tool.

## Adopt the template

1. Copy `AGENTS.md` and `docs/ai` into the target repository.
2. Complete `docs/ai/CONTEXT.md` with verified product facts, constraints, active work, and known risks.
3. Complete `docs/ai/ARCHITECTURE.md`, including security boundaries and reviewed load assumptions.
4. Tailor `docs/ai/AI.md` to the project's authority, risk, test, review, and evidence rules.
5. Link existing ADRs, roadmap sources, issue trackers, and operating documentation rather than duplicating them.
6. Use `docs/ai/specs`, `plans`, and `reviews` for work that needs durable artifacts.
7. Review the result with accountable project owners and commit it to Git.

## Apply proportionately

Low Risk work may use one short specification that combines design, review, and approval. Medium Risk work normally uses explicit specification, plan, and review records. High Risk work requires deeper specialist and human review. Remove sections only when the project has another authoritative location; otherwise mark non-applicable sections with a brief reason.

Prefer concise, maintained facts over comprehensive but stale prose. Do not store secrets, credentials, customer records, or sensitive personal data. Link to an access-controlled system when information cannot safely live in Git.
