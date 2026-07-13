# Glossary

**AI provider** — A hosted service or local runtime supplying model inference and related capabilities. It is replaceable and is not an authoritative project store.

**AI agent** — A bounded software actor that combines a model, supplied context, and tools to pursue a task. Its output remains untrusted until the workflow's validation passes.

**AI-first engineering** — Engineering designed for effective human–AI collaboration while retaining explicit specification, governance, quality controls, and accountability.

**Durable knowledge** — Validated project information maintained across sessions, contributors, tools, and providers in an authoritative Git-tracked artifact.

**Ephemeral context** — Temporary conversations, intermediate reasoning, tool output, or session state that is not an authoritative project record.

**Source of truth** — The designated authority for resolving conflicting information. In this framework, portable engineering knowledge is represented by Git-tracked artifacts.

**Provider-neutral core** — Durable knowledge, process definitions, and core templates that do not require one provider's proprietary format, state, or behavior.

**Provider adapter** — A thin, tool-specific entry point that locates provider-neutral instructions and maps supported integration behavior without duplicating project knowledge.

**Workflow** — A sequence of engineering activities with defined inputs, outputs, responsibilities, gates, and evidence.

**Orchestration** — Coordination of workflow steps, skills, agents, tools, and handoffs. It may be manual or automated and remains separate from durable knowledge.

**Skill** — A reusable method for performing a class of engineering work. It does not contain project-specific facts.

**Engineering dimension** — A cross-cutting concern, such as security or reliability, used to examine requirements, design, implementation, and evidence.

**Verification evidence** — Current, inspectable results supporting or refuting a claim, such as test output, review findings, measurements, logs, or acceptance checks.

**Context Efficiency** — The engineering practice of preserving high-signal context and access to raw evidence while reducing repetitive or low-signal material.

**Project memory** — The maintained subset of durable knowledge needed to understand, operate, and continue a project; it is not a transcript of every interaction.

**Engineering Knowledge Lifecycle** — Creation, validation, approval, use, update, deprecation, archival, retrieval, and reconstruction of derived knowledge representations.

**ADR (Architecture Decision Record)** — A versioned record of the context, decision, consequences, and status of an architecturally significant choice.

**Reference implementation** — A real adoption used to demonstrate and evaluate practices. It provides evidence and examples but does not automatically define the framework.
