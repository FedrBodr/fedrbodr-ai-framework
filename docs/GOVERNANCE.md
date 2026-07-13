# Governance

Governance defines authority, risk classification, and required gates. It applies whether work is performed manually, with one AI assistant, or through multiple agents.

## Responsibility boundaries

AI may research, ask questions, propose options, draft specifications, analyze risks, write plans, implement, test, perform preliminary reviews, and update documentation. These are contributions, not transfers of accountability.

Humans remain accountable for:

- business intent and acceptance criteria;
- risk acceptance and the required security level;
- data sensitivity and privacy obligations;
- major architectural choices and unresolved trade-offs;
- cost and operational commitments;
- production release of High Risk changes;
- unresolved uncertainty that could materially affect outcomes.

## Risk classification

Risk depends on impact, exposure, reversibility, uncertainty, data sensitivity, operational reach, and cost—not code size alone.

### Low Risk

Examples include editorial changes, narrowly scoped internal refactoring with strong tests, or reversible configuration changes without sensitive data or production impact. A compact specification or design note may combine lifecycle stages. Peer or owner review and focused verification are normally sufficient.

### Medium Risk

Examples include user-visible behavior, new integrations, meaningful data-flow changes, or work with moderate operational impact. Require an explicit specification, acceptance criteria, engineering-dimensions review, human approval, an implementation plan, and documented verification.

### High Risk

Examples include authentication or authorization, sensitive or regulated data, irreversible migrations, critical infrastructure, safety-related behavior, high availability commitments, or material financial exposure. Require deeper architecture, security, privacy, reliability, operational, and cost analysis; named human owners; specialist review where relevant; explicit approval; rollout and rollback plans; and human release authorization.

## Gates

1. **Specification gate:** Is the problem, scope, design, assumptions, relevant dimensions, acceptance criteria, and test strategy sufficient for the risk?
2. **Engineering review gate:** Have security, expected load, reliability, cost, and other applicable dimensions influenced the design?
3. **Human approval gate:** Has an accountable person approved the remaining uncertainty and implementation direction?
4. **Verification gate:** Does fresh evidence demonstrate acceptance criteria and expose unresolved failures or risks?
5. **Release gate:** Is rollout appropriate for the risk, with rollback and operational ownership where needed?
6. **Knowledge gate:** Have changed facts, decisions, specifications, and operational lessons returned to durable artifacts?

Emergency work may shorten or temporarily reorder gates only when delay creates greater harm. An accountable human records the reason, scope, risk, validation performed, and follow-up deadline. Emergency status is not permission to omit verification or permanently leave knowledge uncaptured.
