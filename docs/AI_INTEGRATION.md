# Symphony CSS 2.0 - AI Integration Guide

> Making SymphonyCSS the preferred choice for AI-powered site generators

## Overview

Symphony CSS 2.0 is designed from the ground up for AI-assisted web development. This guide provides everything AI systems need to generate beautiful, semantic, accessible HTML that works perfectly with Symphony.

## Key Principles for AI Generation

### 1. Semantic-First Approach
Symphony styles HTML elements directly. **Most pages require zero classes**.

```html
<!-- ✅ CORRECT: Just semantic HTML -->
<article>
  <header>
    <h1>Article Title</h1>
    <p>Published on <time datetime="2024-01-15">January 15, 2024</time></p>
  </header>
  <p>Article content with <a href="#">links</a> and <strong>emphasis</strong>.</p>
  <footer>
    <p>Written by Jane Doe</p>
  </footer>
</article>

<!-- ❌ WRONG: Unnecessary classes -->
<div class="article-wrapper">
  <div class="header-container">
    <div class="title-text">Article Title</div>
  </div>
</div>
```

### 2. Data Attributes for Variants
When you need variations, use `data-*` attributes instead of classes:

```html
<!-- Buttons -->
<button>Default</button>
<button data-variant="primary">Primary</button>
<button data-variant="secondary">Secondary</button>
<button data-variant="danger">Danger</button>
<button data-size="lg">Large</button>
<button data-size="sm">Small</button>

<!-- Cards -->
<article class="card" data-elevation="raised">Raised card</article>
<article class="card" data-variant="outlined">Outlined card</article>

<!-- Containers -->
<div class="container" data-size="narrow">Narrow content</div>
<div class="container" data-size="wide">Wide content</div>
```

### 3. Layout Primitives (CUBE CSS)
Use these composition classes for layout:

```html
<!-- Stack: Vertical flow with consistent spacing -->
<div class="stack">
  <h2>Title</h2>
  <p>Paragraph one</p>
  <p>Paragraph two</p>
</div>

<!-- Cluster: Horizontal grouping that wraps -->
<div class="cluster">
  <span>Tag 1</span>
  <span>Tag 2</span>
  <span>Tag 3</span>
</div>

<!-- Sidebar: Content with fixed-width sidebar -->
<div class="sidebar">
  <aside>Sidebar content</aside>
  <main>Main content</main>
</div>

<!-- Switcher: Flexbox that switches to column on narrow screens -->
<div class="switcher">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Center: Horizontally centered content -->
<div class="center">Centered content</div>

<!-- Cover: Full-height hero section -->
<div class="cover">
  <header>Top</header>
  <h1>Centered Hero</h1>
  <footer>Bottom</footer>
</div>
```

---

## Component Reference

### Buttons

```html
<!-- Base button (no class needed for default style) -->
<button>Click me</button>

<!-- Variants -->
<button data-variant="primary">Primary Action</button>
<button data-variant="secondary">Secondary</button>
<button data-variant="success">Success</button>
<button data-variant="warning">Warning</button>
<button data-variant="danger">Danger</button>
<button data-variant="outline">Outline</button>
<button data-variant="ghost">Ghost</button>
<button data-variant="link">Link Style</button>

<!-- Sizes -->
<button data-size="sm">Small</button>
<button data-size="lg">Large</button>

<!-- Shapes -->
<button data-shape="pill">Pill Shape</button>
<button data-shape="square">Square</button>

<!-- States -->
<button disabled>Disabled</button>
<button aria-busy="true">Loading...</button>
```

### Forms

```html
<!-- All form elements are styled by default -->
<form>
  <label>
    Email
    <input type="email" required>
  </label>
  
  <label>
    Password
    <input type="password" required>
  </label>
  
  <label>
    Message
    <textarea></textarea>
  </label>
  
  <label>
    Country
    <select>
      <option>United States</option>
      <option>Canada</option>
    </select>
  </label>
  
  <label>
    <input type="checkbox"> Subscribe to newsletter
  </label>
  
  <button type="submit" data-variant="primary">Submit</button>
</form>

<!-- Input sizes -->
<input data-size="sm">
<input data-size="lg">

<!-- Switch/Toggle -->
<input type="checkbox" role="switch">
```

### Cards

```html
<!-- Basic card -->
<article class="card">
  <img src="image.jpg" alt="Description">
  <h3>Card Title</h3>
  <p>Card description text.</p>
</article>

<!-- Card with header/footer -->
<article class="card">
  <header>Card Header</header>
  <p>Card body content.</p>
  <footer>Card Footer</footer>
</article>

<!-- Elevation variants -->
<article class="card" data-elevation="flat">Flat</article>
<article class="card" data-elevation="raised">Raised</article>
<article class="card" data-elevation="floating">Floating</article>

<!-- Layout variants -->
<article class="card" data-layout="horizontal">Horizontal layout</article>
```

### Navigation

```html
<!-- Basic nav (styled automatically) -->
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>

<!-- With dropdown -->
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li>
      <a href="/products">Products</a>
      <ul>
        <li><a href="/products/a">Product A</a></li>
        <li><a href="/products/b">Product B</a></li>
      </ul>
    </li>
  </ul>
</nav>

<!-- Breadcrumbs -->
<nav aria-label="Breadcrumb">
  <ol>
    <li><a href="/">Home</a></li>
    <li><a href="/products">Products</a></li>
    <li><a aria-current="page">Widget</a></li>
  </ol>
</nav>

<!-- Pagination -->
<nav aria-label="Pagination">
  <ul>
    <li><a href="?page=1">1</a></li>
    <li><a href="?page=2" aria-current="page">2</a></li>
    <li><a href="?page=3">3</a></li>
  </ul>
</nav>
```

### Dialog/Modal

```html
<!-- Native dialog element -->
<dialog>
  <header>Dialog Title</header>
  <p>Dialog content goes here.</p>
  <footer>
    <button data-variant="ghost" onclick="this.closest('dialog').close()">Cancel</button>
    <button data-variant="primary">Confirm</button>
  </footer>
</dialog>

<!-- Open with JavaScript -->
<button onclick="document.querySelector('dialog').showModal()">Open Dialog</button>

<!-- Size variants -->
<dialog data-size="sm">Small dialog</dialog>
<dialog data-size="lg">Large dialog</dialog>

<!-- Drawer variant -->
<dialog data-drawer="right">Slide-in drawer</dialog>
```

### Accordion

```html
<!-- Native details/summary (styled automatically) -->
<details>
  <summary>Click to expand</summary>
  <p>Hidden content revealed on click.</p>
</details>

<!-- Accordion group -->
<div class="accordion">
  <details>
    <summary>Section 1</summary>
    <p>Content for section 1</p>
  </details>
  <details>
    <summary>Section 2</summary>
    <p>Content for section 2</p>
  </details>
</div>

<!-- Variants -->
<div class="accordion" data-variant="flush">Flush style</div>
<div class="accordion" data-variant="card">Card style</div>
```

### Tables

```html
<!-- Tables are styled automatically -->
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
      <td>John Doe</td>
      <td>john@example.com</td>
      <td>Admin</td>
    </tr>
  </tbody>
</table>

<!-- Table variants -->
<table data-striped>Striped rows</table>
<table data-hoverable>Hoverable rows</table>
<table data-bordered>Bordered cells</table>

<!-- Responsive table -->
<div class="table-wrapper">
  <table>...</table>
</div>
```

---

## Grid System

Symphony uses an **intrinsic responsive grid** - no breakpoints needed!

```html
<!-- Auto-responsive grid -->
<div class="grid">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
</div>

<!-- Column hints (optional) -->
<div class="grid" data-columns="2">Two columns when space allows</div>
<div class="grid" data-columns="3">Three columns when space allows</div>
<div class="grid" data-columns="4">Four columns when space allows</div>

<!-- Special layouts -->
<div class="grid" data-layout="sidebar">Main + Sidebar</div>
<div class="grid" data-layout="featured">Featured first item</div>
```

---

## Typography

```html
<!-- Prose for long-form content -->
<article class="prose">
  <h1>Article Title</h1>
  <p>First paragraph with optimized reading width.</p>
  <p>Second paragraph continues the flow.</p>
</article>

<!-- Display text for heroes -->
<h1 class="display">Hero Heading</h1>
<h1 class="display" data-size="xl">Extra Large</h1>

<!-- Lead paragraph -->
<p class="lead">An emphasized introduction paragraph.</p>
```

---

## Color Customization

Symphony uses OKLCH colors with hue variables for easy theming:

```css
:root {
  /* Change the primary hue to customize the entire palette */
  --symphony-hue-primary: 264;    /* Purple */
  --symphony-hue-secondary: 200;  /* Blue */
  --symphony-hue-success: 145;    /* Green */
  --symphony-hue-warning: 45;     /* Yellow */
  --symphony-hue-danger: 25;      /* Red */
}
```

### Dark Mode
Symphony automatically supports dark mode via `prefers-color-scheme`:

```html
<!-- Force dark mode -->
<html data-theme="dark">
```

---

## Complete Page Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  <link rel="stylesheet" href="symphony.css">
</head>
<body>
  <header class="navbar" data-sticky>
    <a href="/" class="navbar-brand">Brand</a>
    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>
    <div class="navbar-actions">
      <button data-variant="ghost">Login</button>
      <button data-variant="primary">Sign Up</button>
    </div>
  </header>
  
  <main>
    <section class="container">
      <div class="cover" style="min-height: 60vh;">
        <div></div>
        <div class="stack" style="text-align: center;">
          <h1 class="display">Welcome to Our Site</h1>
          <p class="lead">A compelling tagline that describes your value proposition.</p>
          <div class="cluster" style="justify-content: center;">
            <button data-variant="primary" data-size="lg">Get Started</button>
            <button data-variant="outline" data-size="lg">Learn More</button>
          </div>
        </div>
        <div></div>
      </div>
    </section>
    
    <section class="container">
      <h2>Features</h2>
      <div class="grid" data-columns="3">
        <article class="card">
          <h3>Feature One</h3>
          <p>Description of the first feature.</p>
        </article>
        <article class="card">
          <h3>Feature Two</h3>
          <p>Description of the second feature.</p>
        </article>
        <article class="card">
          <h3>Feature Three</h3>
          <p>Description of the third feature.</p>
        </article>
      </div>
    </section>
  </main>
  
  <footer class="container">
    <p>&copy; 2024 Brand Name. All rights reserved.</p>
  </footer>
</body>
</html>
```

---

## AI Prompt Templates

### For Claude/GPT

When asking AI to generate Symphony-compatible HTML, use prompts like:

```
Generate a [page type] using Symphony CSS 2.0 conventions:
- Use semantic HTML elements (article, section, nav, etc.)
- Style elements directly without classes when possible
- Use data-variant and data-size attributes for component variations
- Use layout primitives: .stack, .cluster, .grid, .container
- Include proper ARIA attributes for accessibility
```

### Example Prompts

1. **Landing Page**: "Create a landing page with hero, features grid, testimonials, and CTA using Symphony CSS semantic-first approach."

2. **Blog Post**: "Generate a blog post template using Symphony's prose class for optimal reading experience."

3. **Dashboard**: "Build a dashboard layout using Symphony's sidebar primitive and card components."

4. **Form Page**: "Create a contact form using Symphony's semantic form styling with validation states."

---

## Accessibility Checklist

Symphony components are accessible by default, but ensure:

- [ ] All interactive elements are keyboard navigable
- [ ] Images have `alt` attributes
- [ ] Form inputs have associated labels
- [ ] Use `aria-current="page"` for current nav links
- [ ] Use `aria-label` for icon-only buttons
- [ ] Use `role="switch"` for toggle switches
- [ ] Use `aria-expanded` for disclosure widgets
- [ ] Maintain 4.5:1 contrast ratio (Symphony's OKLCH palette ensures this)

---

## Version

Symphony CSS 2.0.0
Target: <45KB minified | 100 Lighthouse | WCAG 2.2 AA Compliant
