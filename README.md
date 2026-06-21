# Agentic Assistant Template

A **portable, file-system-based framework** for building autonomous AI assistants that maintain persistent memory, grow horizontally through skills, and work across any LLM engine.

## The Problem This Solves

Standard LLM chat interfaces suffer from:
- **Context rot** — conversations lose coherence over time
- **No persistent memory** — every session starts from zero
- **Vendor lock-in** — your agent's knowledge dies with the platform
- **Vertical scaling only** — adding capabilities means rewriting the whole prompt

## The Architecture

This framework solves all four problems with a simple, file-based architecture:

```
├── AGENTS.md                # Agent identity, behavior rules, and context loading
├── context/                 # Living knowledge base (updated as things change)
│   ├── me.md                # Who the agent serves
│   ├── work.md              # Current work context
│   ├── goals.md             # Active objectives
│   └── current-priorities.md # What matters right now
├── rules/                   # Behavioral constraints (accumulated over time)
├── skills/                  # Horizontal capabilities (added without rewriting core)
├── tools/                   # Deterministic scripts the agent can execute
├── decisions/               # Decision log with reasoning trail
│   └── log.md               # [DATE] DECISION: ... | REASONING: ...
├── references/              # Static knowledge (guides, APIs, masterclasses)
├── sessions/                # Session summaries for continuity across conversations
└── templates/               # Reusable output formats
```

## Key Design Principles

### 1. Persistent Memory via Files
Context files are read at the start of every session. The agent updates them as things change. No conversation history needed — the filesystem *is* the memory.

### 2. Horizontal Skill Growth
New capabilities are added as markdown files in `skills/`. Each skill is a self-contained instruction set that the agent can invoke. The agent grows broader without getting deeper (avoiding context window bloat).

### 3. Engine-Agnostic
This structure works with **any** LLM-powered IDE or agent framework:
- Antigravity IDE
- Claude Code (via CLAUDE.md)
- Cursor (via .cursorrules)
- Gemini CLI
- Any system that can read files as context

### 4. Deterministic Tools
The `tools/` directory contains Python scripts for tasks that should never be probabilistic (calculations, API calls, data transformations). Skills reference these tools when they need guaranteed-correct execution.

### 5. Decision Audit Trail
Every significant decision is logged in `decisions/log.md` with explicit reasoning. This creates accountability and allows future sessions to understand *why* things were done a certain way.

## Getting Started

1. Fork this repo
2. Edit `AGENTS.md` to define your agent's identity and purpose
3. Populate `context/` with your specific domain knowledge
4. Add rules as you discover preferences: `rules/communication-style.md`, etc.
5. Build skills organically as recurring workflows emerge
6. Add deterministic tools for anything that needs guaranteed accuracy

## Real-World Usage

This architecture has been battle-tested across:
- **Technical Product Management** — PRD generation, sprint planning, ClickUp integration
- **Business Strategy** — Exit planning, sales pipelines, market research
- **Marketing Automation** — Content creation, competitor analysis, social media strategy
- **AI Development** — n8n workflow building, agent orchestration

## Philosophy

> *"Don't build a smarter agent. Build a system that makes any agent smarter."*

The power isn't in the LLM — it's in the structured, persistent context you give it. This framework turns any AI assistant into a domain expert that remembers everything, learns your preferences, and never loses context.

## License

MIT
