# AI Dev Kit

> A personal, battle-tested standard for building software with any AI agent — Claude Code, Cursor, Codex, OpenCode, Grok, and more.

It’s a **stack-agnostic, tool-agnostic** collection of rules, skills, and memory files.  
Drop it into a project, give your AI a single instruction, and it knows **exactly** how you work.

---

## Why This Exists

AI coding assistants are powerful but forgetful. Without a shared “brain”, you waste time re-explaining:

- Tech stack conventions
- Design tokens and UI rules
- Task order and progress
- Which components already exist

This kit is a **permanent, portable operating manual** for your AI, so every session starts with full context — no repetition, no guessing, no drift.

---

## Structure

```
ai-dev-kit/
├── .agents/
│   └── skills/
│       ├── architect/
│       │   └── SKILL.md
│       ├── imprint/
│       │   └── SKILL.md
│       ├── recover/
│       │   └── SKILL.md
│       ├── remember/
│       │   └── SKILL.md
│       └── review/
│           └── SKILL.md
├── context/
│   ├── designs/              # Active design screenshots for the current project
│   ├── designs-old/          # Archived design screenshots
│   ├── architecture.md
│   ├── build-plan.md
│   ├── code-standards.md
│   ├── library-docs.md
│   ├── progress-tracker.md
│   ├── project-overview.md
│   ├── ui-registry.md
│   ├── ui-rules.md
│   ├── ui-rules-old.md       # Previous version of UI rules (reference only)
│   ├── ui-tokens.md
│   └── ui-tokens-old.md      # Previous version of UI tokens (reference only)
├── .gitignore
├── AGENTS.md
├── CLAUDE.md
└── README.md
```

---

## What Each File Does

### Root

| File         | Purpose                                                                                                                                                               |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `AGENTS.md`  | The AI’s entry point and core rules. Tells the agent which context files to read (and in what order), lists non-negotiable rules, and points to the available skills. |
| `CLAUDE.md`  | Thin shim for Claude Code; points at `AGENTS.md` so Claude picks up the same rules automatically.                                                                     |
| `.gitignore` | Standard ignores (node_modules, env files, build output, OS junk, etc.).                                                                                              |
| `README.md`  | This file — how the kit works and how to use it.                                                                                                                      |

### Skills (`.agents/skills/`)

| Skill       | Command                                | Purpose                                                                                                                                                            |
| ----------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `architect` | `/architect`                           | Think through a complex feature before coding. Aligns language, surfaces decisions, and produces an implementation plan you confirm first.                         |
| `imprint`   | `/imprint`                             | After any new UI component, extract visual patterns and save them to `context/ui-registry.md` so later components stay consistent. Also supports `/imprint audit`. |
| `review`    | `/review`                              | After a feature, check plan alignment, architecture/design compliance, and production readiness. Reports issues; you decide what to fix.                           |
| `recover`   | `/recover`                             | When something breaks after a failed fix, diagnose the failure mode (targeted fix vs hard reset vs full rethink) before more prompting.                            |
| `remember`  | `/remember save` · `/remember restore` | Save session state to `memory.md` at the end of a multi-session feature, or restore it at the start of the next session.                                           |

### Context (`context/`)

| File / folder                          | Purpose                                                                                                          |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `project-overview.md`                  | High-level product brief: what you’re building, problem, pages, flows, in/out of scope. Fill once per project.   |
| `architecture.md`                      | System blueprint — layers, data flow, boundaries. Keeps the AI aligned with intended structure.                  |
| `build-plan.md`                        | Master ordered task list. The AI works through it and marks items done.                                          |
| `code-standards.md`                    | Concrete coding conventions for the current stack (naming, TypeScript, framework rules, testing).                |
| `ui-tokens.md`                         | Design tokens: colours, fonts, spacing, shadows, breakpoints. Single source of visual truth.                     |
| `ui-rules.md`                          | When to use which patterns (cards, max-widths, mobile, a11y). Complements tokens with behavioural rules.         |
| `ui-registry.md`                       | Live catalogue of reusable components and their visual patterns. Updated via `/imprint` after each UI component. |
| `library-docs.md`                      | Project-specific notes and safe usage patterns for third-party libraries. Reduces API hallucination.             |
| `progress-tracker.md`                  | Live status table the AI updates after each task so you always know what’s done.                                 |
| `designs/`                             | Drop current design screenshots here for vision-capable agents.                                                  |
| `designs-old/`                         | Archived screenshots from earlier iterations.                                                                    |
| `ui-rules-old.md` / `ui-tokens-old.md` | Previous token/rule snapshots kept for reference; not used as live source of truth.                              |

---

## Usage

### For Claude Code (auto-discovers skills)

```bash
npx skills add Nierowheezy/ai-dev-kit
```

Claude Code loads `AGENTS.md` / `CLAUDE.md` and the skills under `.agents/skills/`.

### For any other AI agent (Cursor, Codex, OpenCode, Grok, etc.)

```bash
npx degit Nierowheezy/ai-dev-kit my-project/ai-dev-kit
```

Or copy the kit into your repo root so paths stay as `context/` and `.agents/skills/`.

At the start of every session, tell your AI something like:

> Read `AGENTS.md`, then every file under `context/` in the order listed there. Follow `build-plan.md` task by task. Adhere to all rules and use the skills when appropriate.

The kit is plain Markdown — no proprietary formats, no tool-specific magic.

---

## The Build Workflow

**1. Initialise a new project**

```bash
npx degit Nierowheezy/ai-dev-kit my-project/ai-dev-kit
cd my-project
```

**2. Fill project-specific context**

- Edit `context/project-overview.md` with what you’re building.
- Sketch the system in `context/architecture.md`.
- Optionally drop screenshots into `context/designs/`.
- Trim or expand `context/code-standards.md` for your stack.

**3. Generate a build plan**

> Based on `project-overview.md` and `architecture.md`, generate an ordered, atomic task list and save it in `build-plan.md`.

**4. Architect before complex work**

For non-trivial features:

> `/architect` — think through the feature, align on language, and confirm a plan before coding.

**5. Execute the loop**

Pick the next task in `build-plan.md`:

> Implement the next open task. Follow `AGENTS.md` and `code-standards.md`. Update `progress-tracker.md` when done.

The AI should:

- Read the required context files
- Write code that matches your standards
- Run `/imprint` after new UI components
- Register components in `ui-registry.md`
- Mark tasks complete in `progress-tracker.md`

**6. Review**

> `/review` — check plan alignment, system integrity, and production readiness before shipping or moving on.

**7. Recover if stuck**

If a fix fails once and the same problem persists:

> `/recover` — diagnose failure mode, then target fix, hard reset, or rethink.

**8. Remember across sessions**

- End of session: `/remember save` → writes `memory.md`
- Start of next session: `/remember restore`

**9. Refine the kit**

If the AI makes a mistake, don’t only fix it in chat — update the relevant `.md` file so it never happens again (e.g. clarify a token in `ui-tokens.md`).

---

## Keeping It Up to Date

- Add new skills under `.agents/skills/<name>/SKILL.md` when you spot a repeating workflow.
- Archive old designs into `context/designs-old/`.
- Override any `context/` file per project — the repo only ships defaults/templates.
- Commit and tag releases (`v1.0`, `v1.1`) so you can track what worked.

---

## Pro Tips

- **Atomic tasks** — “Build dashboard” is too vague. Prefer “Dashboard layout shell”, “Stats card”, “Wire stats to API”.
- **Vision + text** — If the agent supports images, put screenshots in `context/designs/`.
- **Pin critical rules** — Put non-negotiables in `AGENTS.md` (e.g. never hardcode hex; always use design tokens).
- **Review often** — Don’t let the AI run ten tasks unchecked; small drift compounds.
- **Use skills on purpose** — `/architect` before complex features, `/imprint` after UI, `/review` before demos, `/recover` after failed fixes, `/remember` between sessions.

---

## Tech Stack Adaptation

The kit is stack-agnostic. Customise:

- `context/code-standards.md` for your framework and language
- `context/library-docs.md` for the libraries you actually use
- `context/ui-tokens.md` / `context/ui-rules.md` for your design system

Delete or ignore sections that don’t apply. The AI follows what remains.

---

## Credits

Built by [Nierowheezy](https://github.com/Nierowheezy).  
Inspired by the [Anthropic Skills specification](https://docs.anthropic.com/en/docs/claude-code/skills) and a desire to make AI-assisted coding predictable, repeatable, and actually enjoyable.

---

**Now go build something great — with your AI sidekick perfectly in sync.**
