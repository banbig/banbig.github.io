# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **AstroWind**, a production-ready website template built with:
- **Astro 5.0** - Modern static site generator with component islands architecture
- **Tailwind CSS** - Utility-first CSS framework with dark mode support
- **TypeScript** - Type-safe development
- **MDX** - Markdown with JSX for rich blog content

The project is configured for static site generation (`output: 'static'`) and includes a blog system with content collections.

## Development Commands

| Command | Purpose |
|---------|---------|
| `npm install` | Install dependencies |
| `npm run dev` | Start development server at `localhost:4321` |
| `npm run build` | Build for production to `./dist/` |
| `npm run preview` | Preview production build locally |
| `npm run check` | Run all checks (Astro, ESLint, Prettier) |
| `npm run check:astro` | Check Astro files for errors |
| `npm run check:eslint` | Check code with ESLint |
| `npm run check:prettier` | Check code formatting |
| `npm run fix` | Auto-fix ESLint and format with Prettier |
| `npm run fix:eslint` | Auto-fix ESLint issues |
| `npm run fix:prettier` | Auto-format code with Prettier |

**Always run `npm run check` before committing to ensure code quality.**

## Project Architecture

### Configuration Files
- **`src/config.yaml`** - Main site configuration (SEO metadata, blog settings, analytics)
- **`astro.config.ts`** - Astro configuration with integrations and build settings
- **`src/navigation.ts`** - Header and footer navigation structure
- **Path alias**: `~/*` maps to `src/*` for clean imports

### Directory Structure
```
src/
├── components/           # Reusable Astro components
│   ├── blog/            # Blog-specific components
│   ├── common/          # Shared components (Analytics, Meta, etc.)
│   ├── ui/              # UI primitives (Button, Form, etc.)
│   └── widgets/         # Page sections (Hero, Features, etc.)
├── content/config.ts    # Content collections schema
├── data/post/           # Blog posts (MDX/Markdown)
├── layouts/             # Page layout templates
├── pages/               # File-based routing
├── utils/               # Utility functions
└── assets/              # Static assets requiring processing
```

### Key Architectural Patterns

#### Content Collections
Blog posts use Astro's content collections system:
- Posts are stored in `src/data/post/` as `.md` or `.mdx` files
- Schema defined in `src/content/config.ts` with frontmatter validation
- Support for categories, tags, publish dates, and SEO metadata

#### Component Organization
- **Widgets**: Large page sections (Hero, Features, Footer, etc.)
- **UI Components**: Reusable primitives with consistent styling
- **Common Components**: Shared functionality (meta tags, analytics, theme toggle)
- **Blog Components**: Blog-specific layouts and functionality

#### Utility Functions
- **`src/utils/permalinks.ts`** - URL generation and routing logic
- **`src/utils/blog.ts`** - Blog post processing and filtering
- **`src/utils/utils.ts`** - General utilities (date formatting, number formatting)

#### Styling System
- Tailwind CSS with custom configuration in `tailwind.config.js`
- Dark mode support with system preference detection
- Custom styles in `src/components/CustomStyles.astro`
- Typography plugin for rich content formatting

#### SEO and Performance
- Automatic sitemap generation
- Open Graph and Twitter meta tags
- Image optimization with Astro Assets and Unpic
- RSS feed generation for blog posts
- Compression and minification in production

### Development Notes
- Uses file-based routing with dynamic routes for blog categories and tags
- TypeScript strict mode enabled with custom path aliases
- ESLint configured for Astro, TypeScript, and JSX files
- Prettier for consistent code formatting
- Content is prerendered at build time for optimal performance