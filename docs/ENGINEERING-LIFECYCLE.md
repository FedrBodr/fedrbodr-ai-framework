# Engineering Lifecycle

[English](ENGINEERING-LIFECYCLE.md) | [Русский](ru/ENGINEERING-LIFECYCLE.md)

The compact lifecycle is **Think → Specify → Review → Plan → Generate → Verify → Capture Knowledge → Improve**. The extended lifecycle below makes responsibilities and gates explicit. Stages may iterate rather than proceed once in a straight line.

The full conceptual sequence is:

**Business Problem → Discovery → Requirements → Specification → Architecture → Engineering Review → Human Approval → Implementation Plan → TDD Implementation → Specification Compliance Review → Code Quality and Security Review → Verification → Release → Documentation Update → Knowledge Capture → Improvement**

The operational stages below combine the Business Problem with Problem Framing, develop architecture within Specification and Engineering Review, perform both compliance and quality/security checks within Review, and treat Documentation Update as part of Knowledge Capture. These combinations keep ownership clear without duplicating gates.

## 1. Problem Framing

- **Purpose:** Define the business or user problem and why it matters.
- **Inputs:** Observations, requests, incidents, strategy, and existing project context.
- **Outputs:** Problem statement, owner, desired outcome, initial scope, and risk signals.
- **AI responsibilities:** Synthesize evidence, expose ambiguity, and ask focused questions without inventing intent.
- **Human responsibilities:** Own intent, priority, constraints, and the decision to proceed.
- **Exit criteria:** The problem, owner, outcome, and important unknowns are explicit.

## 2. Discovery

- **Purpose:** Gather evidence about users, domain, current system, alternatives, and constraints.
- **Inputs:** Framed problem, repositories, research, stakeholder knowledge, and operational evidence.
- **Outputs:** Findings, source links, assumptions, risks, and unresolved questions.
- **AI responsibilities:** Research, compare options, trace repository facts, and distinguish evidence from inference.
- **Human responsibilities:** Provide access and domain context, validate findings, and resolve priority conflicts.
- **Exit criteria:** Evidence is sufficient to state requirements or the decision not to proceed.

## 3. Requirements

- **Purpose:** Translate the problem into verifiable outcomes and constraints.
- **Inputs:** Discovery findings, policies, user needs, and business priorities.
- **Outputs:** Functional and non-functional requirements, acceptance measures, exclusions, and traceability.
- **AI responsibilities:** Draft precise requirements, find contradictions, and identify missing engineering dimensions.
- **Human responsibilities:** Approve business meaning, data sensitivity, compliance needs, and priority.
- **Exit criteria:** Requirements are testable, scoped, and owned; unknowns are visible.

## 4. Specification

- **Purpose:** Define a proposed solution sufficiently to evaluate before implementation.
- **Inputs:** Approved requirements, architecture, constraints, decisions, and applicable dimensions.
- **Outputs:** Draft specification covering design, boundaries, security, load, reliability, cost, acceptance criteria, test strategy, rollout, and open questions.
- **AI responsibilities:** Draft options and trade-offs, make assumptions explicit, and avoid silently fabricating load or security facts.
- **Human responsibilities:** Supply consequential assumptions and judge whether the proposed design serves the intent.
- **Exit criteria:** The specification is complete enough for risk-proportional engineering review.

## 5. Engineering Review

- **Purpose:** Challenge feasibility, safety, operability, maintainability, and specification completeness.
- **Inputs:** Draft specification, architecture, applicable engineering dimensions, and evidence.
- **Outputs:** Review findings, required changes, residual risks, and an approval recommendation.
- **AI responsibilities:** Perform preliminary structured review, trace requirements, and surface conflicts and missing evidence.
- **Human responsibilities:** Apply domain expertise, request specialist review, and prevent unsupported assumptions from passing.
- **Exit criteria:** Blocking findings are resolved or explicitly assigned; residual risk is understandable.

## 6. Human Approval

- **Purpose:** Establish accountable authorization for implementation and accepted uncertainty.
- **Inputs:** Reviewed specification, findings, trade-offs, estimates, and residual risks.
- **Outputs:** Approved, rejected, or revision-requested status with approver and rationale.
- **AI responsibilities:** Present the decision record concisely and never infer approval from silence.
- **Human responsibilities:** Approve business intent, consequential architecture, security level, cost, and risk acceptance.
- **Exit criteria:** Required approvers explicitly authorize a specific specification revision.

## 7. Implementation Planning

- **Purpose:** Translate an approved specification into ordered, testable, reviewable steps.
- **Inputs:** Approved specification, repository state, architecture, and delivery constraints.
- **Outputs:** Tasks linked to requirements, expected files, tests, verification, dependencies, and completion evidence.
- **AI responsibilities:** Propose small steps, identify unknowns, and keep the plan aligned with the approved design.
- **Human responsibilities:** Confirm sequencing, ownership, operational constraints, and any plan-level trade-offs.
- **Exit criteria:** Each task can produce an independently reviewable result and verification evidence.

## 8. TDD Implementation

- **Purpose:** Implement behavior through short test-driven feedback loops where behavior can be tested.
- **Inputs:** Approved specification and plan, current code, and test infrastructure.
- **Outputs:** Tests, minimal implementation, refactoring, and task-level evidence.
- **AI responsibilities:** Follow red–green–refactor, preserve scope, expose blockers, and avoid weakening tests to manufacture success.
- **Human responsibilities:** Resolve ambiguous intent, review consequential choices, and intervene when implementation reveals a design change.
- **Exit criteria:** Planned behavior is implemented, relevant tests pass, and deviations return to specification review.

For documentation-only, exploratory, or otherwise non-behavioral work, use the closest evidence-producing feedback loop rather than adding meaningless tests.

## 9. Review

- **Purpose:** Independently assess specification compliance, code quality, security, and maintainability.
- **Inputs:** Approved specification, plan, diff, tests, and implementation notes.
- **Outputs:** Findings classified by impact, resolved issues, and residual concerns.
- **AI responsibilities:** Perform preliminary specification and quality reviews and cite concrete evidence.
- **Human responsibilities:** Review material behavior and risk, adjudicate findings, and reject unsupported completion claims.
- **Exit criteria:** Blocking findings are resolved; remaining risks are explicit and owned.

## 10. Verification

- **Purpose:** Demonstrate that acceptance criteria and relevant quality properties hold in the intended environment.
- **Inputs:** Reviewed implementation, acceptance criteria, test strategy, deployment assumptions, and raw evidence.
- **Outputs:** Test results, acceptance checks, security and operational evidence, failures, and verification conclusion.
- **AI responsibilities:** Run fresh checks, preserve relevant raw output, and report failures without minimizing them.
- **Human responsibilities:** Judge evidence sufficiency, especially for High Risk work and behavior that automation cannot establish.
- **Exit criteria:** Required evidence supports release or clearly blocks it; unresolved risks are listed.

## 11. Release

- **Purpose:** Deliver verified change with controlled operational risk.
- **Inputs:** Release approval, artifacts, rollout and rollback plan, observability, and operational ownership.
- **Outputs:** Released change, deployment record, observed health, or documented rollback.
- **AI responsibilities:** Prepare release material, execute only authorized steps, and monitor defined signals when tools permit.
- **Human responsibilities:** Authorize High Risk production release, own incident decisions, and accept operational consequences.
- **Exit criteria:** Release state is known, health checks are complete, and rollback remains available as specified.

## 12. Knowledge Capture

- **Purpose:** Return validated learning and changed facts to durable project knowledge.
- **Inputs:** Specification, decisions, implementation, reviews, verification, release observations, and incidents.
- **Outputs:** Updated context, architecture, ADRs, runbooks, roadmap, specifications, and deprecation notes.
- **AI responsibilities:** Propose focused updates, remove stale claims, and preserve links to evidence.
- **Human responsibilities:** Approve consequential knowledge and ensure sensitive information stays outside Git.
- **Exit criteria:** Maintained artifacts match the verified system state and important learning is retrievable.

## 13. Improvement

- **Purpose:** Improve the product, workflow, skills, and governance from observed results.
- **Inputs:** Outcomes, defects, cycle time, context usage, cost, incidents, and contributor feedback.
- **Outputs:** Prioritized improvements, experiments, changed practices, or explicit no-change decisions.
- **AI responsibilities:** Analyze patterns and propose bounded experiments without promoting them to standards.
- **Human responsibilities:** Choose changes, evaluate trade-offs, and approve evolution of governance or architecture.
- **Exit criteria:** Learning has an owner and disposition; accepted methodology changes are recorded explicitly.

## Proportional application

Low Risk work may combine framing, requirements, specification, review, and approval in one compact design note, then use a focused plan and verification record. Medium and High Risk work separate stages and add depth or specialist review. The artifacts may shrink; the intent—explicit assumptions, approval, verification, and knowledge capture—does not disappear.
