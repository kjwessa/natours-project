# Natours Landing Page

A polished marketing site for a fictional outdoor adventure company. The project focuses on modern CSS/Sass techniques, responsive layouts, and performance-friendly animations.

## Features
- Fully responsive single-page layout built with semantic HTML5.
- Component-driven Sass architecture (7-1 pattern) compiled to optimized CSS.
- Animated hero section, cards, stories, and booking form showcasing advanced CSS effects.
- Build tooling for development (live reload + Sass watcher) and production-ready CSS builds with autoprefixing and minification.

## Tech Stack
- **HTML5** for structure and accessibility.
- **Sass (SCSS syntax)** to organize styles and enable reusable variables/mixins.
- **Node.js toolchain** with `node-sass`, `postcss` (autoprefixer), and `npm-run-all`.
- **live-server** for local development with automatic reloads.

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v12 or later recommended)
- npm (comes with Node.js)

### Installation
```bash
npm install
```

### Development workflow
Start a local dev server and watch Sass files for changes:
```bash
npm start
```
This runs `live-server` alongside `node-sass` in watch mode, compiling `sass/main.scss` into `css/style.css`.

### Production build
Generate an optimized CSS bundle suitable for deployment:
```bash
npm run build:css
```
This command compiles Sass, concatenates icon fonts, applies vendor prefixes for the last 10 browser versions, and outputs a compressed `css/style.css`.

## Project Structure
```
.
├── index.html          # Landing page markup
├── sass/               # Source Sass files (abstracts, base, components, layout, pages, themes)
├── css/                # Compiled CSS outputs and icon font styles
├── img/                # Optimized images used throughout the page
└── package.json        # npm scripts and build tooling configuration
```

## Customization Tips
- Update colors, typography, and spacing in `sass/abstracts/_variables.scss`.
- Add or adjust reusable mixins in `sass/abstracts/_mixins.scss`.
- Modify section-specific styles within the relevant files under `sass/layout` or `sass/pages`.
- Re-run the build commands after making Sass changes to regenerate the compiled CSS.

## License
This project is open source under the ISC License (see `package.json` for details).
