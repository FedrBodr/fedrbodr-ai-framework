# Architecture

Record the current, verified architecture. Link to detailed diagrams or ADRs rather than duplicating them.

## System context

Describe the system's purpose, actors, and external environment.

## Boundaries

Define what is inside the system, what is outside, and who owns each boundary.

## Components

List major components, their responsibilities, and their maturity or deployment status.

## Dependencies

Document internal and external dependencies, dependency direction, and failure assumptions.

## Data flows

Describe important inputs, transformations, storage, outputs, trust boundaries, and data retention.

## Security boundaries

Identify data classifications, actors, trust boundaries, authentication, authorization, secrets, abuse cases, safe logging constraints, and human security-review triggers. Link to a threat model where risk warrants one.

## Expected load and performance

Record expected users, normal and peak traffic, requests per second, concurrency, data volume and growth, latency, availability, recovery, deployment environment, infrastructure constraints, and cost constraints. Mark unknown values as explicit assumptions for human review; do not invent them.

## Constraints

Record technical, operational, regulatory, compatibility, cost, and organizational constraints.

## Engineering dimensions

State how Security, Privacy, Performance, Reliability, Scalability, Observability, Maintainability, Testability, Operability, Cost, Compliance, Accessibility where applicable, and Context Efficiency affect this architecture. Link to deeper reviews rather than duplicating them.

## Risks

List material architectural risks, their impact, mitigation, and owner where known.

## Open questions

Track unresolved architectural questions with the decision or evidence needed to close them.
