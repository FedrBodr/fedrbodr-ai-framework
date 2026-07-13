# ADR 0002: Specification Before Implementation

## Status

Accepted

## Context

AI can generate code before requirements, assumptions, security needs, load expectations, and acceptance criteria have been examined. That makes implementation the hidden location of design decisions and raises the cost of detecting a wrong premise. At the same time, requiring a large formal specification for every trivial edit would discourage adoption without reducing meaningful risk.

## Decision

No meaningful implementation begins before a sufficient written specification exists and receives the decision owner approval required by its risk classification.

Specification depth is proportional to impact, uncertainty, reversibility, exposure, data sensitivity, and operational cost. Low Risk work may use a compact design note that combines problem, scope, assumptions, affected dimensions, acceptance criteria, and approval. Medium and High Risk work require progressively deeper review and explicit decision records.

When behavior can be tested, the approved specification is translated into a testable plan and TDD implementation. If implementation reveals a material design change or invalid assumption, work returns to specification and approval rather than silently changing scope.

An emergency may shorten or reorder the process only when delay creates greater harm. An accountable human records the reason, scope, validation performed, and time-bound follow-up.

## Consequences

Benefits:

- Hidden requirements and design assumptions become reviewable before generation.
- Security, load, reliability, and cost can influence architecture early.
- Tests and verification can trace to explicit acceptance criteria.
- Process remains lightweight for genuinely Low Risk work.

Costs and limitations:

- Teams must invest thought before seeing implementation.
- Risk classification and specification sufficiency require human judgment.
- Emergency exceptions can become loopholes unless documented and reviewed.
- A written specification can still be wrong; discovery, review, and verification remain necessary.
