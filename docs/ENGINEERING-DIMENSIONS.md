# Engineering Dimensions

Engineering dimensions are cross-cutting lenses applied during discovery, specification, architecture, implementation, and verification. Not every task needs equal depth. The [risk classification](GOVERNANCE.md#risk-classification) determines how much analysis and evidence is proportionate.

## Dimension guide

| Dimension | Key questions | When deeper review is needed | What belongs in the specification | Example verification evidence |
| --- | --- | --- | --- | --- |
| Security | What data, actors, threats, trust boundaries, access controls, and abuse cases exist? | Sensitive data, exposed interfaces, identity, privilege, secrets, or high impact | Security level, controls, assumptions, threat model, review triggers | Security tests, access-control cases, scan findings, review record |
| Privacy | Is personal data necessary, lawful, minimized, retained, and deletable? | Personal, behavioral, financial, health, location, or regulated data | Data purpose, classification, retention, consent, subject rights | Data-flow review, deletion test, privacy assessment |
| Performance | What latency, throughput, concurrency, and resource use are required? | User-facing latency, high volume, constrained resources, or expensive operations | Normal and peak targets, measurement method, assumptions | Benchmarks, profiles, representative load results |
| Reliability | What failures are expected and how does the system recover? | Critical paths, distributed state, external dependencies, or tight availability goals | Failure modes, availability, recovery objectives, degradation and rollback | Failure injection, recovery test, SLO evidence |
| Scalability | How will load and data growth change bottlenecks and topology? | Large growth range, hot partitions, fan-out, or costly horizontal scaling | Growth assumptions, capacity limits, scaling approach | Capacity tests, scaling observations, limit analysis |
| Observability | Can operators detect, explain, and act on important behavior? | Production services, asynchronous work, regulated audit, or complex failures | Signals, ownership, alerts, correlation, safe logging | Dashboard and alert tests, trace/log inspection, runbook exercise |
| Maintainability | Can contributors understand, change, and retire the design safely? | Long-lived systems, complex dependencies, high turnover, or shared platforms | Boundaries, dependency rules, migration and deprecation strategy | Review findings, dependency checks, change-impact test |
| Testability | Can requirements and failure modes be verified deterministically? | Hard-to-isolate dependencies, nondeterminism, stateful workflows, or safety impact | Test seams, fixtures, environments, acceptance mapping | Unit/integration/system tests and traceability |
| Operability | Can the system be deployed, configured, supported, and restored? | On-call ownership, migrations, manual operations, or multiple environments | Deployment, rollback, runbooks, ownership, recovery | Deployment rehearsal, rollback test, operational checklist |
| Cost | What build, run, storage, network, vendor, and AI costs are accepted? | Usage-based services, uncertain scale, material commitments, or poor reversibility | Cost model, budgets, assumptions, measurement and guardrails | Cost estimate, usage report, budget alert test |
| Compliance | Which legal, contractual, audit, or policy obligations apply? | Regulated domains, customer commitments, cross-border data, or audit scope | Applicable obligations, controls, evidence ownership | Control review, audit artifact, policy conformance check |
| Accessibility | Can relevant users perceive, navigate, and operate the product? | User interfaces, public services, procurement requirements, or assistive technology users | Applicable standards, interaction and content requirements | Automated checks plus keyboard and assistive-technology review |
| Context Efficiency | Is working context focused without losing authoritative evidence? | Large repositories, verbose tools, long agent sessions, or token-based costs | Context sources, output policy, raw fallback, known compression risks | Context audit, raw-output retrieval, before/after task evidence |

## Security

Security is a design input and lifecycle-wide responsibility, not a final scan.

Where relevant, a specification answers:

- What data is processed, and is it personal, financial, regulated, confidential, or otherwise sensitive?
- Who are legitimate users, threat actors, administrators, services, and external parties?
- What trust boundaries and data flows exist?
- What authentication and authorization models are required?
- What abuse cases, privilege paths, injection surfaces, and denial-of-service risks exist?
- Which secrets are required, and how are they stored, scoped, rotated, and revoked?
- What dependency and supply-chain risks are introduced?
- How will logs remain useful without leaking secrets or sensitive data?
- What security assumptions and residual risks require human acceptance?
- Does the impact of compromise require a dedicated human security review?

Security requirements affect architecture, complexity, infrastructure, schedule, and cost. High-impact identity, authorization, cryptography, sensitive-data, or internet-exposed changes normally require deeper human review and explicit negative tests.

## Expected Load and Performance

Architecture approval records values or explicit unknowns for:

- expected users and usage patterns;
- normal and peak traffic;
- requests per second and concurrent operations;
- data volume and expected growth;
- latency and throughput expectations;
- availability and recovery expectations;
- deployment environment and infrastructure constraints;
- resource and operational cost constraints.

When exact numbers are unavailable, the owner reviews explicit assumptions and the design identifies how they will be validated. AI must not invent load characteristics. Architecture without reviewed load assumptions is an unreviewed guess. Deeper review is needed when traffic is bursty, capacity is expensive, state is difficult to partition, latency is contractual, or failure has wide impact. Evidence may include representative load tests, profiling, capacity calculations, production observations, and cost estimates—with limitations stated.

## Context Efficiency

Context Efficiency preserves attention and evidence while reducing low-signal material. High-signal output includes failures, changed behavior, security findings, meaningful warnings, acceptance results, and diagnostic traces. Low-signal output often includes repeated success lines, unchanged boilerplate, redundant file listings, or verbose progress output.

The objective is not minimum tokens at any cost. It is to:

- keep source selection and tasks focused;
- make output easier for humans and agents to inspect;
- reduce unnecessary context-window pressure and token-based cost;
- compact repetitive output while keeping its meaning and limitations visible;
- preserve a direct path to original files, reports, logs, and full command output.

> Compress noise, not evidence.

Do not compress when exact formatting matters, output is unfamiliar, a failure is being diagnosed, security or data-loss risk is present, warnings may be material, or the optimizer cannot provide trustworthy raw fallback. A summary is not complete evidence merely because it is shorter. Context compression complements good context architecture, scoped tasks, focused files, and durable documentation; it does not replace them.
