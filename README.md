# Symphony CSS v0.1.2 - Anthology

A modular, semantic-first CSS framework with modern CSS features.

## ✨ Features

- **🎯 CSS Cascade Layers** - Predictable specificity control with `@layer`
- **🎨 CSS Custom Properties** - Typed, animatable variables with `@property`
- **🔧 Framework Agnostic** - Works seamlessly with React, Vue, Svelte, or vanilla HTML
- **📦 Modular Architecture** - Import only what you need
- **🎭 BEM Naming** - Clear, maintainable class names
- **🌐 Semantic First** - Style HTML elements directly, minimal classes required
- **🌙 Dark Mode** - Built-in dark mode support
- **📱 Responsive** - Mobile-first responsive design
- **♿ Accessible** - WCAG compliant focus states and form controls

## 📦 Installation

### NPM

```bash
npm install symphonycss
```

### CDN

```html
<link rel="stylesheet" href="path/to/symphony.css">
```

### Download

Download the latest release from the [releases page](https://github.com/your-repo/symphonycss/releases).

## 🚀 Quick Start

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Symphony CSS Example</title>
  <link rel="stylesheet" href="path/to/symphony.css">
</head>
<body>
  <div class="symphony-container">
    <h1>Welcome to Symphony CSS</h1>
    <p class="symphony-lead">A modern CSS framework for the modern web.</p>
    <button class="symphony-button symphony-button--primary">Get Started</button>
  </div>
</body>
</html>
```

## 📚 Documentation

### Core Concepts

#### Cascade Layers

Symphony uses CSS Cascade Layers for predictable specificity:

```css
@layer reset, base, layout, components, utilities;
```

This ensures that utility classes always override component styles, which override base styles.

#### Design Tokens

All design values are stored as CSS Custom Properties:

```css
:root {
  --symphony-primary: hsl(220, 90%, 55%);
  --symphony-spacing-4: 1rem;
  --symphony-radius-base: 0.5rem;
}
```

Easily customize by overriding these variables.

### Typography

Symphony provides semantic HTML styling out of the box:

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<p>Regular paragraph text</p>
<p class="symphony-lead">Lead paragraph for emphasis</p>
```

Typography utilities:

```html
<p class="symphony-text--lg symphony-text--bold">Large bold text</p>
<p class="symphony-text--center symphony-text--muted">Centered muted text</p>
```

### Buttons

Multiple button variants and sizes:

```html
<!-- Variants -->
<button class="symphony-button symphony-button--primary">Primary</button>
<button class="symphony-button symphony-button--secondary">Secondary</button>
<button class="symphony-button symphony-button--outline">Outline</button>
<button class="symphony-button symphony-button--ghost">Ghost</button>

<!-- Sizes -->
<button class="symphony-button symphony-button--primary symphony-button--sm">Small</button>
<button class="symphony-button symphony-button--primary">Default</button>
<button class="symphony-button symphony-button--primary symphony-button--lg">Large</button>

<!-- States -->
<button class="symphony-button symphony-button--primary" disabled>Disabled</button>
<button class="symphony-button symphony-button--primary symphony-button--loading">Loading</button>
```

### Forms

Accessible form components with validation states:

```html
<div class="symphony-form-group">
  <label for="email">Email Address</label>
  <input type="email" id="email" class="symphony-input" placeholder="Enter email">
  <span class="symphony-form-help">We'll never share your email.</span>
</div>

<!-- Validation states -->
<input type="text" class="symphony-input symphony-input--success">
<input type="text" class="symphony-input symphony-input--error">

<!-- Other form controls -->
<textarea class="symphony-textarea"></textarea>
<select class="symphony-select">
  <option>Option 1</option>
</select>
<input type="checkbox" class="symphony-checkbox">
<input type="radio" class="symphony-radio">
```

### Cards

Flexible card containers:

```html
<div class="symphony-card">
  <div class="symphony-card__header">
    <h3 class="symphony-card__title">Card Title</h3>
    <p class="symphony-card__subtitle">Subtitle</p>
  </div>
  <div class="symphony-card__body">
    <p>Card content goes here</p>
  </div>
  <div class="symphony-card__footer">
    <button class="symphony-button symphony-button--primary">Action</button>
  </div>
</div>

<!-- Card variants -->
<div class="symphony-card symphony-card--elevated">Elevated card</div>
<div class="symphony-card symphony-card--outlined">Outlined card</div>
<div class="symphony-card symphony-card--flat">Flat card</div>
```

### Layout

#### Container

Responsive centered container:

```html
<div class="symphony-container">
  <!-- Content -->
</div>

<!-- Fluid container (no max-width) -->
<div class="symphony-container symphony-container--fluid">
  <!-- Content -->
</div>
```

#### Grid System

Modern CSS Grid layout:

```html
<!-- 3 column grid -->
<div class="symphony-grid symphony-grid--cols-3 symphony-grid--gap-md">
  <div>Column 1</div>
  <div>Column 2</div>
  <div>Column 3</div>
</div>

<!-- Responsive grid -->
<div class="symphony-grid symphony-grid--cols-1 symphony-grid--md-cols-2 symphony-grid--lg-cols-3">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Column spanning -->
<div class="symphony-grid symphony-grid--cols-12">
  <div class="symphony-col-span-6">Half width</div>
  <div class="symphony-col-span-6">Half width</div>
</div>
```

#### Flexbox

Flexible box layout utilities:

```html
<div class="symphony-flex symphony-flex--justify-between symphony-flex--align-center symphony-flex--gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Flex direction -->
<div class="symphony-flex symphony-flex--col">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

### Utilities

#### Spacing

Systematic spacing utilities:

```html
<!-- Margin -->
<div class="symphony-m-4">Margin all sides</div>
<div class="symphony-mt-4">Margin top</div>
<div class="symphony-mx-4">Margin horizontal</div>
<div class="symphony-my-4">Margin vertical</div>

<!-- Padding -->
<div class="symphony-p-4">Padding all sides</div>
<div class="symphony-pt-4">Padding top</div>
<div class="symphony-px-4">Padding horizontal</div>
<div class="symphony-py-4">Padding vertical</div>
```

Spacing scale: `0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 16, 20, 24`

#### Display & Visibility

```html
<div class="symphony-block">Block</div>
<div class="symphony-inline-block">Inline block</div>
<div class="symphony-hidden">Hidden</div>
<div class="symphony-invisible">Invisible</div>
```

#### Shadows

```html
<div class="symphony-shadow-sm">Small shadow</div>
<div class="symphony-shadow">Base shadow</div>
<div class="symphony-shadow-lg">Large shadow</div>
<div class="symphony-shadow-xl">Extra large shadow</div>
```

#### Border Radius

```html
<div class="symphony-rounded-sm">Small radius</div>
<div class="symphony-rounded">Base radius</div>
<div class="symphony-rounded-lg">Large radius</div>
<div class="symphony-rounded-full">Full radius</div>
```

## 🎨 Customization

### CSS Variables

Override CSS variables to customize the framework:

```css
:root {
  /* Colors */
  --symphony-primary-hue: 280;
  --symphony-primary-sat: 80%;
  --symphony-primary-light: 60%;
  
  /* Spacing */
  --symphony-spacing-unit: 0.5rem;
  
  /* Typography */
  --symphony-font-sans: 'Inter', system-ui, sans-serif;
  
  /* Border radius */
  --symphony-radius-base: 0.75rem;
}
```

### Dark Mode

Symphony includes automatic dark mode support:

```html
<!-- Automatic (follows system preference) -->
<body>
  <!-- Content -->
</body>

<!-- Manual dark mode -->
<body class="symphony-dark">
  <!-- Content -->
</body>

<!-- Or use data attribute -->
<body data-theme="dark">
  <!-- Content -->
</body>
```

### Modular Imports

Import only the modules you need:

```css
/* Import specific modules */
@import 'symphonycss/src/core/_reset.css';
@import 'symphonycss/src/core/_variables.css';
@import 'symphonycss/src/components/_buttons.css';
@import 'symphonycss/src/utilities/_spacing.css';
```

## 🏗️ Architecture

```
symphonycss/
├── src/
│   ├── core/              # Foundation styles
│   │   ├── _reset.css     # Modern CSS reset
│   │   ├── _variables.css # CSS Custom Properties
│   │   ├── _tokens.css    # Design tokens
│   │   └── _base.css      # Semantic HTML styles
│   ├── layout/            # Layout systems
│   │   ├── _grid.css      # CSS Grid
│   │   ├── _flexbox.css   # Flexbox utilities
│   │   └── _container.css # Container system
│   ├── components/        # UI components
│   │   ├── _typography.css
│   │   ├── _buttons.css
│   │   ├── _forms.css
│   │   └── _cards.css
│   ├── utilities/         # Utility classes
│   │   ├── _spacing.css
│   │   └── _helpers.css
│   └── symphony.css       # Main entry point
├── dist/                  # Distribution files
│   ├── symphony.css       # Unminified
│   └── symphony.min.css   # Minified
└── docs/                  # Documentation
```

## 🔧 Development

### Build

```bash
npm install
npm run build
```

### Watch Mode

```bash
npm run watch
```

## 🌐 Browser Support

Symphony CSS supports all modern browsers:

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Opera (latest)

Note: CSS Cascade Layers and `@property` require modern browser versions.

## 📖 Framework Integration

### React

```jsx
import 'symphonycss/dist/symphony.css';

function App() {
  return (
    <div className="symphony-container">
      <h1>Hello Symphony</h1>
      <button className="symphony-button symphony-button--primary">
        Click me
      </button>
    </div>
  );
}
```

### Vue

```vue
<template>
  <div class="symphony-container">
    <h1>Hello Symphony</h1>
    <button class="symphony-button symphony-button--primary">
      Click me
    </button>
  </div>
</template>

<script>
import 'symphonycss/dist/symphony.css';
</script>
```

### Svelte

```svelte
<script>
  import 'symphonycss/dist/symphony.css';
</script>

<div class="symphony-container">
  <h1>Hello Symphony</h1>
  <button class="symphony-button symphony-button--primary">
    Click me
  </button>
</div>
```

## 📄 License

MIT License - feel free to use Symphony CSS in your projects.

## 🤝 Contributing

Contributions are welcome! Please read our contributing guidelines before submitting PRs.

## 📮 Support

- Documentation: [View Docs](./docs/index.html)
- Issues: [GitHub Issues](https://github.com/your-repo/symphonycss/issues)
- Discussions: [GitHub Discussions](https://github.com/your-repo/symphonycss/discussions)

## 🎵 Why Symphony?

Like a symphony orchestra where each instrument plays its part in harmony, Symphony CSS brings together modern CSS features in perfect coordination to create beautiful, maintainable web experiences.

---

**Built with ❤️ for the modern web**
