# Инженерный жизненный цикл

[English source](../ENGINEERING-LIFECYCLE.md) | Русский

> **Статус перевода:** актуален. Каноническим является [английский оригинал](../ENGINEERING-LIFECYCLE.md).

Компактный lifecycle: **Обдумать → Специфицировать → Проверить → Спланировать → Реализовать → Верифицировать → Сохранить знания → Улучшить**. Расширенный lifecycle ниже делает обязанности и gates явными. Стадии могут образовывать итерации, а не проходиться один раз по прямой.

Полная концептуальная последовательность:

**Business Problem → Discovery → Requirements → Specification → Architecture → Engineering Review → Human Approval → Implementation Plan → TDD Implementation → Specification Compliance Review → Code Quality and Security Review → Verification → Release → Documentation Update → Knowledge Capture → Improvement**

Практические стадии ниже объединяют Business Problem с Problem Framing, развивают архитектуру внутри Specification и Engineering Review, выполняют compliance и quality/security проверки в Review, а Documentation Update относят к Knowledge Capture. Это сохраняет ясные обязанности без дублирования gates.

## 1. Постановка проблемы

- **Цель:** определить бизнес- или пользовательскую проблему и её важность.
- **Входы:** наблюдения, запросы, инциденты, стратегия и существующий контекст.
- **Выходы:** problem statement, owner, желаемый результат, начальный scope и признаки риска.
- **Обязанности AI:** обобщить evidence, показать неоднозначность и задать точные вопросы, не придумывая intent.
- **Обязанности человека:** владеть intent, priority, constraints и решением продолжать работу.
- **Exit criteria:** проблема, owner, результат и важные unknowns сформулированы явно.

## 2. Discovery

- **Цель:** собрать evidence о пользователях, домене, текущей системе, альтернативах и ограничениях.
- **Входы:** сформулированная проблема, репозитории, research, знания stakeholders и operational evidence.
- **Выходы:** findings, ссылки на источники, assumptions, risks и unresolved questions.
- **Обязанности AI:** исследовать, сравнить варианты, проверить факты репозитория и отделить evidence от inference.
- **Обязанности человека:** предоставить доступ и domain context, проверить findings и разрешить конфликты priorities.
- **Exit criteria:** evidence достаточно для требований или решения не продолжать.

## 3. Требования

- **Цель:** превратить проблему в проверяемые результаты и ограничения.
- **Входы:** discovery findings, policies, user needs и business priorities.
- **Выходы:** функциональные и нефункциональные требования, acceptance measures, exclusions и traceability.
- **Обязанности AI:** написать точный draft, найти противоречия и недостающие engineering dimensions.
- **Обязанности человека:** одобрить business meaning, data sensitivity, compliance и priority.
- **Exit criteria:** требования проверяемы, ограничены scope и имеют owner; неизвестные видимы.

## 4. Спецификация

- **Цель:** описать предлагаемое решение достаточно для оценки до реализации.
- **Входы:** approved requirements, architecture, constraints, decisions и applicable dimensions.
- **Выходы:** draft specification с design, boundaries, security, load, reliability, cost, acceptance criteria, test strategy, rollout и open questions.
- **Обязанности AI:** описать варианты и trade-offs, сделать assumptions явными и не выдумывать load или security facts.
- **Обязанности человека:** предоставить существенные assumptions и оценить соответствие дизайна intent.
- **Exit criteria:** specification достаточна для risk-proportional engineering review.

## 5. Инженерное review

- **Цель:** проверить feasibility, safety, operability, maintainability и полноту specification.
- **Входы:** draft specification, architecture, applicable dimensions и evidence.
- **Выходы:** review findings, required changes, residual risks и recommendation.
- **Обязанности AI:** выполнить предварительное structured review, проверить traceability и найти conflicts и missing evidence.
- **Обязанности человека:** применить domain expertise, запросить specialist review и не пропустить unsupported assumptions.
- **Exit criteria:** blocking findings устранены или назначены; residual risk понятен.

## 6. Человеческое одобрение

- **Цель:** установить ответственное разрешение реализации и принятой неопределённости.
- **Входы:** reviewed specification, findings, trade-offs, estimates и residual risks.
- **Выходы:** Approved, Rejected или Revision Requested с approver и rationale.
- **Обязанности AI:** кратко представить decision record и не выводить approval из молчания.
- **Обязанности человека:** одобрить business intent, существенную architecture, security level, cost и risk acceptance.
- **Exit criteria:** required approvers явно разрешили конкретную revision specification.

## 7. План реализации

- **Цель:** превратить approved specification в упорядоченные, тестируемые и reviewable шаги.
- **Входы:** approved specification, repository state, architecture и delivery constraints.
- **Выходы:** tasks со ссылками на requirements, ожидаемые files, tests, verification, dependencies и completion evidence.
- **Обязанности AI:** предложить небольшие шаги, показать unknowns и сохранить alignment с approved design.
- **Обязанности человека:** подтвердить sequencing, ownership, operational constraints и plan-level trade-offs.
- **Exit criteria:** каждый task даёт независимо reviewable result и verification evidence.

## 8. TDD-реализация

- **Цель:** реализовать поведение короткими test-driven feedback loops там, где оно тестируемо.
- **Входы:** approved specification и plan, current code и test infrastructure.
- **Выходы:** tests, minimal implementation, refactoring и task-level evidence.
- **Обязанности AI:** следовать red–green–refactor, соблюдать scope, показывать blockers и не ослаблять tests ради успеха.
- **Обязанности человека:** разрешать ambiguous intent, проверять consequential choices и вмешиваться при design change.
- **Exit criteria:** запланированное поведение реализовано, relevant tests проходят, deviations возвращены в specification review.

Для documentation-only, exploratory и другой non-behavioral работы используется ближайший feedback loop со свидетельствами, а не бессмысленные тесты.

## 9. Review

- **Цель:** независимо оценить specification compliance, code quality, security и maintainability.
- **Входы:** approved specification, plan, diff, tests и implementation notes.
- **Выходы:** findings по impact, resolved issues и residual concerns.
- **Обязанности AI:** провести preliminary specification и quality reviews с конкретным evidence.
- **Обязанности человека:** проверить существенное поведение и risk, разрешить findings и отклонить unsupported completion claims.
- **Exit criteria:** blocking findings устранены; remaining risks явны и имеют owners.

## 10. Верификация

- **Цель:** показать, что acceptance criteria и relevant quality properties выполняются в целевом окружении.
- **Входы:** reviewed implementation, acceptance criteria, test strategy, deployment assumptions и raw evidence.
- **Выходы:** test results, acceptance checks, security и operational evidence, failures и conclusion.
- **Обязанности AI:** выполнить свежие checks, сохранить relevant raw output и сообщить failures без преуменьшения.
- **Обязанности человека:** оценить достаточность evidence, особенно для High Risk и нетестируемого автоматически поведения.
- **Exit criteria:** evidence разрешает или блокирует release; unresolved risks перечислены.

## 11. Релиз

- **Цель:** доставить проверенное изменение с контролируемым operational risk.
- **Входы:** release approval, artifacts, rollout и rollback plan, observability и operational ownership.
- **Выходы:** released change, deployment record, observed health или documented rollback.
- **Обязанности AI:** подготовить release material, выполнять только разрешённые шаги и отслеживать заданные signals при наличии tools.
- **Обязанности человека:** разрешить High Risk production release, владеть incident decisions и принять operational consequences.
- **Exit criteria:** release state известен, health checks завершены, rollback доступен согласно specification.

## 12. Сохранение знаний

- **Цель:** вернуть проверенный опыт и изменившиеся факты в durable project knowledge.
- **Входы:** specification, decisions, implementation, reviews, verification, release observations и incidents.
- **Выходы:** updated context, architecture, ADRs, runbooks, roadmap, specifications и deprecation notes.
- **Обязанности AI:** предложить focused updates, удалить stale claims и сохранить ссылки на evidence.
- **Обязанности человека:** одобрить consequential knowledge и не допустить sensitive information в Git.
- **Exit criteria:** maintained artifacts соответствуют verified system state, важный опыт доступен для поиска.

## 13. Улучшение

- **Цель:** улучшать product, workflow, skills и governance по наблюдаемым результатам.
- **Входы:** outcomes, defects, cycle time, context usage, cost, incidents и contributor feedback.
- **Выходы:** prioritized improvements, experiments, changed practices или explicit no-change decisions.
- **Обязанности AI:** анализировать patterns и предлагать bounded experiments, не превращая их в standards.
- **Обязанности человека:** выбирать changes, оценивать trade-offs и одобрять evolution governance или architecture.
- **Exit criteria:** learning имеет owner и disposition; accepted methodology changes записаны явно.

## Соразмерное применение

Low Risk работа может объединить framing, requirements, specification, review и approval в одной короткой design note, а затем использовать focused plan и verification record. Medium и High Risk разделяют стадии и добавляют глубину или specialist review. Артефакты могут сокращаться; intent — явные assumptions, approval, verification и knowledge capture — не исчезает.
