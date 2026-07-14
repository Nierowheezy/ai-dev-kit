# UI Tokens — DevHunter AI

Design tokens for DevHunter AI. All colors, typography, spacing, and component values are extracted from the official design system.

These tokens are the **single source of truth**. Never hardcode values or use raw Tailwind color classes.

---

# How to Use

This project uses **Tailwind CSS v4** with tokens defined via `@theme` in `app/globals.css`.

No `tailwind.config.ts` is used for colors.

Tailwind automatically generates utilities from tokens:

- `--color-primary` → `bg-primary`, `text-primary`, `border-primary`
- `--color-surface` → `bg-surface-container`, `text-on-surface`

---

## Correct Usage

```tsx
className = "bg-surface-container text-on-surface border-outline-variant";
```

```tsx
style={{ color: "var(--color-on-surface)" }}
```

---

## Never Do This

```tsx
className = "bg-[#131313] text-[#e5e2e1]";
className = "bg-gray-900 text-white";
className = "bg-green-500";
```

---

# globals.css — Complete Token Definition

```css
@import "tailwindcss";

@theme {
  /* Font */
  --font-sans: "Geist", sans-serif;

  /* Backgrounds */
  --color-background: #0a0a0a;

  /* Surfaces (Tonal Layers) */
  --color-surface: #171717;
  --color-surface-dim: #131313;

  --color-surface-container-lowest: #0e0e0e;
  --color-surface-container-low: #1c1b1b;
  --color-surface-container: #201f1f;
  --color-surface-container-high: #2a2a2a;
  --color-surface-container-highest: #353534;

  /* Text */
  --color-on-surface: #e5e2e1;
  --color-on-surface-variant: #bbcabf;

  --color-inverse-surface: #e5e2e1;
  --color-inverse-on-surface: #313030;

  /* Borders */
  --color-outline: #86948a;
  --color-outline-variant: #3c4a42;

  /* Brand / Primary (Emerald) */
  --color-primary: #4edea3;
  --color-primary-container: #10b981;
  --color-on-primary: #003824;
  --color-on-primary-container: #00422b;
  --color-surface-tint: #4edea3;

  /* Secondary */
  --color-secondary: #95d3ba;
  --color-secondary-container: #0b513d;
  --color-on-secondary: #003829;
  --color-on-secondary-container: #83c2a9;

  /* Tertiary (soft accent red/pink) */
  --color-tertiary: #ffb3af;
  --color-tertiary-container: #fc7c78;
  --color-on-tertiary: #650911;
  --color-on-tertiary-container: #711419;

  /* Error */
  --color-error: #ffb4ab;
  --color-error-container: #93000a;
  --color-on-error: #690005;
  --color-on-error-container: #ffdad6;

  /* Inverse Primary */
  --color-inverse-primary: #006c49;

  /* Fixed Tokens */
  --color-primary-fixed: #6ffbbe;
  --color-primary-fixed-dim: #4edea3;
  --color-on-primary-fixed: #002113;
  --color-on-primary-fixed-variant: #005236;

  --color-secondary-fixed: #b0f0d6;
  --color-secondary-fixed-dim: #95d3ba;
  --color-on-secondary-fixed: #002117;
  --color-on-secondary-fixed-variant: #0b513d;

  --color-tertiary-fixed: #ffdad7;
  --color-tertiary-fixed-dim: #ffb3af;
  --color-on-tertiary-fixed: #410005;
  --color-on-tertiary-fixed-variant: #842225;

  /* Utility */
  --color-overlay: rgba(0, 0, 0, 0.6);

  /* Surface Tint / Glow */
  --color-surface-glow: rgba(78, 222, 163, 0.12);

  /* Radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 16px;
  --radius-xl: 24px;
  --radius-full: 9999px;
}
```

---

# Color Usage Guide

## Layout

| Element          | Token                      |
| ---------------- | -------------------------- |
| Page background  | `bg-background`            |
| Card surface     | `bg-surface-container-low` |
| Elevated surface | `bg-surface-container`     |
| Borders          | `border-outline-variant`   |

---

## Text

| Usage          | Token                     |
| -------------- | ------------------------- |
| Primary text   | `text-on-surface`         |
| Secondary text | `text-on-surface-variant` |
| Muted labels   | `text-outline`            |

---

## Primary (Emerald System)

Used for:

- Primary actions
- Active states
- Highlights
- Data emphasis

| Element           | Token             |
| ----------------- | ----------------- |
| Button background | `bg-primary`      |
| Button text       | `text-on-primary` |
| Accent glow       | `bg-surface-glow` |

---

## Status Colors

| Type    | Token                                     |
| ------- | ----------------------------------------- |
| Success | `bg-secondary-container / text-secondary` |
| Warning | `bg-tertiary-container`                   |
| Error   | `bg-error-container`                      |

---

# Typography

All typography uses **Geist**.

| Element     | Size | Weight | Color              |
| ----------- | ---- | ------ | ------------------ |
| Headline XL | 48px | 700    | on-surface         |
| Headline LG | 32px | 600    | on-surface         |
| Headline MD | 20px | 600    | on-surface         |
| Body LG     | 18px | 400    | on-surface         |
| Body MD     | 16px | 400    | on-surface         |
| Body SM     | 14px | 400    | on-surface-variant |
| Label       | 12px | 500    | on-surface-variant |

---

# Spacing System

Base unit: **4px**

| Token | Value |
| ----- | ----- |
| xs    | 4px   |
| sm    | 8px   |
| md    | 12px  |
| lg    | 16px  |
| xl    | 24px  |
| 2xl   | 32px  |
| 3xl   | 48px  |

Page container max width: **1280px**

---

# Component Tokens

---

## Cards

```css
background: var(--color-surface-container-low);
border: 1px solid var(--color-outline-variant);
border-radius: var(--radius-lg);
padding: 24px;
```

Hover:

```css
background: var(--color-surface-container);
```

---

## Buttons

### Primary

```css
background: var(--color-primary);
color: var(--color-on-primary);
border-radius: var(--radius-md);
padding: 8px 16px;
font-weight: 500;
```

### Secondary

```css
background: transparent;
border: 1px solid var(--color-outline-variant);
color: var(--color-on-surface);
```

### Ghost

```css
background: transparent;
color: var(--color-on-surface-variant);
```

---

## Inputs

```css
background: var(--color-surface-container-lowest);
border: 1px solid var(--color-outline-variant);
border-radius: var(--radius-md);
padding: 8px 12px;
color: var(--color-on-surface);
```

Focus:

```css
border-color: var(--color-primary);
box-shadow: 0 0 0 2px rgba(78, 222, 163, 0.15);
```

---

## Badges

```css
border-radius: var(--radius-full);
padding: 4px 10px;
font-size: 12px;
font-weight: 500;
```

---

## Tables

- No zebra striping
- Row divider: `1px solid var(--color-outline-variant)`
- Hover: `var(--color-surface-container)`

---

## Progress Bars

Track:

```css
background: var(--color-outline-variant);
height: 4px;
border-radius: var(--radius-full);
```

Fill:

- Success: `var(--color-primary)`
- Info: `var(--color-secondary)`
- Warning: `var(--color-tertiary-container)`

---

## Glass / Floating UI (Restricted Use Only)

Allowed only for:

- Modals
- Command palette
- Floating AI panels

```css
backdrop-filter: blur(20px);
background: rgba(32, 31, 31, 0.8);
border: 1px solid rgba(255, 255, 255, 0.06);
```

---

# Invariants

- Never hardcode hex values in components
- Never use Tailwind default colors (`gray`, `green`, `purple`, etc.)
- Never reintroduce light theme tokens
- Always use surface layering instead of shadows for depth
- Primary accent is **#4EDEA3 only**
- Never mix multiple accent systems
- Never use white backgrounds anywhere
- Never break tonal surface hierarchy
