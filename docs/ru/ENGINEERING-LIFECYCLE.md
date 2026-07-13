# Инженерный жизненный цикл

[English source](../ENGINEERING-LIFECYCLE.md) | Русский

> **Статус перевода:** актуален. Каноническим является [английский оригинал](../ENGINEERING-LIFECYCLE.md).

Компактный цикл: **Обдумать → Специфицировать → Проверить → Спланировать → Реализовать → Верифицировать → Сохранить знания → Улучшить**.

Полная последовательность: **Бизнес-проблема → Discovery → Требования → Спецификация → Архитектура → Инженерное review → Утверждение владельцем решения → План реализации → TDD-реализация → Проверка соответствия спецификации → Review качества и безопасности → Верификация → Релиз → Обновление документации → Сохранение знаний → Улучшение**.

Практические стадии ниже объединяют связанные шаги, не убирая их смысл. Работа может возвращаться назад.

## 1. Постановка проблемы

- **Цель / входы / выходы:** превратить наблюдения, запросы, инциденты и стратегию в problem statement с владельцем, желаемым результатом, scope и признаками риска.
- **AI / человек / выход:** AI показывает неоднозначность, не придумывая intent. Человек владеет priority и constraints. Стадия завершена, когда проблема, владелец, результат и важные unknowns явны.

## 2. Discovery

- **Цель / входы / выходы:** использовать репозитории, research, знания stakeholders и operational evidence для findings со ссылками, assumptions, risks и open questions.
- **AI / человек / выход:** AI отделяет evidence от inference. Люди дают domain context и проверяют findings. Стадия завершена, когда evidence достаточно для требований или решения остановиться.

## 3. Требования

- **Цель / входы / выходы:** превратить проверенные findings и policies в scoped, traceable функциональные и нефункциональные требования с acceptance measures.
- **AI / человек / выход:** AI пишет draft и ищет противоречия; люди утверждают business meaning, data sensitivity, compliance и priority. Стадия завершена, когда требования тестируемы, имеют владельцев и показывают unknowns.

## 4. Спецификация

- **Цель / входы / выходы:** превратить approved requirements, architecture, constraints и decisions в design с boundaries, security, load, reliability, cost, acceptance, tests, rollout и open questions.
- **AI / человек / выход:** AI показывает варианты и явные assumptions; люди дают существенные факты и оценивают соответствие задаче. Стадия завершена, когда specification готова к risk-proportional review.

## 5. Инженерное review

- **Цель / входы / выходы:** проверить feasibility, security, operability, maintainability и полноту; получить findings, required changes и residual risks.
- **AI / человек / выход:** AI проводит structured preliminary review; люди применяют domain expertise и привлекают специалистов. Стадия завершена, когда blockers устранены или назначены, а residual risk понятен.

## 6. Утверждение владельцем решения

- **Цель / входы / выходы:** превратить reviewed specification, trade-offs, estimates и residual risks в явное approval, rejection или revision request для конкретной версии.
- **AI / человек / выход:** AI кратко представляет решение и не выводит approval из молчания. Владелец решения принимает intent, существенную architecture, security level, cost и risk. Стадия завершена после зафиксированного утверждения нужными владельцами.

## 7. План реализации

- **Цель / входы / выходы:** превратить approved specification в упорядоченные задачи со ссылками на requirements, files, tests, dependencies, verification и completion evidence.
- **AI / человек / выход:** AI предлагает небольшие reviewable steps; люди подтверждают sequence, ownership и operational constraints. Стадия завершена, когда каждая задача даёт независимо проверяемый результат.

## 8. TDD-реализация

- **Цель / входы / выходы:** по approved plan и циклу red–green–refactor создать tests, minimal implementation, refactoring и task evidence.
- **AI / человек / выход:** AI соблюдает scope и не ослабляет tests; люди разрешают неоднозначность и существенные design changes. Стадия завершена, когда planned behavior проходит relevant tests, а deviations возвращены в specification review.

Для документации, exploration и другой non-behavioral работы используйте ближайший feedback loop со свидетельствами, а не бессмысленные тесты.

## 9. Review

- **Цель / входы / выходы:** сначала проверить specification compliance, затем code quality, security и maintainability; получить findings по impact и residual concerns.
- **AI / человек / выход:** AI приводит конкретное evidence; люди разрешают существенные findings и unsupported completion claims. Стадия завершена, когда blockers устранены, а remaining risks имеют владельцев.

## 10. Верификация

- **Цель / входы / выходы:** проверить acceptance criteria и нужные quality properties в целевом окружении; получить test, security, operational и failure evidence.
- **AI / человек / выход:** AI выполняет свежие checks и сохраняет relevant raw output; люди оценивают достаточность evidence. Стадия завершена, когда evidence явно разрешает или блокирует release, а unresolved risks перечислены.

## 11. Релиз

- **Цель / входы / выходы:** доставить verified change с approved artifacts, rollout, rollback, observability и operational ownership; зафиксировать release state и health.
- **AI / человек / выход:** AI выполняет только разрешённые шаги; люди разрешают High Risk production releases и владеют incidents. Стадия завершена, когда state и health известны, а rollback доступен согласно specification.

## 12. Сохранение знаний

- **Цель / входы / выходы:** превратить specifications, decisions, reviews, verification, release observations и incidents в обновлённые context, architecture, ADRs, runbooks и plans.
- **AI / человек / выход:** AI предлагает focused updates и удаляет stale claims; люди утверждают consequential knowledge и защищают sensitive data. Стадия завершена, когда maintained artifacts соответствуют verified reality.

## 13. Улучшение

- **Цель / входы / выходы:** использовать outcomes, defects, cycle time, cost, incidents и feedback для улучшений, experiments или explicit no-change decisions с владельцами.
- **AI / человек / выход:** AI ищет patterns, не превращая experiments в standards; люди выбирают changes и утверждают evolution governance. Стадия завершена, когда каждый lesson имеет owner и disposition.

## Соразмерное применение

Low Risk работа может объединить framing, requirements, specification, review и approval в одной короткой design note. Medium и High Risk разделяют стадии и добавляют глубину или specialist review. Артефакты могут сокращаться; явные assumptions, approval, verification и knowledge capture остаются.
