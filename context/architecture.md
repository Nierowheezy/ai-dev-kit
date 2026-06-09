# Architecture

<!-- High‑level blueprint of the system. Fill this in for each project. -->

## System Components

- **Frontend:** <!-- e.g. Next.js 14, Vue 3 -->
- **Backend:** <!-- e.g. NestJS, Supabase, Express -->
- **Database:** <!-- e.g. PostgreSQL, MongoDB -->
- **Hosting:** <!-- e.g. Vercel, Railway, AWS -->

## Directory Structure (conceptual)

src/
components/ # Reusable UI pieces
pages/ # Route-level views (or app/ for Next.js)
services/ # API calls, business logic
hooks/ # Custom hooks / composables
utils/ # Pure helpers
styles/ # Global styles, tokens

## Database Schema (sketch)

- `users` – id, email, name, role…
- `posts` – id, title, body, user_id (FK → users)…

## API Routes (if applicable)

| Method | Endpoint          | Description  |
| ------ | ----------------- | ------------ |
| GET    | `/api/users`      | List users   |
| POST   | `/api/auth/login` | Authenticate |

````

---

**To save it directly** from the terminal (so the shell writes the exact bytes and the code block doesn't break), run:

```bash
cat > context/architecture.md << 'ENDOFFILE'
# Architecture

<!-- High‑level blueprint of the system. Fill this in for each project. -->

## System Components
- **Frontend:** <!-- e.g. Next.js 14, Vue 3 -->
- **Backend:** <!-- e.g. NestJS, Supabase, Express -->
- **Database:** <!-- e.g. PostgreSQL, MongoDB -->
- **Hosting:** <!-- e.g. Vercel, Railway, AWS -->

## Directory Structure (conceptual)
src/
  components/    # Reusable UI pieces
  pages/         # Route-level views (or app/ for Next.js)
  services/      # API calls, business logic
  hooks/         # Custom hooks / composables
  utils/         # Pure helpers
  styles/        # Global styles, tokens

## Database Schema (sketch)
- `users` – id, email, name, role…
- `posts` – id, title, body, user_id (FK → users)…

## API Routes (if applicable)
| Method | Endpoint           | Description       |
|--------|--------------------|-------------------|
| GET    | `/api/users`       | List users        |
| POST   | `/api/auth/login`  | Authenticate      |
````
