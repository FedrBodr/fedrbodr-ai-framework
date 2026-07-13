# Specifications

Create one file per meaningful feature or change. A Low Risk change may use a compact version; a non-applicable section says `Not applicable` and briefly explains why. Unknowns belong under Assumptions or Open Questions, never as invented facts.

## Specification template

# Feature or Change Name

## Status

Draft | In Review | Approved | Implemented | Superseded

Record the owner, reviewers, approver, approval date, and revision or commit approved.

## Problem

What verified problem requires change, and why now?

## Goals

What outcomes should this change produce?

## Non-Goals

What is intentionally outside the change?

## Users and Use Cases

Who is affected, and which primary and abuse cases matter?

## Requirements

List uniquely identifiable functional and non-functional requirements.

## Assumptions

Record assumptions, owner, impact if wrong, and validation plan.

## Alternatives Considered

Compare realistic alternatives, including no change, and explain trade-offs.

## Proposed Design

Describe behavior, components, interfaces, decisions, and migration approach.

## System Boundaries

Identify in-scope systems, external actors, dependencies, ownership, and trust boundaries.

## Data and Data Classification

Describe processed data, sensitivity, location, retention, minimization, and access.

## Security Considerations

Cover threat actors, authentication, authorization, abuse cases, secrets, dependency risk, safe logging, impact of compromise, assumptions, and required human review.

## Expected Load

State expected users, normal and peak traffic, requests per second, concurrency, data volume and growth, deployment environment, and infrastructure constraints—or mark each material unknown.

## Performance Expectations

State latency, throughput, resource, and measurement expectations.

## Reliability Requirements

Define availability, failure behavior, recovery objectives, idempotency, and degradation where applicable.

## Observability

Define logs, metrics, traces, audit needs, alerts, and operational ownership without exposing sensitive data.

## Cost Considerations

State build, runtime, storage, network, vendor, and AI cost assumptions and guardrails.

## Compliance and Privacy

Identify obligations, data-subject needs, evidence, and accountable reviewers.

## Context and Tooling Considerations

Identify required source context, optional tools, output-compression risks, and raw-evidence fallback.

## Acceptance Criteria

Provide observable, testable outcomes traced to requirements.

## Test Strategy

Define unit, integration, system, security, performance, migration, and manual evidence as applicable.

## Rollout and Rollback

Describe release stages, compatibility, monitoring, rollback triggers, and ownership.

## Open Questions

List unresolved questions, impact, owner, and decision deadline.

## Human Review

Record specification, engineering, security or specialist reviews; approval decision; residual risks; and accountable approver.
