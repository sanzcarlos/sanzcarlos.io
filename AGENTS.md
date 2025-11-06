# Repository Guidelines

## Project Structure & Module Organization
- Source lives in `src/`:
  - `src/pages/` routes (`.astro`), kebab-case (e.g., `about/index.astro`).
  - `src/components/` reusable components, PascalCase (e.g., `Welcome.astro`).
  - `src/layouts/` shared page layouts.
  - `src/assets/` images/svg used by components.
- Static files in `public/` are served at `/`.
- Build output goes to `dist/`.

## Build, Test, and Development Commands
- `pnpm install` — install dependencies.
- `pnpm dev` — start dev server at `http://localhost:4321`.
- `pnpm build` — produce production build into `dist/`.
- `pnpm preview` — serve the built site locally.
- `pnpm astro check` — run Astro diagnostics/type checks.

## Coding Style & Naming Conventions
- Indentation: 4 spaces; keep lines concise; prefer descriptive names.
- Components: PascalCase in `src/components/` (e.g., `HeroBanner.astro`).
- Pages: kebab-case in `src/pages/` (e.g., `blog-post.astro`).
- Assets: lowercase-hyphen names in `src/assets/` and `public/`.
- Keep components focused; prefer server-rendered content and Astro islands only when needed.
- TypeScript config is strict via `tsconfig.json`; fix type warnings before merging.

## Testing Guidelines
- No test runner is configured yet. If adding tests:
  - Unit: prefer Vitest for utility modules.
  - E2E: prefer Playwright for core routes.
  - Mirror structure under `tests/` (e.g., `tests/pages/index.spec.ts`).
  - Aim for smoke coverage on key pages (home, critical layouts).

## Commit & Pull Request Guidelines
- Current history has no set convention; use Conventional Commits:
  - `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `perf:`, `test:`
  - Example: `feat(components): add HeroBanner with CTA`
- PRs should include:
  - Clear description and motivation; link issues.
  - Screenshots/GIFs of UI changes.
  - Steps to verify locally (commands, pages to visit).
  - Small, focused diffs; update docs when needed.

## Security & Configuration Tips
- Do not commit secrets. Use `.env` files (git-ignored) and access via Astro environment APIs.
- Keep `astro.config.mjs` minimal; prefer static assets and lightweight client JS.
- Validate external links/assets in PRs to avoid broken content.
