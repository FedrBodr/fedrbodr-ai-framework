# Engineering Reviews

Review depth is proportional to risk. A Low Risk change may combine these reviews in one short record; Medium and High Risk work should keep findings and approvals explicit. Reviewers cite evidence and distinguish blocking issues, non-blocking improvements, and open risk.

## Specification Review

Confirm that the problem, requirements, assumptions, boundaries, alternatives, design, acceptance criteria, test strategy, and approval scope are clear. Check for contradictions, hidden implementation decisions, invented facts, and unresolved questions that block work.

## Engineering Dimensions Review

Review the applicable dimensions: Security, Privacy, Performance, Reliability, Scalability, Observability, Maintainability, Testability, Operability, Cost, Compliance, Accessibility where applicable, and Context Efficiency. Confirm that security and expected load influence design before architecture approval.

## Implementation Review

Review specification compliance first, then code quality and security. Trace behavior to requirements and tests. Identify scope drift, unsafe assumptions, weakened tests, incompatible interfaces, missing documentation, and operational consequences.

## Verification Review

Confirm and record:

- tests and checks executed, including environment and result;
- every acceptance criterion checked;
- security-relevant behavior and negative cases reviewed;
- relevant raw evidence retained and accessible;
- compressed output did not hide failures, warnings, or changed behavior;
- documentation and durable project knowledge updated;
- rollout or rollback evidence reviewed where applicable;
- unresolved failures and risks listed with owners;
- the final conclusion and decision owner approval required by risk.
