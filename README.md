# cmit-starter

Стартер ЦМИТ для новых проектов, где регулярно работают AI-агенты (Claude Code, Codex, Cursor). Docs-first: правила агента, проектная документация, память состояния — без прикладного runtime.

## Как использовать

1. Создать новый репозиторий из этого шаблона (кнопка **Use this template**) или скопировать файлы.
2. Пройти `agent_docs/setup-checklist.md` и удалить его.
3. Заполнить «Описание проекта» в `AGENTS.md`.

## Из чего собран

Стартер — гибрид двух проектов:

- **[2030ai/2030ai-project-template](https://github.com/2030ai/2030ai-project-template)** — основа: `AGENTS.md` с принципами работы агента (`CLAUDE.md` — ссылка на него), структура `agent_docs/` (архитектура, глоссарий, атомарные ADR и development-history, гайды, шаблоны), skills-зеркала для Claude/Codex/Cursor, `.gitignore` / `.editorconfig` / `.cursorignore` / markdownlint CI.
- **[alexeykrol/claude-code-starter](https://github.com/alexeykrol/claude-code-starter)** — двухосевая модель памяти: `agent_docs/invariants.md` (жёсткие правила продукта), `agent_docs/snapshot.md` (текущая точка работы), `agent_docs/backlog.md` (Next / Soon / Later / Won't do). Тяжёлая часть фреймворка (hooks, релизная машинерия) сознательно не взята.

## Структура

- `AGENTS.md` — правила работы агента над проектом; единый источник для всех AI-инструментов.
- `agent_docs/index.md` — карта документов.
- `agent_docs/invariants.md` — что не должно произойти с продуктом; нарушение = баг.
- `agent_docs/snapshot.md` + `agent_docs/backlog.md` — состояние: читать при старте сессии, обновлять при завершении.
- `agent_docs/adr/`, `agent_docs/development-history/` — атомарные журналы решений и итераций.
- `.agents/skills/` — canonical source проектных skills, зеркала в `.claude/`, `.codex/`, `.cursor/`.
