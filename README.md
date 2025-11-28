# Symphony CSS v0.2.1

**The semantic-first CSS framework for AI-powered web development.**

Symphony CSS is a zero-class baseline framework that makes beautiful, accessible websites possible with just semantic HTML. Add data-attributes for variants when you need them.

## ✨ Features

- **🎯 Zero-Class Baseline** - Beautiful pages with just semantic HTML
- **🎨 OKLCH Color System** - Perceptually uniform, mathematically perfect colors
- **📦 <45KB Minified** - Lightweight yet comprehensive
- **🤖 AI-Generator Friendly** - Designed for Claude, GPT, and other AI systems
- **📐 Container Queries** - Component-level responsive design
- **🔀 CSS Nesting** - Native browser nesting for maintainable code
- **🎭 Data-Attribute API** - `data-variant`, `data-size` instead of class soup
- **🌙 Dark Mode** - Automatic and manual theme switching
- **♿ WCAG 2.2 AA** - Accessible by default
- **🌐 RTL Ready** - Logical properties throughout

## 📦 Installation

### NPM

```bash
npm install @symphonyui/symphonycss
```

### CDN

```html
<link rel="stylesheet" href="https://unpkg.com/@symphonyui/symphonycss/dist/symphony.min.css">
```

### Download

Download the latest release from the [releases page](https://github.com/symphonyui/symphonycss/releases).

## 🚀 Quick Start

**That's the magic of Symphony CSS** – this works beautifully with zero classes:

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
  <header>
    <nav>
      <a href="/">Logo</a>
      <ul>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>
  </header>
  
  <main>
    <article>
      <h1>Welcome to Symphony CSS</h1>
      <p>A modern CSS framework that embraces semantic HTML.</p>
      <button data-variant="primary">Get Started</button>
    </article>
  </main>
  
  <footer>
    <p>&copy; 2025 Your Company</p>
  </footer>
</body>
</html>
```

**No classes needed!** The semantic HTML elements are styled automatically.

## 📚 Documentation

### The Semantic-First Philosophy

Symphony CSS follows a simple principle: **semantic HTML should look beautiful by default**.

1. **Level 1: Zero Classes** - Semantic HTML elements are styled automatically
2. **Level 2: Data Attributes** - Add `data-variant`, `data-size` for variants
3. **Level 3: Utility Classes** - Use `.cluster`, `.stack` for layout compositions
4. **Level 4: Custom CSS** - Extend with your own styles at highest specificity

### Cascade Layers

Symphony uses CSS Cascade Layers for predictable specificity:

```css
@layer symphony.reset,      /* Browser normalization */
       symphony.base,       /* Foundation styles */
       symphony.semantic,   /* Semantic HTML styling */
       symphony.layout,     /* Grid, flexbox, containers */
       symphony.components, /* Buttons, cards, forms */
       symphony.utilities,  /* Helper classes */
       symphony.themes;     /* Theme customizations */
```

### Design Tokens (OKLCH Colors)

Symphony uses OKLCH for perceptually uniform, accessible colors:

```css
:root {
  /* Hue values for easy theming */
  --symphony-hue-primary: 264;    /* Purple */
  --symphony-hue-success: 145;    /* Green */
  --symphony-hue-warning: 85;     /* Yellow */
  --symphony-hue-danger: 25;      /* Red */
  
  /* Derived colors using OKLCH */
  --symphony-primary: oklch(55% 0.25 var(--symphony-hue-primary));
}
```

Change your entire color scheme by adjusting hue values:

```css
:root {
  --symphony-hue-primary: 200; /* Switch to blue theme */
}
```

### Typography

**Zero-class styling** - just use semantic HTML:

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<p>Regular paragraph with <strong>bold</strong> and <em>italic</em> text.</p>
<p><small>Small text for fine print</small></p>
```

**Prose container** for long-form content:

```html
<article class="prose">
  <h1>Article Title</h1>
  <p>Content with optimal reading line length...</p>
</article>
```

**Data-attribute variants**:

```html
<p data-variant="muted">Muted text</p>
<p data-size="lg">Large text</p>
```

### Buttons

**Semantic buttons work automatically**:

```html
<button>Default Button</button>
<button disabled>Disabled</button>
```

**Data-attribute variants**:

```html
<!-- Variants -->
<button data-variant="primary">Primary</button>
<button data-variant="secondary">Secondary</button>
<button data-variant="outline">Outline</button>
<button data-variant="ghost">Ghost</button>
<button data-variant="danger">Danger</button>

<!-- Sizes -->
<button data-size="sm">Small</button>
<button data-size="lg">Large</button>

<!-- Shapes -->
<button data-shape="pill">Pill Button</button>
<button data-shape="square">■</button>
```

### Forms

**Semantic forms are styled automatically**:

```html
<form>
  <label>
    Email Address
    <input type="email" placeholder="you@example.com">
  </label>
  
  <label>
    Message
    <textarea placeholder="Your message..."></textarea>
  </label>
  
  <label>
    Country
    <select>
      <option>United States</option>
      <option>Canada</option>
    </select>
  </label>
  
  <button type="submit" data-variant="primary">Send</button>
</form>
```

**Validation states** with data attributes:

```html
<input type="email" data-state="success" value="valid@email.com">
<input type="email" data-state="error" value="invalid">
<input type="text" data-state="warning">
```

**Toggle switches**:

```html
<label class="switch">
  <input type="checkbox">
  <span>Enable notifications</span>
</label>
```

### Cards

**Semantic article cards**:

```html
<article class="card">
  <header>
    <h3>Card Title</h3>
    <p>Subtitle text</p>
  </header>
  <p>Card content goes here</p>
  <footer>
    <button data-variant="primary">Action</button>
  </footer>
</article>
```

**Container query responsive cards**:

Cards automatically adapt their layout based on their container width, not the viewport.

**Elevation variants**:

```html
<article class="card" data-elevation="flat">No shadow</article>
<article class="card" data-elevation="raised">Subtle shadow</article>
<article class="card" data-elevation="floating">Prominent shadow</article>
```

### Navigation

**Semantic navigation** - styled automatically:

```html
<nav>
  <a href="/" aria-current="page">Home</a>
  <a href="/about">About</a>
  <a href="/contact">Contact</a>
</nav>
```

**Nav with nested lists**:

```html
<nav data-variant="navbar">
  <a href="/">Logo</a>
  <ul>
    <li><a href="/products">Products</a></li>
    <li><a href="/about">About</a></li>
    <li><button data-variant="primary">Sign Up</button></li>
  </ul>
</nav>
```

**Breadcrumbs, tabs, pagination**:

```html
<nav data-variant="breadcrumb">
  <ol>
    <li><a href="/">Home</a></li>
    <li><a href="/products">Products</a></li>
    <li aria-current="page">Widget</li>
  </ol>
</nav>

<nav data-variant="tabs">
  <a href="#tab1" aria-current="page">Tab 1</a>
  <a href="#tab2">Tab 2</a>
  <a href="#tab3">Tab 3</a>
</nav>
```

### Accordion

**Native details/summary elements**:

```html
<details>
  <summary>Click to expand</summary>
  <p>Expanded content here...</p>
</details>

<!-- Grouped accordions -->
<div class="accordion" data-exclusive>
  <details open>
    <summary>Section One</summary>
    <p>First section content</p>
  </details>
  <details>
    <summary>Section Two</summary>
    <p>Second section content</p>
  </details>
</div>
```

### Dialog

**Native HTML dialog**:

```html
<dialog id="my-dialog">
  <header>
    <h2>Dialog Title</h2>
  </header>
  <p>Dialog content here</p>
  <footer>
    <button data-variant="ghost">Cancel</button>
    <button data-variant="primary">Confirm</button>
  </footer>
</dialog>

<button onclick="document.getElementById('my-dialog').showModal()">
  Open Dialog
</button>
```

**Size variants**:

```html
<dialog data-size="sm">Small dialog</dialog>
<dialog data-size="lg">Large dialog</dialog>
<dialog data-size="fullscreen">Fullscreen</dialog>
```

### Tables

**Semantic tables** - styled automatically:

```html
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Email</th>
      <th>Role</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Jane Doe</td>
      <td>jane@example.com</td>
      <td>Admin</td>
    </tr>
  </tbody>
</table>
```

**Variants**:

```html
<table data-variant="striped">...</table>
<table data-variant="bordered">...</table>
<table data-size="compact">...</table>
```

### Layout Primitives (CUBE CSS)

Symphony includes powerful layout compositions:

#### Stack (Vertical Flow)

```html
<div class="stack">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Custom spacing -->
<div class="stack" data-space="lg">...</div>
```

#### Cluster (Horizontal Wrap)

```html
<div class="cluster">
  <span>Tag 1</span>
  <span>Tag 2</span>
  <span>Tag 3</span>
</div>
```

#### Sidebar Layout

```html
<div class="sidebar">
  <aside>Sidebar content</aside>
  <main>Main content (grows)</main>
</div>
```

#### Switcher (Responsive Columns)

```html
<div class="switcher">
  <div>Column 1</div>
  <div>Column 2</div>
  <div>Column 3</div>
</div>
```

Automatically switches from horizontal to vertical below threshold.

#### Center

```html
<div class="center">
  <article>Centered content with max-width</article>
</div>
```

#### Cover

```html
<div class="cover">
  <header>Top</header>
  <main>Centered vertically</main>
  <footer>Bottom</footer>
</div>
```

### Grid System

**Intrinsic responsive grid** (no breakpoint classes needed):

```html
<div class="grid">
  <div>Auto-sized column</div>
  <div>Auto-sized column</div>
  <div>Auto-sized column</div>
</div>
```

**Column hints**:

```html
<div class="grid" data-columns="2">Two columns</div>
<div class="grid" data-columns="3">Three columns</div>
<div class="grid" data-columns="4">Four columns</div>
```

**Special layouts**:

```html
<div class="grid" data-layout="masonry">Masonry layout</div>
<div class="grid" data-layout="auto-fill">Fill available space</div>
```

### Container

**Centered container with fluid width**:

```html
<div class="container">
  <!-- Max-width content -->
</div>

<div class="container" data-size="narrow">Narrow content</div>
<div class="container" data-size="wide">Wide content</div>
```

### Spacing Utilities

**Logical properties for RTL support**:

```html
<!-- Margin -->
<div class="m-md">Margin all sides</div>
<div class="mt-lg">Margin block-start (top)</div>
<div class="mx-auto">Margin inline auto (center)</div>

<!-- Padding -->
<div class="p-lg">Padding all sides</div>
<div class="py-md">Padding block (vertical)</div>
<div class="px-sm">Padding inline (horizontal)</div>

<!-- Gap (for flex/grid) -->
<div class="cluster gap-md">Gap between items</div>
```

**Scale**: `2xs`, `xs`, `sm`, `md`, `lg`, `xl`, `2xl`, `3xl`

## 🎨 Customization

### Theme Customization

Override CSS variables to customize your theme:

```css
:root {
  /* Change primary hue (0-360) */
  --symphony-hue-primary: 200;  /* Blue theme */
  
  /* Adjust color intensity */
  --symphony-chroma: 0.2;       /* More vibrant */
  
  /* Typography */
  --symphony-font-sans: 'Inter', system-ui, sans-serif;
  --symphony-font-heading: 'Playfair Display', serif;
  
  /* Spacing scale multiplier */
  --symphony-space-unit: 0.25rem;
  
  /* Border radius */
  --symphony-radius-md: 0.75rem;
}
```

### Dark Mode

**Automatic** (follows system preference):
```html
<body><!-- Auto dark mode --></body>
```

**Manual toggle**:
```html
<body data-theme="dark"><!-- Force dark --></body>
<body data-theme="light"><!-- Force light --></body>
```

### Modular Imports

Import only what you need:

```css
/* Core (required) */
@import 'symphonycss/src/core/_reset.css';
@import 'symphonycss/src/core/_variables.css';
@import 'symphonycss/src/core/_base.css';

/* Layout (pick what you need) */
@import 'symphonycss/src/layout/_container.css';
@import 'symphonycss/src/layout/_grid.css';
@import 'symphonycss/src/layout/_flexbox.css';

/* Components (pick what you need) */
@import 'symphonycss/src/components/_buttons.css';
@import 'symphonycss/src/components/_cards.css';
@import 'symphonycss/src/components/_forms.css';
```

## 🤖 AI Integration

Symphony CSS is designed for AI-powered site generators. See our [AI Integration Guide](./docs/AI_INTEGRATION.md) for:

- Component patterns and prompts
- JSON schema for validation
- Best practices for AI generation
- Example prompts for Claude/GPT

### Quick AI Prompt Template

```
Generate a [component type] using Symphony CSS.
Use semantic HTML elements with data-attributes for variants.
Available variants: primary, secondary, outline, ghost, danger
Available sizes: sm, md, lg
Use CUBE CSS primitives: stack, cluster, sidebar, switcher
```

## 🏗️ Architecture

```
symphonycss/
├── src/
│   ├── core/               # Foundation (required)
│   │   ├── _reset.css      # Zero-specificity reset
│   │   ├── _variables.css  # OKLCH tokens & @property
│   │   ├── _tokens.css     # Semantic aliases
│   │   └── _base.css       # Semantic HTML styling
│   ├── layout/             # CUBE CSS compositions
│   │   ├── _container.css  # Centered containers
│   │   ├── _grid.css       # Intrinsic grid
│   │   └── _flexbox.css    # Stack, cluster, sidebar, etc.
│   ├── components/         # Enhanced HTML elements
│   │   ├── _typography.css # Prose & text utilities
│   │   ├── _buttons.css    # Button variants
│   │   ├── _cards.css      # Container-query cards
│   │   ├── _forms.css      # Form controls
│   │   ├── _dialog.css     # Native dialogs
│   │   ├── _navigation.css # Nav patterns
│   │   ├── _accordion.css  # Details/summary
│   │   └── _tables.css     # Responsive tables
│   ├── utilities/          # Helper classes
│   │   ├── _spacing.css    # Logical margin/padding
│   │   └── _helpers.css    # Display, visibility, etc.
│   └── symphony.css        # Main entry point
├── dist/                   # Built files
│   ├── symphony.css        # Full bundle
│   └── symphony.min.css    # Minified (<45KB)
└── docs/
    ├── AI_INTEGRATION.md   # AI generator guide
    └── symphony-schema.json # Component JSON schema
```

## 🔧 Development

```bash
# Install dependencies
npm install

# Build all variants
npm run build

# Watch mode
npm run watch

# Build minified only
npm run build:minify

# Check bundle size
npm run size
```

## 🌐 Browser Support

Symphony CSS requires modern browsers with support for:

- CSS Cascade Layers (`@layer`)
- CSS Nesting (native)
- Container Queries
- OKLCH colors
- `:has()` selector

**Supported browsers:**
- Chrome 115+ / Edge 115+
- Firefox 117+
- Safari 17+

## 📖 Framework Integration

### React

```jsx
import 'symphonycss/dist/symphony.css';

function App() {
  return (
    <main>
      <article>
        <h1>Hello Symphony</h1>
        <p>Using semantic HTML in React.</p>
        <button data-variant="primary">Click me</button>
      </article>
    </main>
  );
}
```

### Vue

```vue
<template>
  <main>
    <article>
      <h1>Hello Symphony</h1>
      <p>Using semantic HTML in Vue.</p>
      <button data-variant="primary">Click me</button>
    </article>
  </main>
</template>

<script setup>
import 'symphonycss/dist/symphony.css';
</script>
```

### Astro

```astro
---
import 'symphonycss/dist/symphony.css';
---

<main>
  <article>
    <h1>Hello Symphony</h1>
    <p>Using semantic HTML in Astro.</p>
    <button data-variant="primary">Click me</button>
  </article>
</main>
```

### AI Site Generators

Symphony CSS is designed to be the output target for AI-generated sites:

```javascript
// Example AI generation config
const symphonyConfig = {
  framework: 'symphonycss',
  version: '0.2.1',
  preferences: {
    useSemanticHTML: true,
    variantSystem: 'data-attributes',
    layoutPrimitives: ['stack', 'cluster', 'sidebar'],
    colorScheme: 'oklch'
  }
};
```

## 🆚 Comparison

| Feature | Symphony | Tailwind | Bootstrap | Pico |
|---------|----------|----------|-----------|------|
| Zero-class baseline | ✅ | ❌ | ❌ | ✅ |
| Data-attribute API | ✅ | ❌ | ❌ | ❌ |
| OKLCH colors | ✅ | ❌ | ❌ | ❌ |
| Container queries | ✅ | Partial | ❌ | ❌ |
| CSS nesting (native) | ✅ | ❌ | ❌ | ❌ |
| Bundle size | ~35KB | ~300KB+ | ~230KB | ~10KB |
| AI-generator friendly | ✅ | ❌ | ❌ | Partial |

## 📄 License

MIT License - use SymphonyCSS freely in your projects.

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## 📮 Support

- [Documentation](./docs/index.html)
- [AI Integration Guide](./docs/AI_INTEGRATION.md)
- [GitHub Issues](https://github.com/symphonyui/symphonycss/issues)
- [Discussions](https://github.com/symphonyui/symphonycss/discussions)

## 🎵 Why Symphony?

Like a symphony orchestra where each instrument plays its part in harmony, Symphony CSS brings together modern CSS features—cascade layers, container queries, OKLCH colors, and native nesting—in perfect coordination to create beautiful, maintainable web experiences.

**Write semantic HTML. Get beautiful results. Zero class soup required.**

---

**Built with ❤️ for the modern web and AI-powered future**
