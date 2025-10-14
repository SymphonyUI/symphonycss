# Changelog

All notable changes to Symphony CSS will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2024-10-14

### 🔧 Critical Fixes Applied (Post-Validation)

#### Grid System
- **FIXED:** Grid now uses exact 1200px mathematics: 12 columns × 78px + 11 gutters × 24px
- **FIXED:** Changed from fluid `1fr` to fixed `78px` columns at desktop
- **ADDED:** BEM naming convention: `.symphony-grid__col--1` through `.symphony-grid__col--12`
- **MAINTAINED:** Legacy class support for backward compatibility

#### Typography
- **FIXED:** H1 size from ~51px to exact 74px (4.625rem)
- **FIXED:** H2 size from ~38px to exact 42px (2.625rem)
- **ADDED:** H1 letter-spacing: 1% (0.01em)
- **ADDED:** H2 letter-spacing: 0%
- **ADDED:** `text-wrap: balance` on h1, h2, h3
- **FIXED:** Body text sizes: 14px, 16px, 18px, 20px (not 4px-based scale)

#### Google Fonts Integration
- **ADDED:** New file `src/core/_fonts.css` for font imports
- **ADDED:** Mona Sans (Regular 400, Medium 500, Semibold 600) for body text
- **ADDED:** Inter Display (Semibold 600) for all headings
- **FIXED:** Font loading order (fonts imported first)

#### Dark Theme Colors
- **FIXED:** Background from HSL to exact hex #020410
- **FIXED:** Primary from HSL to exact hex #0055FE
- **FIXED:** Text titles to pure white #FFFFFF
- **FIXED:** Text body to exact hex #CBD2D9 (gray-300)
- **ADDED:** Surface color #0A0F1E for cards

#### Button Specifications
- **FIXED:** Horizontal padding from 24px to 32px (2rem)
- **FIXED:** Font size from 16px to 14px (0.875rem)
- **FIXED:** Font weight from 500 to 400 (Regular)
- **ADDED:** Letter spacing: 0
- **CHANGED:** Default border radius to 50px (pill shape)
- **ADDED:** `.symphony-button--rounded` variant (10px radius)
- **FIXED:** Font family to Mona Sans

#### Modern CSS 2025 Features
- **ADDED:** Container queries support on `.symphony-container`
- **ADDED:** Container queries support on `.symphony-card`
- **ADDED:** Example `@container` query for responsive card padding
- **ADDED:** `text-wrap: balance` on headings

### Added

#### Core
- Modern CSS reset with accessibility considerations
- CSS Custom Properties with `@property` definitions for typed, animatable variables
- Comprehensive design token system with semantic mappings
- CSS Cascade Layers architecture (`@layer reset, base, layout, components, utilities`)
- Semantic-first base styles for HTML elements
- Automatic dark mode support with system preference detection
- Manual dark mode toggle via class or data attribute

#### Layout
- Responsive container system with fluid variant
- Modern CSS Grid layout with 12-column system
- Auto-fit and auto-fill grid patterns
- Responsive grid column utilities
- Column and row span utilities
- Comprehensive Flexbox utilities with BEM naming
- Flex direction, wrap, justify, and align utilities
- Gap utilities for Grid and Flexbox

#### Components
- Typography system with display text, lead paragraphs, and utilities
- Text size, weight, color, and alignment utilities
- Prose component for optimized reading experience
- Button component with multiple variants (primary, secondary, success, warning, danger)
- Outline, ghost, and link button styles
- Button sizes (small, default, large)
- Button states (disabled, loading)
- Icon buttons and button groups
- Form components (input, textarea, select, checkbox, radio)
- Form validation states (success, error)
- Switch toggle component
- Input groups with addons
- Form helper and error text
- Card component with header, body, and footer sections
- Card variants (elevated, outlined, flat, interactive)
- Card sizes and horizontal layout
- Card groups with responsive grid
- Card overlay variant

#### Utilities
- Comprehensive spacing utilities (margin, padding, gap)
- Display and visibility utilities
- Position utilities (static, relative, absolute, fixed, sticky)
- Width and height utilities
- Min/max width and height utilities
- Overflow utilities
- Z-index scale
- Opacity utilities
- Cursor utilities
- Pointer events and user select
- Border radius utilities
- Border utilities
- Shadow utilities (6 levels)
- Background color utilities
- Object fit utilities
- Aspect ratio utilities
- Screen reader only utility
- Transition utilities
- Transform utilities
- Responsive visibility utilities
- Print utilities

#### Documentation
- Comprehensive documentation site with live examples
- Getting started guide
- Component documentation with code examples
- Layout system documentation
- Utilities reference
- Landing page example
- README with installation and usage instructions
- Changelog

#### Build System
- Package.json with build scripts
- LightningCSS integration for minification
- Source and distribution file structure

### Architecture Highlights
- **Modular**: Import only what you need
- **Framework Agnostic**: Works with React, Vue, Svelte, or vanilla HTML
- **BEM Naming**: Clear, maintainable class names for components
- **Semantic First**: Minimal classes required, HTML elements styled by default
- **Modern CSS**: Leverages latest CSS features (Cascade Layers, @property)
- **Accessible**: WCAG compliant focus states and semantic markup
- **Responsive**: Mobile-first responsive design
- **Customizable**: Easy theming via CSS Custom Properties

[0.1.0]: https://github.com/your-repo/symphony-css/releases/tag/v0.1.0
