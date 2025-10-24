# Natours Landing Page

A modern, fully responsive marketing site for a fictional outdoor adventure company. Built with cutting-edge web technologies and optimized for deployment on Cloudflare Workers.

## Features

- Fully responsive single-page layout with semantic HTML5
- Modern Sass module system using `@use` instead of deprecated `@import`
- Component-driven architecture following the 7-1 pattern
- Animated hero section, flip cards, stories, and booking form
- Lightning-fast dev experience with Vite HMR (Hot Module Replacement)
- Production-optimized builds with automatic code splitting
- Code quality enforcement with Biome

## Tech Stack

- **Vite 7** - Next-generation frontend tooling with instant HMR
- **Sass (Modern Module System)** - Using `@use`/`@forward` for better encapsulation
- **sass-embedded** - Fast Dart Sass implementation (replaces deprecated node-sass)
- **PostCSS + Autoprefixer** - Automatic vendor prefixing
- **Biome** - Fast linter and formatter for JavaScript/TypeScript
- **pnpm@10.18.1** - Fast, disk space efficient package manager
- **Cloudflare Pages/Workers** - Edge deployment with Workers Static Assets

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v22 or later recommended)
- [pnpm](https://pnpm.io/) v10.18.1 or compatible (required for consistent builds)

> **Note:** This project uses pnpm as specified in the `packageManager` field. Using npm or yarn may cause dependency conflicts.

### Installation

```bash
pnpm install
```

### Development

Start the Vite dev server with hot module replacement:

```bash
pnpm dev
```

The site will open automatically at `http://localhost:5173` with instant hot reload.

### Code Quality

Check code for issues:

```bash
pnpm check
```

Auto-fix issues:

```bash
pnpm fix
```

### Production Build

Build optimized static assets for production:

```bash
pnpm build
```

Preview the production build locally:

```bash
pnpm preview
```

### Deployment

This project is configured for deployment to **Cloudflare Pages**:

- Deployments are triggered automatically on git push
- Build command: `pnpm build`
- Output directory: `dist`
- The `packageManager` field ensures Cloudflare Pages uses pnpm (not npm)

For manual deployments using Cloudflare Workers:

```bash
wrangler deploy
```

The site will be deployed to Cloudflare's global edge network with automatic SSL and CDN.

## Project Structure

```
.
├── index.html              # Main HTML entry point
├── src/
│   └── main.js            # JavaScript entry point (imports styles)
├── sass/                   # Modern Sass with @use modules
│   ├── abstracts/         # Variables, mixins, functions
│   │   └── _index.scss    # Forwards all abstracts
│   ├── base/              # Reset, typography, utilities
│   ├── components/        # Reusable components (buttons, cards, etc.)
│   ├── layout/            # Layout patterns (header, footer, grid)
│   └── pages/             # Page-specific styles
├── css/                    # Static CSS (icon fonts)
├── img/                    # Optimized images and videos
├── dist/                   # Production build output (generated)
├── wrangler.toml          # Cloudflare Workers configuration
├── vite.config.js         # Vite configuration
├── postcss.config.js      # PostCSS configuration
├── biome.json             # Biome linter/formatter config
└── package.json           # Project dependencies and scripts
```

## Sass Architecture

This project uses the modern Sass module system:

- **`@use` instead of `@import`** - Better namespace control and no duplicate CSS
- **`@forward` in abstracts** - Central module that exports variables, mixins, and functions
- **Scoped imports** - Each file imports only what it needs via `@use '../abstracts' as *`

### Key Files

- `sass/abstracts/_variables.scss` - Color palette, typography, grid settings
- `sass/abstracts/_mixins.scss` - Reusable mixins (media queries, clearfix, etc.)
- `sass/abstracts/_index.scss` - Forwards all abstracts as a single module
- `sass/main.scss` - Main entry point that composes all modules

## Customization

### Colors

Update the color palette in `sass/abstracts/_variables.scss`:

```scss
$color-primary: #7ed56f;
$color-primary-light: #55c57a;
$color-primary-dark: #28b485;
```

### Responsive Breakpoints

Modify breakpoint mixins in `sass/abstracts/_mixins.scss`:

```scss
@mixin respond($breakpoint) {
    @if $breakpoint == phone {
        @media only screen and (max-width: 37.5em) { @content }
    }
    // ... more breakpoints
}
```

### Components

All components are modular and can be found in `sass/components/`. Each component file imports abstracts independently.

## Performance

- **Vite's build optimization** - Automatic code splitting, tree shaking, and minification
- **Modern Sass compilation** - sass-embedded is significantly faster than node-sass
- **Edge deployment** - Cloudflare Workers serves content from 300+ locations worldwide
- **Image optimization** - Responsive images with srcset for optimal loading

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Progressive enhancement for older browsers
- Autoprefixer targets last 10 versions

## License

This project is open source under the ISC License.
