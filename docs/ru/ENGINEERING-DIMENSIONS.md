# Инженерные аспекты

[English source](../ENGINEERING-DIMENSIONS.md) | Русский

> **Статус перевода:** актуален. Каноническим является [английский оригинал](../ENGINEERING-DIMENSIONS.md).

Engineering dimensions — сквозные перспективы для discovery, specification, architecture, implementation и verification. Не каждая задача требует одинаковой глубины. [Классификация риска](GOVERNANCE.md#классификация-риска) определяет соразмерный анализ и evidence.

## Краткий справочник

| Аспект | Ключевые вопросы | Когда нужно глубокое review | Что входит в specification | Примеры evidence |
| --- | --- | --- | --- | --- |
| Security | Какие существуют data, actors, threats, trust boundaries, access controls и abuse cases? | Sensitive data, exposed interfaces, identity, privilege, secrets или высокий impact | Security level, controls, assumptions, threat model, review triggers | Security tests, access-control cases, scan findings, review record |
| Privacy | Нужны ли personal data, законны ли обработка, minimization, retention и deletion? | Personal, behavioral, financial, health, location или regulated data | Data purpose, classification, retention, consent, subject rights | Data-flow review, deletion test, privacy assessment |
| Performance | Какие latency, throughput, concurrency и resource use требуются? | User-facing latency, high volume, constrained resources или expensive operations | Normal и peak targets, measurement method, assumptions | Benchmarks, profiles, representative load results |
| Reliability | Какие failures ожидаются и как система восстанавливается? | Critical paths, distributed state, external dependencies или строгая availability | Failure modes, availability, recovery objectives, degradation, rollback | Failure injection, recovery test, SLO evidence |
| Scalability | Как рост load и data меняет bottlenecks и topology? | Большой диапазон роста, hot partitions, fan-out или дорогое scaling | Growth assumptions, capacity limits, scaling approach | Capacity tests, scaling observations, limit analysis |
| Observability | Могут ли operators обнаружить, объяснить и исправить важное поведение? | Production services, async work, regulated audit или complex failures | Signals, ownership, alerts, correlation, safe logging | Dashboard и alert tests, trace/log inspection, runbook exercise |
| Maintainability | Могут ли contributors безопасно понимать, менять и удалять дизайн? | Long-lived systems, complex dependencies, turnover или shared platforms | Boundaries, dependency rules, migration и deprecation strategy | Review findings, dependency checks, change-impact test |
| Testability | Можно ли детерминированно проверить requirements и failure modes? | Hard-to-isolate dependencies, nondeterminism, stateful workflows или safety impact | Test seams, fixtures, environments, acceptance mapping | Unit, integration и system tests, traceability |
| Operability | Можно ли deploy, configure, support и restore систему? | On-call ownership, migrations, manual operations или multiple environments | Deployment, rollback, runbooks, ownership, recovery | Deployment rehearsal, rollback test, operational checklist |
| Cost | Какие build, runtime, storage, network, vendor и AI costs допустимы? | Usage-based services, uncertain scale, material commitments или poor reversibility | Cost model, budgets, assumptions, measurement, guardrails | Cost estimate, usage report, budget alert test |
| Compliance | Какие legal, contractual, audit или policy obligations действуют? | Regulated domains, customer commitments, cross-border data или audit scope | Applicable obligations, controls, evidence ownership | Control review, audit artifact, policy conformance check |
| Accessibility | Могут ли relevant users воспринимать продукт и управлять им? | User interfaces, public services, procurement или assistive technology users | Applicable standards, interaction и content requirements | Automated checks, keyboard и assistive-technology review |
| Context Efficiency | Сфокусирован ли контекст без потери authoritative evidence? | Large repositories, verbose tools, long agent sessions или token-based costs | Context sources, output policy, raw fallback, compression risks | Context audit, raw-output retrieval, before/after task evidence |

## Безопасность

Безопасность — вход проектирования и ответственность всего lifecycle, а не финальный scan.

Где применимо, specification отвечает:

- Какие данные обрабатываются: personal, financial, regulated, confidential или другие sensitive?
- Кто является legitimate users, threat actors, administrators, services и external parties?
- Какие существуют trust boundaries и data flows?
- Какие authentication и authorization models требуются?
- Какие возможны abuse cases, privilege paths, injection surfaces и denial-of-service risks?
- Какие secrets нужны и как они stored, scoped, rotated и revoked?
- Какие dependency и supply-chain risks добавляются?
- Как logs сохранят полезность без утечки secrets или sensitive data?
- Какие security assumptions и residual risks требуют human acceptance?
- Требует ли impact of compromise отдельного human security review?

Security requirements влияют на architecture, complexity, infrastructure, schedule и cost. Identity, authorization, cryptography, sensitive-data и internet-exposed изменения с высоким impact обычно требуют глубокого человеческого review и явных negative tests.

## Ожидаемая нагрузка и производительность

До одобрения архитектуры фиксируются значения или явные unknowns для:

- expected users и usage patterns;
- normal и peak traffic;
- requests per second и concurrent operations;
- data volume и expected growth;
- latency и throughput expectations;
- availability и recovery expectations;
- deployment environment и infrastructure constraints;
- resource и operational cost constraints.

Если точных чисел нет, owner проверяет явные assumptions, а дизайн описывает способ их валидации. AI не придумывает load characteristics. Архитектура без reviewed load assumptions — непроверенная догадка. Глубокое review нужно при bursty traffic, дорогой capacity, сложном partitioning, contractual latency или широком impact отказа. Evidence может включать representative load tests, profiling, capacity calculations, production observations и cost estimates с указанными ограничениями.

## Эффективность контекста

Context Efficiency сохраняет внимание и evidence, уменьшая малосигнальный материал. High-signal output включает failures, changed behavior, security findings, meaningful warnings, acceptance results и diagnostic traces. Low-signal output часто состоит из повторяющихся success lines, неизменного boilerplate, избыточных file listings или verbose progress.

Цель — не минимум tokens любой ценой, а:

- focused source selection и scoped tasks;
- удобный для людей и agents output;
- меньше ненужного context-window pressure и token-based cost;
- сжатие повторов с видимыми meaning и limitations;
- прямой доступ к original files, reports, logs и full command output.

> Сжимайте шум, а не свидетельства.

Не используйте compression, когда важен точный формат, output незнаком, диагностируется failure, присутствует security или data-loss risk, warnings могут быть существенными либо optimizer не даёт надёжный raw fallback. Summary не становится полным evidence только потому, что оно короче. Context compression дополняет хорошую context architecture, scoped tasks, focused files и durable documentation, но не заменяет их.
