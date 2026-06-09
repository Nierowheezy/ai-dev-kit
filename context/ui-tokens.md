# UI Tokens

<!-- Design tokens – the single source of truth for all visual values. -->

## Colors

- `--color-primary: #3B82F6`
- `--color-primary-hover: #2563EB`
- `--color-secondary: #10B981`
- `--color-background: #FFFFFF`
- `--color-surface: #F9FAFB`
- `--color-text: #111827`
- `--color-text-muted: #6B7280`
- `--color-border: #E5E7EB`

## Typography

- Font family: `Inter, system-ui, sans-serif`
- Scale (px): `12, 14, 16, 20, 24, 32, 40`
- Weights: `400, 500, 600, 700`

## Spacing & Sizing

- Base unit: `4px`
- Scale: `4, 8, 12, 16, 24, 32, 48, 64, 96`

## Shadows

- `sm`: `0 1px 2px rgba(0,0,0,0.05)`
- `md`: `0 4px 6px rgba(0,0,0,0.1)`
- `lg`: `0 10px 15px rgba(0,0,0,0.1)`

## Breakpoints

- `sm: 640px`, `md: 768px`, `lg: 1024px`, `xl: 1280px`, `2xl: 1536px`

````

To write it directly from the terminal:

```bash
cat > context/ui-tokens.md << 'ENDOFFILE'
# UI Tokens

<!-- Design tokens – the single source of truth for all visual values. -->

## Colors
- `--color-primary: #3B82F6`
- `--color-primary-hover: #2563EB`
- `--color-secondary: #10B981`
- `--color-background: #FFFFFF`
- `--color-surface: #F9FAFB`
- `--color-text: #111827`
- `--color-text-muted: #6B7280`
- `--color-border: #E5E7EB`

## Typography
- Font family: `Inter, system-ui, sans-serif`
- Scale (px): `12, 14, 16, 20, 24, 32, 40`
- Weights: `400, 500, 600, 700`

## Spacing & Sizing
- Base unit: `4px`
- Scale: `4, 8, 12, 16, 24, 32, 48, 64, 96`

## Shadows
- `sm`: `0 1px 2px rgba(0,0,0,0.05)`
- `md`: `0 4px 6px rgba(0,0,0,0.1)`
- `lg`: `0 10px 15px rgba(0,0,0,0.1)`

## Breakpoints
- `sm: 640px`, `md: 768px`, `lg: 1024px`, `xl: 1280px`, `2xl: 1536px`

````
