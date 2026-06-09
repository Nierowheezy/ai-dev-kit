# AI Dev Kit

My personal standard operating procedure for building software with AI agents (Claude Code, Cursor, Codex, OpenCode, etc.). Stack‑agnostic, tool‑agnostic, one‑command installable.

## Structure

- `agent.md` — Global system prompt and rules
- `skills/` — Reusable skill prompts (Anthropic Skills spec)
- `context/` — Project‑level memory and templates

## Usage

### 1. For Claude Code (automatic skill loading)

```bash
npx skills add Nierowheezy/ai-dev-kit
```
