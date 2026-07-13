# Engineering Lifecycle

[English](ENGINEERING-LIFECYCLE.md) | [Русский](ru/ENGINEERING-LIFECYCLE.md)

Compact cycle: **Think → Specify → Review → Plan → Generate → Verify → Capture Knowledge → Improve**.

Full sequence: **Business Problem → Discovery → Requirements → Specification → Architecture → Engineering Review → Decision Owner Approval → Implementation Plan → TDD Implementation → Specification Compliance Review → Code Quality and Security Review → Verification → Release → Documentation Update → Knowledge Capture → Improvement**.

The operational stages below combine related steps without removing their intent. Work may iterate.

## 1. Problem Framing

- **Purpose / inputs / outputs:** Turn observations, requests, incidents, and strategy into an owned problem statement, desired outcome, initial scope, and risk signals.
- **AI / human / exit:** AI exposes ambiguity without inventing intent. The human owns priority and constraints. Exit when the problem, owner, outcome, and important unknowns are explicit.

## 2. Discovery

- **Purpose / inputs / outputs:** Use repositories, research, stakeholder knowledge, and operational evidence to produce sourced findings, assumptions, risks, and open questions.
- **AI / human / exit:** AI separates evidence from inference. Humans provide domain context and validate findings. Exit when evidence supports requirements or a decision to stop.

## 3. Requirements

- **Purpose / inputs / outputs:** Convert validated findings and policies into scoped, traceable functional and non-functional requirements with acceptance measures.
- **AI / human / exit:** AI drafts and checks contradictions; humans approve business meaning, data sensitivity, compliance, and priority. Exit when requirements are testable, owned, and explicit about unknowns.

## 4. Specification

- **Purpose / inputs / outputs:** Turn approved requirements, architecture, constraints, and decisions into a design covering boundaries, security, load, reliability, cost, acceptance, tests, rollout, and open questions.
- **AI / human / exit:** AI presents options and explicit assumptions; humans supply consequential facts and judge fit. Exit when the specification is ready for risk-proportional review.

## 5. Engineering Review

- **Purpose / inputs / outputs:** Challenge feasibility, security, operability, maintainability, and completeness; produce findings, required changes, and residual risks.
- **AI / human / exit:** AI performs structured preliminary review; humans apply domain expertise and request specialists. Exit when blockers are resolved or owned and residual risk is clear.

## 6. Decision Owner Approval

- **Purpose / inputs / outputs:** Turn a reviewed specification, trade-offs, estimates, and residual risks into an explicit approval, rejection, or revision request tied to a specific revision.
- **AI / human / exit:** AI summarizes the decision and never infers approval. The decision owner accepts intent, material architecture, security level, cost, and risk. Exit on recorded authorization by required owners.

## 7. Implementation Planning

- **Purpose / inputs / outputs:** Convert the approved specification into ordered tasks linked to requirements, files, tests, dependencies, verification, and completion evidence.
- **AI / human / exit:** AI proposes small reviewable steps; humans confirm sequence, ownership, and operational constraints. Exit when each task can produce an independently verifiable result.

## 8. TDD Implementation

- **Purpose / inputs / outputs:** Use the approved plan and red–green–refactor loops to produce tests, minimal implementation, refactoring, and task evidence.
- **AI / human / exit:** AI preserves scope and never weakens tests; humans resolve ambiguity and material design changes. Exit when planned behavior passes relevant tests and deviations return to specification review.

For documentation, exploration, or other non-behavioral work, use the closest evidence-producing feedback loop instead of meaningless tests.

## 9. Review

- **Purpose / inputs / outputs:** Assess specification compliance first, then code quality, security, and maintainability; produce impact-ranked findings and residual concerns.
- **AI / human / exit:** AI cites concrete evidence; humans adjudicate material findings and unsupported completion claims. Exit when blockers are resolved and remaining risks have owners.

## 10. Verification

- **Purpose / inputs / outputs:** Check acceptance criteria and required quality properties in the intended environment; produce test, security, operational, and failure evidence.
- **AI / human / exit:** AI runs fresh checks and preserves relevant raw output; humans judge evidence sufficiency. Exit when evidence clearly permits or blocks release and unresolved risks are listed.

## 11. Release

- **Purpose / inputs / outputs:** Deliver verified change using approved artifacts, rollout, rollback, observability, and operational ownership; record release state and health.
- **AI / human / exit:** AI performs only authorized steps; humans authorize High Risk production releases and own incidents. Exit when state and health are known and rollback remains available as specified.

## 12. Knowledge Capture

- **Purpose / inputs / outputs:** Turn specifications, decisions, reviews, verification, release observations, and incidents into updated context, architecture, ADRs, runbooks, and plans.
- **AI / human / exit:** AI proposes focused updates and removes stale claims; humans approve consequential knowledge and protect sensitive data. Exit when maintained artifacts match verified reality.

## 13. Improvement

- **Purpose / inputs / outputs:** Use outcomes, defects, cycle time, cost, incidents, and feedback to create owned improvements, experiments, or explicit no-change decisions.
- **AI / human / exit:** AI finds patterns without promoting experiments to standards; humans choose changes and approve governance evolution. Exit when each lesson has an owner and disposition.

## Proportional application

Low Risk work may combine framing, requirements, specification, review, and approval in one short design note. Medium and High Risk work separate stages and add depth or specialist review. Artifacts may shrink; explicit assumptions, approval, verification, and knowledge capture remain.
