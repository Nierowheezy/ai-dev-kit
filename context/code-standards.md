# Code Standards

## Universal Rules (all stacks)

- Use TypeScript everywhere possible.
- Prefer functions and composition over classes.
- Names: camelCase for variables/functions, PascalCase for components/classes, UPPER_SNAKE for constants.
- Keep files under 200 lines; split if necessary.
- Write JSDoc for public APIs.
- Commit messages: `type: description` (feat, fix, refactor, etc.)

## React / Next.js

- Use functional components with hooks.
- Prefer Server Components unless interactivity is needed.
- Use Tailwind CSS for styling, following `context/ui-tokens.md`.
- State management: Context + useReducer for complex state, avoid Redux unless large scale.
- Props: destructure, provide defaults.

## Vue / Nuxt

- Use Composition API with `<script setup>`.
- Use Tailwind CSS (or tokens if defined).
- Pinia for state management.
- Single-file components; keep templates clean.

## Node / NestJS

- Use NestJS modules, controllers, services.
- DTOs with class-validator.
- Follow repository pattern for data access.
- Use environment variables for config.

## Testing

- Framework: Vitest or Jest (depending on project).
- Component testing: React Testing Library or Vue Test Utils.
- E2E: Playwright (if needed).
