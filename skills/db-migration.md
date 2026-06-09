# db-migration skill

When a task requires a database schema change:

1. Check `context/architecture.md` for current schema.
2. Write a migration file with `up` and `down` steps.
3. Use safe operations (IF NOT EXISTS, transactions).
4. Update `context/architecture.md` schema section.
5. Test the migration against a local DB.
