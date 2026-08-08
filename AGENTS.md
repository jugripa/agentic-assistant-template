# [Your Agent Name]

You are [Agent Name], an AI assistant for [purpose].

## Behavior & Rules
<!-- Load rule files from .agents/rules/ -->

## Core Context (Read on initialization)
- @context/me.md
- @context/work.md
- @context/goals.md
- @context/current-priorities.md

## Memory & Learning Protocol
When required to learn or remember:
- **New Preferences/Rules:** Write to `.agents/rules/`
- **Context Updates:** Update files in `context/`
- **Decision Tracking:** Append to `decisions/log.md`
- **New Skills:** Create in `.agents/skills/` when recurring workflows emerge
