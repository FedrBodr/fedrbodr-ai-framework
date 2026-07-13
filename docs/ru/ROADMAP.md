# Roadmap

[English source](../ROADMAP.md) | Русский

> **Статус перевода:** актуален. Каноническим является [английский оригинал](../ROADMAP.md).

Roadmap показывает направление без обещания сроков. Перемещение между committed scope, exploration и long-term ideas требует свидетельств и review.

## Phase 0 — Foundation

- Манифест, терминология, архитектура, governance и первые ADR.
- Инженерный жизненный цикл и сквозные dimensions.
- Provider-neutral проектный шаблон со specification и review gates.
- Честные заметки об опциональных независимо поддерживаемых integration targets.

## Phase 1 — Project Standard

- Проверить и стабилизировать соглашение `docs/ai` в реальных репозиториях.
- Определить Engineering Knowledge Lifecycle: создание, валидацию, одобрение, использование, обновление, deprecation, архивирование, retrieval и восстановление производных indexes.
- Уточнить provider-neutral agent instructions и классификацию риска.
- Опубликовать руководства по внедрению и миграции.

Git-tracked durable knowledge остаётся авторитетным на всём жизненном цикле. RAG, vector stores, summaries, caches и indexes могут быть производными и перестраиваемыми слоями, но не единственным источником истины.

## Phase 2 — Reference Workflows

- Discovery и requirements.
- Specification, engineering review и human approval.
- Planning и TDD implementation.
- Specification compliance, code quality и security review.
- Verification, release, documentation update и передача между моделями.

Reference workflows становятся рекомендациями только после свидетельств реального использования.

## Phase 3 — Tooling Experiments

- Валидация структуры документации и ссылок.
- Опциональные CLI-эксперименты после подтверждения повторяющейся ручной боли.
- Эксперименты с thin provider adapters и MCP compatibility.
- Retrieval и RAG experiments с перестраиваемым производным состоянием.
- Оценка опциональных workflow, skill и context-efficiency integrations.

Эксперименты не являются обещанными функциями и могут быть отброшены. В версии 0.1 нет CLI, MCP server, adapter runtime, retrieval implementation или skills package manager.

## Phase 4 — Reference Implementations

- Оценить внедрение в отдельном проекте FedrBodr OS.
- Применить методологию в реальных software projects.
- Опубликовать примеры миграции провайдеров и risk-proportional workflows.
- Учесть измеренные уроки и стабилизировать доказавшие себя соглашения.

Reference implementations дают свидетельства, но не меняют спецификацию неявно.
