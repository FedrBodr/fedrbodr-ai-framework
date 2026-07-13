# Principles

[English](PRINCIPLES.md) | [Русский](ru/PRINCIPLES.md)

These principles refine the [Manifesto](MANIFESTO.md). Each states a meaning, rationale, practical implications, and a common failure mode.

## 1. Engineering Before Generation

- **Meaning:** Understand the problem and relevant constraints before asking AI to produce implementation.
- **Rationale:** Generation speed amplifies both sound decisions and hidden mistakes.
- **Practical implications:** Frame the problem, identify engineering dimensions, and select a proportionate process first.
- **Common failure mode:** A plausible solution solves the wrong problem or transfers cost into operations.

## 2. Specification Before Implementation

- **Meaning:** Meaningful implementation follows a sufficient written specification and required decision owner approval.
- **Rationale:** A specification makes assumptions, boundaries, and acceptance criteria reviewable before code makes them expensive.
- **Practical implications:** Use a short design note for Low Risk work and deeper specifications for higher risk.
- **Common failure mode:** Generated code becomes the first place where requirements and architecture are decided.

## 3. Security Is a Design Input

- **Meaning:** Security participates in discovery, requirements, specification, architecture, implementation, verification, release, and operations.
- **Rationale:** Trust boundaries and data sensitivity shape the system; a final scan cannot repair every unsafe premise.
- **Practical implications:** Record data classification, actors, authentication, authorization, abuse cases, secrets, assumptions, and review triggers early.
- **Common failure mode:** A late checklist discovers that the chosen architecture cannot meet the required security level.

## 4. Expected Load Shapes Architecture

- **Meaning:** Capacity, latency, growth, availability, environment, and cost assumptions inform architecture approval.
- **Rationale:** A design cannot be evaluated without knowing the operating conditions it must support.
- **Practical implications:** Record numbers where known and explicit assumptions or open questions where not; never invent them silently.
- **Common failure mode:** An architecture optimized for imagined scale fails real demand or creates unnecessary cost.

## 5. Evidence Over Claims

- **Meaning:** Generated output and completion statements remain untrusted until supported by current verification evidence.
- **Rationale:** Fluent explanations and successful-looking diffs do not establish correctness.
- **Practical implications:** Define acceptance criteria, run relevant tests, inspect security-sensitive behavior, and retain meaningful failures and warnings.
- **Common failure mode:** A task is declared complete because an agent says it should work.

## 6. Risk-Proportional Process

- **Meaning:** Review depth and formality increase with potential impact, uncertainty, reversibility, and exposure.
- **Rationale:** Uniform heavyweight process wastes effort, while uniform lightweight process hides consequential risk.
- **Practical implications:** Combine stages for Low Risk work; require explicit specifications and deeper expert review as risk rises.
- **Common failure mode:** Teams either bypass all reasoning for speed or apply production-system ceremony to a typo.

## 7. Provider-Neutral Core

- **Meaning:** Durable knowledge, process definitions, and core templates do not depend on one provider's proprietary state or behavior.
- **Rationale:** Providers, prices, interfaces, and availability change.
- **Practical implications:** Keep provider adapters thin and make Git-tracked artifacts understandable by humans and different tools.
- **Common failure mode:** Switching agents requires migrating architecture, decisions, and project context from private chat history.

## 8. Skills Are Portable

- **Meaning:** A skill describes how to perform a class of engineering work without embedding a particular project's facts.
- **Rationale:** Separating method from project knowledge enables reuse, review, and replacement.
- **Practical implications:** Keep project facts in the Knowledge layer; require provenance and license clarity for third-party skills.
- **Common failure mode:** A reusable skill silently encodes one repository's architecture or overrides its governance.

## 9. Knowledge Must Return to the System

- **Meaning:** Validated discoveries, decisions, changed assumptions, and operational lessons update durable project artifacts.
- **Rationale:** Session context disappears and unrecorded learning is repeatedly rediscovered.
- **Practical implications:** Make knowledge update an exit criterion and treat derived summaries or indexes as reconstructable.
- **Common failure mode:** The code changes while specifications, decisions, and operating context remain stale.

## 10. Context Efficiency Without Evidence Loss

- **Meaning:** Reduce repetitive, low-signal context while preserving access to original evidence.
- **Rationale:** Human attention, model context windows, and tokens are finite and may have direct cost.
- **Practical implications:** Scope tasks, prefer focused files, compact noisy output, and retain raw failures, logs, and reports when relevant.
- **Common failure mode:** Compression removes the warning or stack trace needed to diagnose an incorrect result.
