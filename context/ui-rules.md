# UI Rules

Concise rules for building the DevHunter AI interface. Design assets are the source of truth. Follow these rules to maintain consistency across all pages and components.

---

# Font

Always use Geist as the primary typeface throughout the application.

```typescript
import { Geist } from "next/font/google";

const geist = Geist({
  subsets: ["latin"],
  variable: "--font-sans",
});
```

Apply the font variable class to the root `<html>` element.

Never use system fonts.

---

# Theme

DevHunter AI is a dark-first application.

Core visual principles:

- Obsidian surfaces
- Emerald accents
- Minimal visual noise
- High information density
- Soft rounded geometry
- Tonal layering instead of heavy shadows

The interface should feel like a premium developer workspace rather than a marketing website.

---

# Layout

Desktop:

- Max width: 1280px
- Centered content
- 24px gutters
- 64px horizontal page margin

Tablet:

- 20px gutters

Mobile:

- 20px side margins

Spacing system:

- Base unit: 4px
- Small gap: 8px
- Medium gap: 12px
- Standard gap: 24px
- Large section spacing: 80px–120px

---

# Navbar

Top navigation only.

```css
height: 64px;
background: var(--surface);
border-bottom: 1px solid var(--outline-variant);
```

Navigation items:

Active:

```css
color: var(--primary);
font-weight: 500;
font-size: 14px;
```

Inactive:

```css
color: var(--on-surface-variant);
font-weight: 500;
font-size: 14px;
```

Hover:

```css
color: var(--primary-fixed);
```

No underlines.

---

# Surface Levels

Level 0 — Application Background

```css
background: var(--background);
```

Level 1 — Cards / Panels

```css
background: var(--surface-container-low);
border: 1px solid var(--outline-variant);
border-radius: 16px;
```

Level 2 — Modals / Popovers

```css
background: var(--surface-container);
border: 1px solid var(--outline-variant);
backdrop-filter: blur(20px);
border-radius: 16px;
```

Never use bright backgrounds.

Never use white cards.

---

# Cards

All content sections should live inside cards.

```css
background: var(--surface-container-low);
border: 1px solid var(--outline-variant);
border-radius: 16px;
padding: 24px;
```

Optional hover:

```css
background: var(--surface-container);
transition: all 150ms ease;
```

---

# Typography Hierarchy

Section Titles

```css
font-size: 20px;
font-weight: 600;
line-height: 28px;
color: var(--on-surface);
```

Card Titles

```css
font-size: 16px;
font-weight: 600;
line-height: 24px;
color: var(--on-surface);
```

Primary Content

```css
font-size: 14px;
font-weight: 400;
line-height: 20px;
color: var(--on-surface);
```

Secondary Content

```css
font-size: 14px;
font-weight: 400;
line-height: 20px;
color: var(--on-surface-variant);
```

Labels

```css
font-size: 12px;
font-weight: 500;
line-height: 16px;
letter-spacing: 0.05em;
text-transform: uppercase;
color: var(--on-surface-variant);
```

Dashboard metrics:

```css
font-size: 48px;
font-weight: 700;
line-height: 56px;
color: var(--on-surface);
```

---

# Buttons

Primary Button

```css
background: var(--primary);
color: var(--on-primary);
border-radius: 8px;
padding: 8px 16px;
font-size: 14px;
font-weight: 500;
```

Hover:

```css
background: var(--primary-fixed);
```

Secondary Button

```css
background: transparent;
border: 1px solid var(--primary);
color: var(--primary);
border-radius: 8px;
padding: 8px 16px;
```

Hover:

```css
background: rgba(78, 222, 163, 0.08);
```

Danger Button

```css
background: var(--error-container);
color: var(--on-error-container);
```

---

# Inputs

```css
background: var(--surface-container-lowest);
border: 1px solid var(--outline-variant);
border-radius: 8px;
padding: 8px 12px;
font-size: 14px;
color: var(--on-surface);
```

Placeholder

```css
color: var(--on-surface-variant);
```

Focus State

```css
border-color: var(--primary);
box-shadow: 0 0 0 2px rgba(78, 222, 163, 0.15);
```

---

# Tables

Headers

```css
font-size: 12px;
font-weight: 500;
text-transform: uppercase;
letter-spacing: 0.05em;
color: var(--on-surface-variant);
```

Rows

```css
border-bottom: 1px solid var(--outline-variant);
```

Text

```css
font-size: 14px;
color: var(--on-surface);
```

Hover

```css
background: var(--surface-container);
```

Never use zebra striping.

---

# Tags & Chips

Use pill styling.

```css
border-radius: 9999px;
padding: 4px 10px;
font-size: 12px;
font-weight: 500;
```

Success

```css
background: var(--secondary-container);
color: var(--secondary-fixed);
```

Primary

```css
background: rgba(78, 222, 163, 0.12);
color: var(--primary);
```

---

# Progress Bars

Track

```css
height: 4px;
border-radius: 9999px;
background: var(--surface-variant);
```

Fill

Excellent

```css
background: var(--primary);
```

Good

```css
background: var(--secondary);
```

Warning

```css
background: var(--tertiary-container);
```

---

# Empty States

Keep minimal.

Structure:

- Icon
- Title
- Short description
- CTA if applicable

Description color:

```css
color: var(--on-surface-variant);
```

---

# Glassmorphism Rules

Allowed only for:

- Command palette
- Modals
- Floating panels
- AI assistant overlays

Requirements:

```css
backdrop-filter: blur(20px);
background: rgba(32, 31, 31, 0.8);
border: 1px solid rgba(255, 255, 255, 0.06);
```

Never use glassmorphism for every card.

---

# Tailwind v4 Rules

All colors must come from theme tokens.

Never use:

```html
bg-green-500 text-gray-400 border-zinc-700
```

Use project tokens only.

All new colors must be defined inside:

```css
@theme;
```

Never use tailwind.config.ts for colors.

---

# Do Nots

- Never use white backgrounds
- Never use gradients as primary backgrounds
- Never use pure black (#000000)
- Never use more than one accent color family
- Never use heavy drop shadows
- Never use neon glow effects
- Never use fixed-position UI unless absolutely necessary
- Never expose raw API or system errors
- Never use default Tailwind colors
- Never mix font families
- Never use glassmorphism everywhere
- Never break the dark-theme hierarchy
