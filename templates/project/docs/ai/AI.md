# AI Working Guide

## Purpose

Define how humans and AI agents work in this repository, which artifacts are authoritative, which gates apply, and what evidence is required. Keep this guide provider-neutral.

## Source-of-truth hierarchy

Tailor this hierarchy and resolve conflicts explicitly:

1. Human-approved policies, requirements, specifications, and accepted ADRs.
2. Current product code, tests, schemas, and machine-readable configuration.
3. Maintained context, architecture, and operational documentation.
4. Approved implementation plans and active work tracking.
5. Task instructions and ephemeral conversation context.

An agent must flag material conflicts rather than silently choosing a convenient source.

## Reading order

1. This file and the repository `AGENTS.md`.
2. `CONTEXT.md` and `ARCHITECTURE.md`.
3. `DECISIONS.md` and linked ADRs.
4. The applicable file under `specs/`, then its approved plan under `plans/`.
5. Relevant review records under `reviews/`, roadmap, and active TODOs.
6. Reusable prompt guidance only when it matches the task.

## Process selection and risk

Classify work using impact, exposure, reversibility, uncertainty, data sensitivity, operational reach, and cost.

- **Low Risk:** a compact design note may combine specification, review, and approval.
- **Medium Risk:** require an explicit specification, engineering review, approval, plan, and verification record.
- **High Risk:** add deeper architecture, security, privacy, reliability, operational, cost, specialist, rollout, rollback, and release review.

Record the classification and rationale. Code size alone does not determine risk.

## Specification gate

Do not begin meaningful implementation until a written specification is sufficient for the risk. It must make the problem, goals, non-goals, requirements, assumptions, design, applicable dimensions, acceptance criteria, and test strategy reviewable. Mark unknowns; never silently invent them.

## Engineering review gate

Review applicable dimensions before approval: Security, Privacy, Performance, Reliability, Scalability, Observability, Maintainability, Testability, Operability, Cost, Compliance, Accessibility where applicable, and Context Efficiency. Security and expected load are architecture inputs, not final checklists.

## Decision owner approval gate

The decision owner approves business intent, data sensitivity, security level, major architecture, cost commitments, accepted risk, and consequential release. An agent may recommend a decision but must not infer approval from silence.

## Implementation rules

- Work from the approved specification and plan; return for approval when material design changes.
- Use red–green–refactor for behavior changes where tests are meaningful.
- Keep changes focused and preserve unrelated work.
- Never weaken tests or omit findings to create the appearance of success.
- Do not introduce secrets, sensitive personal data, or fabricated facts.

## Evidence requirements

Completion requires fresh evidence mapped to acceptance criteria: relevant tests and checks, implementation review, security-relevant negative cases, and documented limitations. Preserve failing tests, useful stack traces, security findings, meaningful warnings, changed behavior, unresolved errors, and acceptance results.

## Context efficiency

Use focused files, scoped tasks, and concise tool output. Compress repetitive noise only when original output remains retrievable and omitted detail cannot change the decision. Use raw output for unfamiliar failures, security review, exact-format checks, incidents, or whenever a summary is insufficient.

## Knowledge-update obligations

When work changes architecture, context, requirements, accepted decisions, priorities, risks, operations, or reusable guidance, update the corresponding durable artifact in the same change. Mark superseded specifications and decisions rather than erasing history. Remove stale active status when Git already preserves the record.

## Definition of done

The approved acceptance criteria are met; required reviews and tests have fresh evidence; security, load, and other applicable dimensions were considered; documentation matches behavior; unresolved risks are listed and owned; and the diff contains no unrelated changes.
