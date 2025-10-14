# Symphony CSS v0.1 - Quick Reference Guide

## 🎯 Grid System (CORRECTED)

### Basic Grid
```html
<div class="symphony-grid">
  <div class="symphony-grid__col--6">Half width</div>
  <div class="symphony-grid__col--6">Half width</div>
</div>
```

### Column Spans (BEM Naming)
- `.symphony-grid__col--1` through `.symphony-grid__col--12`
- At 1200px: Each column = 78px, Gap = 24px
- Mathematical formula: (12 × 78px) + (11 × 24px) = 1200px

### Legacy Support
- `.symphony-col-span-1` through `.symphony-col-span-12` still work

---

## 📝 Typography (CORRECTED)

### Heading Sizes
```css
H1: 74px (4.625rem) - letter-spacing: 1%
H2: 42px (2.625rem) - letter-spacing: 0%
H3: 30px (1.875rem)
H4: 24px (1.5rem)
H5: 20px (1.25rem)
H6: 18px (1.125rem)
```

### Body Text Sizes
```css
14px: --symphony-font-size-sm
16px: --symphony-font-size-base
18px: --symphony-font-size-lg
20px: --symphony-font-size-xl
```

### Fonts
- **Body:** Mona Sans (Regular 400)
- **Headings:** Inter Display (Semibold 600)

---

## 🎨 Buttons (CORRECTED)

### Button Specifications
```css
Padding: 32px horizontal × 12px vertical
Font: 14px Mona Sans Regular
Letter spacing: 0%
Default: Pill shape (50px radius)
```

### Usage
```html
<!-- Default pill button -->
<button class="symphony-button symphony-button--primary">
  Pill Button
</button>

<!-- Rounded button (10px radius) -->
<button class="symphony-button symphony-button--primary symphony-button--rounded">
  Rounded Button
</button>

<!-- Semantic buttons (auto-styled) -->
<button>Auto-styled button</button>
```

### Variants
- `.symphony-button--primary`
- `.symphony-button--secondary`
- `.symphony-button--success`
- `.symphony-button--warning`
- `.symphony-button--danger`
- `.symphony-button--outline`
- `.symphony-button--ghost`

### Border Radius
- `.symphony-button--pill` - 50px radius (default)
- `.symphony-button--rounded` - 10px radius

---

## 🌙 Dark Theme (CORRECTED)

### Exact Hex Colors
```css
Background: #020410
Primary: #0055FE
Text (titles): #FFFFFF
Text (body): #CBD2D9
Surface: #0A0F1E
```

### Usage
```html
<!-- Automatic (follows system preference) -->
<body>...</body>

<!-- Manual dark mode -->
<body class="symphony-dark">...</body>

<!-- Or use data attribute -->
<body data-theme="dark">...</body>
```

---

## 🔧 Modern CSS 2025 Features

### Container Queries
```css
/* Containers have container-type: inline-size */
.symphony-container { container-name: symphony; }
.symphony-card { container-name: card; }

/* Example usage */
@container card (min-width: 400px) {
  .symphony-card__body {
    padding: var(--symphony-spacing-8);
  }
}
```

### Text Wrap Balance
```css
/* Automatically applied to h1, h2, h3 */
h1, h2, h3 {
  text-wrap: balance;
}
```

---

## 📐 Grid Mathematics Verification

### At 1200px Viewport
```
12 columns × 78px = 936px
11 gutters × 24px = 264px
Total: 936px + 264px = 1200px ✓

Example: 6-column span
6 columns × 78px = 468px
5 internal gaps × 24px = 120px
Total width: 468px + 120px = 588px
```

### Responsive Behavior
- **≥1200px:** Fixed 78px columns
- **<1200px:** Fluid 1fr columns with 24px padding
- **<768px:** Single column layout

---

## 🎯 Common Patterns

### Hero Section
```html
<section class="symphony-section">
  <div class="symphony-container">
    <h1>74px heading with 1% letter-spacing</h1>
    <p class="symphony-lead">20px lead text</p>
    <button class="symphony-button symphony-button--primary">
      Get Started
    </button>
  </div>
</section>
```

### Grid Layout
```html
<div class="symphony-grid">
  <div class="symphony-grid__col--4">1/3 width</div>
  <div class="symphony-grid__col--4">1/3 width</div>
  <div class="symphony-grid__col--4">1/3 width</div>
</div>
```

### Card with Container Query
```html
<div class="symphony-card">
  <div class="symphony-card__body">
    <!-- Padding increases to 32px when card is ≥400px wide -->
    Content
  </div>
</div>
```

---

## 🔍 CSS Variables Reference

### Typography
```css
--symphony-font-size-h1: 4.625rem;     /* 74px */
--symphony-font-size-h2: 2.625rem;     /* 42px */
--symphony-letter-spacing-h1: 0.01em;  /* 1% */
--symphony-letter-spacing-default: 0;  /* 0% */
```

### Buttons
```css
--symphony-button-padding-y: 0.75rem;          /* 12px */
--symphony-button-padding-x: 2rem;             /* 32px */
--symphony-button-font-size: 0.875rem;         /* 14px */
--symphony-button-radius-pill: 3.125rem;       /* 50px */
--symphony-button-radius-rounded: 0.625rem;    /* 10px */
```

### Dark Theme
```css
--symphony-background: #020410;
--symphony-primary: #0055FE;
--symphony-text: #FFFFFF;
--symphony-text-body: #CBD2D9;
--symphony-surface: #0A0F1E;
```

---

## ⚠️ Breaking Changes from Initial Version

### Grid Classes
- **OLD:** `.symphony-grid--cols-12` (fluid 1fr)
- **NEW:** `.symphony-grid` (fixed 78px columns at desktop)
- **Column spans:** Use `.symphony-grid__col--6` instead of `.symphony-col-span-6`

### Typography Variables
- **OLD:** `--symphony-font-size-4xl` (51px)
- **NEW:** `--symphony-font-size-h1` (74px)

### Button Padding
- **OLD:** 24px horizontal
- **NEW:** 32px horizontal

### Button Border Radius
- **OLD:** 8px default
- **NEW:** 50px pill (default), 10px rounded (variant)

---

## 📚 Documentation

- Full docs: `docs/index.html`
- Validation report: `VALIDATION_SUCCESS_REPORT.md`
- Examples: `docs/examples/landing-page.html`
- Contributing: `CONTRIBUTING.md`

---

**Symphony CSS v0.1 - Built with precision for the modern web** 🎵
