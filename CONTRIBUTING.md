# Contributing

FedrBodr AI Framework is an early-stage, documentation-first project. Contributions should improve the specification, templates, or evidence behind the practices without overstating their maturity.

## Proposing a change

1. Open an issue or discussion for broad, ambiguous, or architectural proposals when the relevant GitHub feature is available.
2. Explain the problem, intended users, alternatives, and how the proposal supports the roadmap.
3. Submit a focused pull request with the documentation and template changes needed to keep the repository internally consistent.

For architecturally significant or difficult-to-reverse changes, add an ADR in `docs/decisions/`. Smaller decisions may be explained directly in the pull request.

## Documentation-first workflow

- Start from user and engineering needs, then update the specification before proposing tooling.
- Use provider-neutral language. Provider-specific behavior belongs in a clearly identified example or compatibility note.
- Distinguish implemented practices, committed scope, experiments, and long-term ideas.
- Update the glossary when introducing a term with framework-level meaning.
- Update affected templates when a specification change alters project adoption.

## Pull request expectations

- Prefer small, reviewable pull requests with one coherent purpose.
- Check headings, relative links, file names, and Mermaid syntax.
- Read the changed documents as a set and remove contradictions or stale claims.
- Do not include secrets, personal data, or content from separate projects.
- Describe how the change was validated.

[Conventional Commits](https://www.conventionalcommits.org/) are recommended for readable history, for example `docs: clarify project memory lifecycle`, but they are not required.

Participation is governed by the [Code of Conduct](CODE_OF_CONDUCT.md). Report sensitive security matters according to the [Security Policy](SECURITY.md).
