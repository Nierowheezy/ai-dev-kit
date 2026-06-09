You're right — that README was too light. Let’s write a thorough, detailed one that fully explains your kit so anyone (including future you) understands it instantly.

---

## `README.md` – complete, detailed

```markdown
# AI Dev Kit

> My personal, battle‑tested standard for building software with any AI agent — Claude Code, Cursor, Codex, OpenCode, Antigravity, and more.

It’s a **stack‑agnostic, tool‑agnostic** collection of rules, skills, and memory files.  
You drop it into a project, give your AI a single instruction, and it knows **exactly** how you work.

---

## 🤔 Why This Exists

AI coding assistants are powerful but forgetful. Without a shared “brain”, you waste time re‑explaining:
- The tech stack conventions
- Design tokens and UI rules
- The task order and progress
- Which components already exist

This kit solves that. It’s a **permanent, portable operating manual** for your AI, so every session starts with total context — no repetition, no guessing, no drift.

---

## 📁 Structure

```
ai-dev-kit/
├── agent.md                  # Global system prompt & universal rules
├── skills/                   # Reusable AI behaviours (Anthropic Skills spec)
│   ├── ui-component.md       # How to build a UI component from scratch
│   ├── db-migration.md       # How to write safe database migrations
│   └── test.md               # How to write and run tests
├── context/                  # Project‑specific memory & templates
│   ├── project-overview.md   # Elevator pitch, users, core features
│   ├── architecture.md       # System components, folder layout, API routes
│   ├── build-plan.md         # Ordered, atomic task list
│   ├── code-standards.md     # Stack‑specific conventions (React, Vue, Node…)
│   ├── ui-tokens.md          # Design tokens (colours, spacing, typography)
│   ├── ui-rules.md           # Layout rules, responsive behaviour, a11y
│   ├── ui-registry.md        # Catalogue of existing reusable components
│   ├── library-docs.md       # Curated usage snippets for installed libraries
│   ├── progress-tracker.md   # Live status of every task
│   └── designs/              # Screenshots / Figma exports (optional)
└── README.md                 # You’re reading it
```

### What each file does

| File | Purpose |
|------|---------|
| `agent.md` | The AI’s “personality” and core rules. It instructs the AI to read all other files, never guess, follow standards, and use the skills. |
| `skills/ui-component.md` | A checklist the AI runs when asked `@ui-component`. Ensures consistency: design tokens, states, a11y, registry update. |
| `skills/db-migration.md` | Safe schema change workflow: check architecture, write up/down, update docs, test. |
| `skills/test.md` | Forces the AI to write tests after each feature, including accessibility checks. |
| `context/project-overview.md` | High‑level brief. Fill this once per project. |
| `context/architecture.md` | Blueprint of the system. Keeps the AI aligned with your intended structure. |
| `context/build-plan.md` | The master task list. The AI follows this sequentially and marks items done. |
| `context/code-standards.md` | Concrete coding conventions for your current stack. Has sections for React, Vue, Node, and testing. |
| `context/ui-tokens.md` | Single source of design truth: colours, fonts, spacing, shadows, breakpoints. |
| `context/ui-rules.md` | When to use a card vs. a custom border, max‑widths, mobile behaviour, accessibility rules. |
| `context/ui-registry.md` | Auto‑updated catalogue of every reusable component. Prevents duplication. |
| `context/library-docs.md` | Copy‑paste‑ready snippets from your actual dependencies. Stops the AI from hallucinating APIs. |
| `context/progress-tracker.md` | A live table the AI updates after each task, so you always know what’s done. |

---

## 🚀 Usage — One‑Command Install

### For Claude Code (auto‑discovers skills)
```bash
npx skills add Nierowheezy/ai-dev-kit
```
Claude Code will automatically load `agent.md` and all skills inside `skills/`.

### For any other AI agent (Cursor, Codex, OpenCode, etc.)
```bash
npx degit Nierowheezy/ai-dev-kit/context my-project/ai-context
```
Then, at the start of every session, tell your AI:
> *“Read every file inside `ai-context/`. Follow `build-plan.md` task by task. Adhere to all rules and use the skills.”*

This works because the kit is just Markdown — no proprietary formats, no tool‑specific magic.

---

## 🧠 The Build Workflow (Step‑by‑Step)

**1. Initialise a new project**
```bash
npx degit Nierowheezy/ai-dev-kit/context my-project/ai-context
cd my-project
```

**2. Fill the project‑specific context**
- Open `ai-context/project-overview.md` and describe what you’re building.
- Open `ai-context/architecture.md` and sketch the system.
- (Optional) Drop screenshots into `ai-context/designs/`.

**3. Generate a build plan**
Ask your AI:
> *“Based on `project-overview.md` and `architecture.md`, generate an ordered, atomic task list and save it in `build-plan.md`.”*

**4. Start the execution loop**
Pick the first task in `build-plan.md` and instruct the AI:
> *“Implement task 1.1. Follow `agent.md` and `code-standards.md`. Update `progress-tracker.md` when done.”*

The AI will:
- Read all context files
- Write code matching your standards
- Use the appropriate skill if needed (e.g., `@ui-component`)
- Register any new component in `ui-registry.md`
- Mark the task as ✅ Complete

**5. Review & refine**
- Test the code.
- If the AI made a mistake, **don’t just fix it in chat** — update the relevant `.md` file so it never happens again.  
  (e.g., if it used the wrong spacing, clarify the token in `ui-tokens.md`)

**6. Repeat** until all tasks are checked off.

---

## 🔄 Keeping It Up‑to‑Date

Your kit is versioned. Over time:
- Add new skills to `skills/` when you spot a repeating pattern.
- Archive old designs into `designs-old/` so the AI can still reference them if needed.
- When you start a new project, you can override any `context/` file — the repo just gives you the default templates.
- Commit and tag releases (`v1.0`, `v1.1`) so you can track what worked best.

---

## 💡 Pro Tips

- **Small, atomic tasks** – A task like “Build dashboard” is too vague. Break it down into “Dashboard layout shell”, “Stats card component”, “Connect stats to API”.
- **Vision + text** – If your AI supports images, always include a screenshot in `designs/`. It matches details you’d need paragraphs to describe.
- **Pin critical rules** – In `agent.md`, add lines like “Never use inline styles – always Tailwind classes” to prevent common mistakes.
- **Review early, review often** – Don’t let the AI code 10 tasks unchecked. A tiny error can cascade.

---

## 🔧 Tech Stack Adaptation

The kit is designed to work with any stack. Inside `code-standards.md`, you’ll find separate sections for:
- React / Next.js
- Vue / Nuxt
- Node / NestJS
- Testing (Vitest/Jest/Playwright)

When you start a project, just **delete the sections that don’t apply** and expand your stack’s section. The AI will follow what remains.

---

## 🤝 Credits & Inspiration

Built by [Nierowheezy](https://github.com/Nierowheezy).  
Inspired by the [Anthropic Skills specification](https://docs.anthropic.com/en/docs/claude-code/skills) and a desire to make AI‑assisted coding predictable, repeatable, and actually enjoyable.

---

**Now go build something great — with your AI sidekick perfectly in sync.**
```


