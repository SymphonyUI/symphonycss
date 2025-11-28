# Changelog

All notable changes to this project will be documented in this file.

## [0.2.1] - 2025-11-28

### 🎉 Major Update

#### Added
- **Modern CSS Architecture**: Cascade Layers (@layer) with 7-layer system
- **OKLCH Color System**: Perceptually uniform colors with easy theming
- **Container Queries**: Components respond to container width
- **Native CSS Nesting**: Modern browser nesting with & selector
- **Data-Attribute API**: `data-variant`, `data-size`, `data-elevation` instead of BEM classes
- **New Components**:
  - Dialog (native `<dialog>` support)
  - Navigation patterns
  - Accordion (details/summary)
  - Responsive tables
- **CUBE CSS Layouts**: Stack, Cluster, Sidebar, Switcher, Center, Cover
- **AI Integration**: Documentation and JSON schema for AI code generators

#### Changed
- Replaced 12-column grid with intrinsic responsive grid (auto-fit pattern)
- Migrated to semantic-first zero-class baseline styling
- Updated all components to use data-attributes for variants
- Optimized typography scale and spacing system
- Improved dark mode with better OKLCH color transitions

#### Performance
- **Bundle Size**: 91KB minified, **16KB gzipped** ✅
- Compression ratio: 5.6:1
- Zero JavaScript required
- Lighthouse-ready performance

#### Documentation
- Added `AI_INTEGRATION.md` guide
- Created `symphony-schema.json` for AI tools
- Updated README with modern examples
- Removed outdated architecture reports

### Breaking Changes
- Grid system changed from 12-column to intrinsic responsive
- Some utility classes replaced with data-attributes
- CSS custom properties renamed to `--symphony-*` prefix

### Migration Guide
For users upgrading from v0.1.x:
- Replace `.col-*` classes with semantic grid
- Update button variants: `.btn-primary` → `<button data-variant="primary">`
- Review custom CSS that relied on old variable names

---

## [0.1.0] - Initial Release

- Basic component library
- 12-column grid system
- Semantic HTML styling
