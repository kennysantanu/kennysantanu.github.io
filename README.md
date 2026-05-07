# Kenny Santanu Portfolio Website

This is the source code for Kenny Santanu's personal portfolio website, built with SvelteKit, TypeScript, and Tailwind CSS. The site showcases projects, skills, and experience in a modern, responsive, and accessible layout.

## Features

- **SvelteKit**: Modern frontend framework for fast, reactive web apps
- **TypeScript**: Type-safe development for maintainable code
- **Tailwind CSS**: Utility-first CSS for rapid UI development
- **Responsive Design**: Optimized for all devices
- **Accessibility**: Designed for a great user experience
- **Project Highlights**: Showcases real-world projects with technology badges

## Project Structure

- `src/` — Main source code
  - `routes/` — SvelteKit routes (main page: `+page.svelte`)
  - `lib/` — Shared components and utilities
  - `app.css` — Global styles
- `static/` — Static assets (images, icons)
- `build/` — Production build output
- `svelte.config.js`, `vite.config.ts` — Project configuration
- `tsconfig.json` — TypeScript configuration

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v16+ recommended)
- [npm](https://www.npmjs.com/) or [pnpm](https://pnpm.io/)

### Installation

```bash
npm install
```

### Development

```bash
npm run dev
```

Open your browser at [http://localhost:5173](http://localhost:5173) (or as indicated in the terminal).

### Build for Production

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

## Deployment

The site is built with `@sveltejs/adapter-static` and outputs fully pre-rendered static files to `build/`, making it compatible with GitHub Pages, Vercel, Netlify, and any static host.

### Automatic (GitHub Actions)

Every push to `main` triggers the workflow in `.github/workflows/deploy.yml`, which:

1. Installs dependencies and runs `npm run build`.
2. Copies `CNAME` and `.nojekyll` into the build output.
3. Force-pushes the contents of `build/` to the `pages-main` branch.

In GitHub **Settings → Pages**, set the source to `Deploy from a branch`, pick `pages-main`, and folder `/ (root)`. The live site updates automatically on every push.

### Manual

```bash
npm run build
```

Then deploy the contents of the `build/` directory to any static host.

## Credits

- [SvelteKit](https://kit.svelte.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Skeleton UI](https://www.skeleton.dev/) (for some UI components)
- [Supabase](https://supabase.com/) (used in some projects)
- [AG Grid](https://www.ag-grid.com/) (used in some projects)
