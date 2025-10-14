# Symphony CSS - Quick Start Guide

Get up and running with Symphony CSS in minutes.

## Installation

### Option 1: Direct Link (Fastest)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Symphony App</title>
  <link rel="stylesheet" href="path/to/symphony-css/dist/symphony.css">
</head>
<body>
  <!-- Your content here -->
</body>
</html>
```

### Option 2: NPM

```bash
npm install symphony-css
```

Then import in your project:

```javascript
import 'symphony-css/dist/symphony.css';
```

## Your First Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Symphony CSS Demo</title>
  <link rel="stylesheet" href="dist/symphony.css">
</head>
<body>
  <!-- Container -->
  <div class="symphony-container symphony-py-16">
    
    <!-- Hero Section -->
    <div class="symphony-text--center symphony-mb-12">
      <h1 class="symphony-display--lg">Welcome to Symphony</h1>
      <p class="symphony-lead">Build beautiful websites with modern CSS</p>
    </div>
    
    <!-- Buttons -->
    <div class="symphony-flex symphony-flex--justify-center symphony-flex--gap-4 symphony-mb-16">
      <button class="symphony-button symphony-button--primary symphony-button--lg">
        Get Started
      </button>
      <button class="symphony-button symphony-button--outline symphony-button--lg">
        Learn More
      </button>
    </div>
    
    <!-- Feature Cards -->
    <div class="symphony-grid symphony-grid--cols-1 symphony-grid--md-cols-3 symphony-grid--gap-lg">
      
      <div class="symphony-card symphony-card--elevated">
        <div class="symphony-card__body">
          <h3 class="symphony-card__title">Modern CSS</h3>
          <p>Built with cascade layers and custom properties</p>
        </div>
      </div>
      
      <div class="symphony-card symphony-card--elevated">
        <div class="symphony-card__body">
          <h3 class="symphony-card__title">Responsive</h3>
          <p>Mobile-first responsive design out of the box</p>
        </div>
      </div>
      
      <div class="symphony-card symphony-card--elevated">
        <div class="symphony-card__body">
          <h3 class="symphony-card__title">Accessible</h3>
          <p>WCAG compliant components and focus states</p>
        </div>
      </div>
      
    </div>
    
  </div>
</body>
</html>
```

## Common Patterns

### Navigation Bar

```html
<nav class="symphony-bg-surface symphony-border-b symphony-py-4">
  <div class="symphony-container">
    <div class="symphony-flex symphony-flex--justify-between symphony-flex--align-center">
      <div class="symphony-text--xl symphony-text--bold">Brand</div>
      <div class="symphony-flex symphony-flex--gap-6">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
      </div>
    </div>
  </div>
</nav>
```

### Form

```html
<form class="symphony-card" style="max-width: 500px;">
  <div class="symphony-card__body">
    <h2 class="symphony-card__title">Sign Up</h2>
    
    <div class="symphony-form-group">
      <label for="name">Name</label>
      <input type="text" id="name" class="symphony-input" placeholder="Your name">
    </div>
    
    <div class="symphony-form-group">
      <label for="email">Email</label>
      <input type="email" id="email" class="symphony-input" placeholder="your@email.com">
    </div>
    
    <button type="submit" class="symphony-button symphony-button--primary symphony-button--block">
      Submit
    </button>
  </div>
</form>
```

### Grid Layout

```html
<div class="symphony-grid symphony-grid--cols-1 symphony-grid--md-cols-2 symphony-grid--lg-cols-4 symphony-grid--gap-lg">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
</div>
```

## Customization

Override CSS variables to customize the theme:

```html
<style>
  :root {
    /* Change primary color */
    --symphony-primary-hue: 280;
    --symphony-primary-sat: 80%;
    --symphony-primary-light: 60%;
    
    /* Change spacing scale */
    --symphony-spacing-unit: 0.5rem;
    
    /* Change border radius */
    --symphony-radius-base: 1rem;
    
    /* Change font */
    --symphony-font-sans: 'Inter', system-ui, sans-serif;
  }
</style>
```

## Dark Mode

Symphony includes automatic dark mode:

```html
<!-- Automatic (follows system preference) -->
<body>
  <!-- Content -->
</body>

<!-- Force dark mode -->
<body class="symphony-dark">
  <!-- Content -->
</body>
```

## Framework Integration

### React

```jsx
import 'symphony-css/dist/symphony.css';

function App() {
  return (
    <div className="symphony-container symphony-py-16">
      <h1 className="symphony-display--lg">Hello React</h1>
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
  <div class="symphony-container symphony-py-16">
    <h1 class="symphony-display--lg">Hello Vue</h1>
    <button class="symphony-button symphony-button--primary">
      Click me
    </button>
  </div>
</template>

<script>
import 'symphony-css/dist/symphony.css';
</script>
```

## Next Steps

- 📚 Read the [full documentation](docs/index.html)
- 🎨 Check out [example pages](docs/examples/)
- 💡 Browse the [component library](docs/index.html#components)
- 🛠️ Learn about [customization](README.md#customization)

## Need Help?

- 📖 [Documentation](docs/index.html)
- 🐛 [Report Issues](https://github.com/your-repo/symphony-css/issues)
- 💬 [Discussions](https://github.com/your-repo/symphony-css/discussions)

---

**Happy building with Symphony CSS! 🎵**
