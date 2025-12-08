# Symphony Core Build

## Utilidades Removidas para Optimización

El build **Core** de Symphony Anthology v1.0 reduce el tamaño gzipped de **16.25KB a 14.99KB** (bajo el objetivo de 15KB) eliminando utilidades menos usadas mientras mantiene toda la funcionalidad esencial.

### 📦 Comparación de Tamaños

| Build | Minified | Gzipped | Reducción |
|-------|----------|---------|-----------|
| **Full** | 93KB | 16.25KB | baseline |
| **Core** | 85.7KB | 14.99KB | **-1.26KB (-7.7%)** |

### ❌ Utilidades Removidas

#### Helpers (`_helpers.core.css`)
- ~~`.contents`~~ (display: contents)
- ~~`.visible`~~ (visibility: visible - redundante)
- ~~`.collapse`~~ (visibility: collapse)
- ~~`.inset-auto`~~ (poco usado)
- ~~`.top-0`, `.bottom-0`, `.start-0`, `.end-0`~~ (usar `.inset-0` en su lugar)
- ~~`.z-40`~~ (saltos de z-index)
- ~~`.z-sticky`, `.z-fixed`~~ (solo semánticos necesarios)
- ~~`.w-screen`, `.min-w-full`, `.max-w-none`~~ (edge cases)
- ~~`.overflow-clip`, `.overflow-scroll`, `.overflow-x-scroll`, `.overflow-y-scroll`~~
- ~~`.overflow-x-auto`, `.overflow-x-hidden`~~ (usar overflow directo)
- ~~`.rounded-md`~~ (duplicado de `.rounded`)
- ~~`.rounded-xl`, `.rounded-2xl`~~ (tamaños extremos)
- ~~`.border-2`~~ (solo 1px necesario)
- ~~`.border-transparent`, `.border-warning`~~ (poco usados)
- ~~`.shadow-md`~~ (duplicado de `.shadow`)
- ~~`.shadow-xl`, `.shadow-2xl`~~ (sombras muy grandes)
- ~~`.opacity-25`, `.opacity-75`~~ (solo 0, 50, 100)

#### Spacing (`_spacing.core.css`)
- ~~`.m-2xl`, `.m-3xl`~~ (espaciados muy grandes)
- ~~`.mi-xl`, `.mi-2xl`~~ (inline márgenes grandes)
- ~~`.mb-2xl`~~ (block margin muy grande)
- ~~`.mis-*`, `.mie-*`~~ (márgenes inline individuales - usar `.mi-*`)
- ~~`.mbs-xs`, `.mbs-xl`, `.mbs-auto`~~ (solo sm/md/lg comunes)
- ~~`.mbe-xs`, `.mbe-xl`, `.mbe-auto`~~ (solo sm/md/lg comunes)
- ~~`.p-2xl`, `.p-3xl`~~ (padding muy grande)
- ~~`.pis-*`, `.pie-*`~~ (padding inline individual - usar `.pi-*`)
- ~~`.pbs-xs`, `.pbs-xl`~~ (solo sm/md/lg comunes)
- ~~`.pbe-xs`, `.pbe-xl`~~ (solo sm/md/lg comunes)
- ~~`.gap-y-xs`, `.gap-y-xl`~~
- ~~`.gap-x-xs`, `.gap-x-xl`~~

### ✅ Utilidades Conservadas (100% funcionales)

#### Display & Layout
✅ `.block`, `.inline-block`, `.inline`, `.flex`, `.inline-flex`, `.grid`, `.inline-grid`, `.hidden`, `.invisible`

#### Position
✅ `.static`, `.relative`, `.absolute`, `.fixed`, `.sticky`, `.inset-0`

#### Z-Index
✅ `.z-0` a `.z-50`, `.z-dropdown`, `.z-modal`, `.z-tooltip`

#### Sizing
✅ `.w-full`, `.w-auto`, `.h-full`, `.h-auto`, `.h-screen`  
✅ `.min-w-0`, `.max-w-full`, `.max-w-prose`  
✅ `.min-h-0`, `.min-h-full`, `.min-h-screen`  
✅ `.max-h-full`, `.max-h-screen`, `.size-full`

#### Overflow
✅ `.overflow-auto`, `.overflow-hidden`, `.overflow-visible`  
✅ `.overflow-y-auto`, `.overflow-y-hidden`

#### Border & Radius
✅ `.border`, `.border-0`  
✅ `.border-primary`, `.border-success`, `.border-danger`  
✅ `.rounded-none`, `.rounded-sm`, `.rounded`, `.rounded-lg`, `.rounded-full`

#### Shadows
✅ `.shadow-none`, `.shadow-sm`, `.shadow`, `.shadow-lg`

#### Backgrounds
✅ `.bg-transparent`, `.bg-surface`, `.bg-surface-alt`, `.bg-background`  
✅ `.bg-primary`, `.bg-secondary`, `.bg-success`, `.bg-warning`, `.bg-danger`

#### Opacity
✅ `.opacity-0`, `.opacity-50`, `.opacity-100`

#### Interactivity
✅ `.cursor-pointer`, `.cursor-not-allowed`  
✅ `.pointer-events-none`, `.pointer-events-auto`  
✅ `.select-none`, `.select-text`

#### Transitions
✅ `.transition`, `.transition-colors`, `.transition-none`

#### Accessibility
✅ `.sr-only`, `.not-sr-only`, `.focus-visible`

#### Spacing (Esencial)
✅ Margin: `.m-{0,xs,sm,md,lg,xl,auto}`  
✅ Margin Inline: `.mi-{0,xs,sm,md,lg,auto}`  
✅ Margin Block: `.mb-{0,xs,sm,md,lg,xl,auto}`  
✅ Margin Block Start: `.mbs-{0,sm,md,lg}`  
✅ Margin Block End: `.mbe-{0,sm,md,lg}`  
✅ Padding: `.p-{0,xs,sm,md,lg,xl}`  
✅ Padding Inline: `.pi-{0,xs,sm,md,lg,xl}`  
✅ Padding Block: `.pb-{0,xs,sm,md,lg,xl}`  
✅ Padding Block Start/End: `.pbs-{0,sm,md,lg}`, `.pbe-{0,sm,md,lg}`  
✅ Gap: `.gap-{0,xs,sm,md,lg,xl}`  
✅ Gap Y/X: `.gap-y-{0,sm,md,lg}`, `.gap-x-{0,sm,md,lg}`

## 🚀 Uso

### Instalar Core Build (Recomendado para producción)
```html
<!-- CDN (Cuando esté disponible) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@symphonyui/symphonycss@1/dist/symphony.core.min.css">

<!-- NPM -->
import '@symphonyui/symphonycss/dist/symphony.core.min.css';
```

### Full Build (Desarrollo / Máxima flexibilidad)
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@symphonyui/symphonycss@1/dist/symphony.min.css">
```

## 🎯 Cuándo usar cada build

| Escenario | Build Recomendado |
|-----------|-------------------|
| **Producción** | Core (14.99KB) |
| **Aplicaciones web pequeñas/medianas** | Core |
| **Landing pages** | Core |
| **Prototipos rápidos** | Full (16.25KB) |
| **Aplicaciones complejas** | Full |
| **Necesitas todas las variantes de spacing** | Full |

## 📝 Notas

- **Todos los componentes están incluidos** en ambos builds (buttons, forms, cards, etc.)
- **Todo el sistema de diseño está intacto** (colores OKLCH, tokens, variables)
- **Layouts CUBE CSS completos** (.stack, .cluster, .sidebar, .grid, .container)
- Solo se optimizaron **utilidades auxiliares** poco usadas
- Migrar de Full → Core es **100% seguro** si no usas las utilidades listadas arriba

## 🔄 Scripts NPM

```bash
# Build completo (genera Full + Core + Themes)
npm run build

# Solo Core build
npm run build:core

# Comparar tamaños
npm run size:compare

# Ver tamaño Core
npm run size:core

# Ver tamaño Full
npm run size
```
