# UI Rules

<!-- Behavioural and layout constraints. The AI must follow these. -->

## Layout

- Max content width: `max-w-6xl` (1152px)
- Standard section padding: `p-6` (24px)
- Mobile navigation: off‑canvas menu triggered by a hamburger icon

## Component Usage

- Group related content in `<Card>` components; avoid custom borders.
- Buttons: always have `hover`, `focus`, and `disabled` states defined.
- Form fields: show inline validation messages below the input.

## Responsive Behaviour

- Sidebar collapses to bottom tab bar or hamburger on screens < `md`.
- Tables become stacked cards on screens < `sm`.
- Images: use `next/image` or `v-img` with lazy loading.

## Accessibility (a11y)

- All images must have descriptive `alt` text.
- Colour contrast ratio ≥ 4.5:1 for text.
- Interactive elements must be focusable and operable via keyboard.
- Use semantic HTML (`<nav>`, `<main>`, `<button>`, `<form>`).

````

To write it directly from the terminal:

```bash
cat > context/ui-rules.md << 'ENDOFFILE'
# UI Rules

<!-- Behavioural and layout constraints. The AI must follow these. -->

## Layout
- Max content width: `max-w-6xl` (1152px)
- Standard section padding: `p-6` (24px)
- Mobile navigation: off‑canvas menu triggered by a hamburger icon

## Component Usage
- Group related content in `<Card>` components; avoid custom borders.
- Buttons: always have `hover`, `focus`, and `disabled` states defined.
- Form fields: show inline validation messages below the input.

## Responsive Behaviour
- Sidebar collapses to bottom tab bar or hamburger on screens < `md`.
- Tables become stacked cards on screens < `sm`.
- Images: use `next/image` or `v-img` with lazy loading.

## Accessibility (a11y)
- All images must have descriptive `alt` text.
- Colour contrast ratio ≥ 4.5:1 for text.
- Interactive elements must be focusable and operable via keyboard.
- Use semantic HTML (`<nav>`, `<main>`, `<button>`, `<form>`).

````
