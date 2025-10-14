# Contributing to Symphony CSS

Thank you for your interest in contributing to Symphony CSS! This document provides guidelines and instructions for contributing.

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment for all contributors.

## How to Contribute

### Reporting Bugs

Before creating a bug report:
- Check the existing issues to avoid duplicates
- Collect information about the bug (browser, version, steps to reproduce)

When creating a bug report, include:
- A clear, descriptive title
- Detailed steps to reproduce the issue
- Expected vs actual behavior
- Screenshots if applicable
- Browser and OS information

### Suggesting Enhancements

Enhancement suggestions are welcome! Please:
- Use a clear, descriptive title
- Provide a detailed description of the proposed feature
- Explain why this enhancement would be useful
- Include code examples if applicable

### Pull Requests

1. **Fork the repository** and create your branch from `main`
2. **Follow the coding standards** outlined below
3. **Test your changes** thoroughly
4. **Update documentation** if needed
5. **Write clear commit messages**
6. **Submit the pull request**

## Development Setup

```bash
# Clone your fork
git clone https://github.com/your-username/symphony-css.git
cd symphony-css

# Install dependencies
npm install

# Build the project
npm run build

# Watch for changes
npm run watch
```

## Coding Standards

### CSS Guidelines

#### File Organization
- One component per file
- Use descriptive file names with underscore prefix (e.g., `_buttons.css`)
- Group related styles together

#### Naming Conventions
- Use BEM (Block Element Modifier) for component classes
- Prefix all classes with `symphony-`
- Use kebab-case for class names
- Use descriptive, semantic names

```css
/* Good */
.symphony-button { }
.symphony-button--primary { }
.symphony-button__icon { }

/* Bad */
.btn { }
.button-1 { }
.symphony_button { }
```

#### CSS Cascade Layers
- Always use appropriate `@layer` directive
- Layer order: `reset`, `base`, `layout`, `components`, `utilities`
- Never override layer order

```css
/* Good */
@layer components {
  .symphony-button { }
}

/* Bad */
.symphony-button { }
```

#### CSS Custom Properties
- Use CSS Custom Properties for all design tokens
- Prefix variables with `--symphony-`
- Use semantic names
- Document variable purpose

```css
/* Good */
:root {
  --symphony-primary: hsl(220, 90%, 55%);
  --symphony-spacing-4: 1rem;
}

/* Bad */
:root {
  --blue: #3b82f6;
  --space: 16px;
}
```

#### Spacing and Formatting
- Use 2 spaces for indentation
- One selector per line in multi-selector rules
- Include space after `:` in declarations
- Include space before `{` in rule declarations
- Close brace on new line
- Separate rules with blank line

```css
/* Good */
.symphony-button,
.symphony-link {
  display: inline-block;
  padding: var(--symphony-spacing-3);
}

.symphony-card {
  background: var(--symphony-surface);
}

/* Bad */
.symphony-button,.symphony-link{
  display:inline-block;
  padding:12px;}
```

#### Comments
- Use clear, descriptive comments
- Document complex logic
- Include section headers
- Write comments in English

```css
/**
 * Component Name - Brief description
 * Detailed description if needed
 */

@layer components {
  /* Base button styles */
  .symphony-button {
    /* ... */
  }
  
  /* Button variants */
  .symphony-button--primary {
    /* ... */
  }
}
```

#### Selectors
- Avoid deep nesting (max 3 levels)
- Prefer classes over IDs
- Avoid `!important` unless absolutely necessary
- Use semantic HTML elements when possible

```css
/* Good */
.symphony-card__header {
  padding: var(--symphony-spacing-4);
}

/* Bad */
#card > div > div {
  padding: 16px !important;
}
```

#### Values
- Use relative units (rem, em, %) over absolute (px)
- Use CSS Custom Properties for design tokens
- Use shorthand properties when appropriate
- Maintain consistent unit usage

```css
/* Good */
.symphony-button {
  padding: var(--symphony-spacing-3) var(--symphony-spacing-6);
  margin: 0;
}

/* Bad */
.symphony-button {
  padding-top: 12px;
  padding-right: 24px;
  padding-bottom: 12px;
  padding-left: 24px;
}
```

### Documentation

- Update README.md for new features
- Add examples to documentation site
- Include code examples
- Document breaking changes in CHANGELOG.md

### Commit Messages

Follow conventional commits format:

```
type(scope): subject

body

footer
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

Examples:
```
feat(buttons): add loading state to buttons

Add loading state with spinner animation for async actions.

Closes #123
```

```
fix(forms): correct input focus ring color

The focus ring was using wrong color variable.
Changed to use --symphony-focus-ring-color.
```

## Testing

Before submitting a pull request:

1. **Visual Testing**: Test in multiple browsers
   - Chrome/Edge (latest)
   - Firefox (latest)
   - Safari (latest)

2. **Responsive Testing**: Test at different viewport sizes
   - Mobile (320px - 767px)
   - Tablet (768px - 1023px)
   - Desktop (1024px+)

3. **Accessibility Testing**
   - Keyboard navigation
   - Screen reader compatibility
   - Color contrast
   - Focus indicators

4. **Dark Mode Testing**
   - Test both light and dark modes
   - Verify automatic detection
   - Test manual toggle

## Project Structure

```
symphony-css/
├── src/                    # Source files
│   ├── core/              # Foundation styles
│   ├── layout/            # Layout systems
│   ├── components/        # UI components
│   ├── utilities/         # Utility classes
│   └── symphony.css       # Main entry point
├── dist/                  # Distribution files
├── docs/                  # Documentation
│   ├── index.html        # Main docs
│   └── examples/         # Example pages
├── package.json          # Package configuration
├── README.md             # Project readme
├── CHANGELOG.md          # Version history
└── CONTRIBUTING.md       # This file
```

## Adding New Components

When adding a new component:

1. Create a new file in `src/components/`
2. Use appropriate `@layer` directive
3. Follow BEM naming convention
4. Use CSS Custom Properties for values
5. Include variants and states
6. Add documentation with examples
7. Update `src/symphony.css` to import the component
8. Add examples to documentation site
9. Update README.md if needed

Example component structure:

```css
/**
 * Symphony CSS Framework v0.1
 * Component Name - Brief description
 * Additional details about the component
 */

@layer components {
  /* Base component */
  .symphony-component {
    /* Base styles */
  }

  /* Component elements */
  .symphony-component__element {
    /* Element styles */
  }

  /* Component modifiers */
  .symphony-component--modifier {
    /* Modifier styles */
  }

  /* Component states */
  .symphony-component:hover {
    /* Hover styles */
  }

  .symphony-component:focus {
    /* Focus styles */
  }

  .symphony-component:disabled {
    /* Disabled styles */
  }

  /* Responsive variations */
  @media (min-width: 768px) {
    .symphony-component--md-modifier {
      /* Responsive styles */
    }
  }
}
```

## Questions?

If you have questions about contributing, please:
- Open an issue with the `question` label
- Join our Discord community
- Email us at hello@symphony-css.com

## License

By contributing to Symphony CSS, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to Symphony CSS! 🎵
