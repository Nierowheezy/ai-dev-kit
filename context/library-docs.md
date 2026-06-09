# Library Docs

<!-- Curated snippets from libraries we actually use. Prevents AI guesswork. -->

## Validation – Zod

```ts
import { z } from "zod";
const userSchema = z.object({
  email: z.string().email(),
  password: z.string().min(8),
});
```

````

## Internationalisation – next-intl

```tsx
import { useTranslations } from "next-intl";
const t = useTranslations("Home");
<h1>{t("title")}</h1>;
```

## Date Handling – date-fns

```ts
import { format, parseISO } from "date-fns";
format(parseISO(dateStr), "MMMM dd, yyyy");
```

<!-- Add more libraries as you install them. Keep snippets minimal and copy‑paste ready. -->

````

To write it directly from the terminal:

````bash
cat > context/library-docs.md << 'ENDOFFILE'
# Library Docs

<!-- Curated snippets from libraries we actually use. Prevents AI guesswork. -->

## Validation – Zod
```ts
import { z } from 'zod';
const userSchema = z.object({
  email: z.string().email(),
  password: z.string().min(8),
});
````

## Internationalisation – next-intl

```tsx
import { useTranslations } from "next-intl";
const t = useTranslations("Home");
<h1>{t("title")}</h1>;
```

## Date Handling – date-fns

```ts
import { format, parseISO } from "date-fns";
format(parseISO(dateStr), "MMMM dd, yyyy");
```

<!-- Add more libraries as you install them. Keep snippets minimal and copy‑paste ready. -->
