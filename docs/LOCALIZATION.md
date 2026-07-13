# Localization Policy

## Language layout

English is the canonical language of FedrBodr AI Framework:

- `README.md` is the default GitHub entry point.
- Core specifications remain at stable paths under `docs/`.
- ADRs, project templates, contribution rules, security policy, and agent instructions are maintained in English.

Russian translations use parallel discoverable paths:

- `README.ru.md` is the Russian repository entry point.
- `docs/ru/` contains translations of the core explanatory methodology.
- `docs/ru/README.md` records translation coverage and links to canonical sources.

English files are not moved into `docs/en/`. Keeping their existing paths preserves external links and avoids a repository-wide migration. Future languages should use an appropriate locale directory under `docs/` and a suffixed top-level README when needed.

## Source of truth

English documents are normative. Translations help readers understand and adopt the framework, but they do not create separate decisions or requirements. If a translation conflicts with its English source, the English source governs until the translation is corrected.

ADRs are not duplicated by default because two independently changing decision records would weaken the source-of-truth model. A translated explanation may link to an ADR, but the accepted record remains the English file.

## Translation workflow

1. Change and review the canonical English document.
2. Identify affected translations in the same pull request.
3. Update translations when practical; otherwise mark their status clearly in the translation index.
4. Preserve headings, links, diagrams, examples, qualifications, and maturity statements.
5. Keep commands, file paths, identifiers, normative status values, and proper names unchanged unless a localized explanation improves clarity without changing meaning.
6. Review terminology against both glossaries and validate local links and Mermaid blocks.

Machine translation may be used as a draft, but a human or accountable maintainer must review technical meaning before the translation is marked current.

## Translation status

- **Current:** reviewed against the present canonical document.
- **Needs review:** source changes may have made the translation incomplete or inaccurate.
- **Planned:** no maintained translation exists yet.

Git history records when translations changed. The translation index should be updated whenever coverage or status changes.
