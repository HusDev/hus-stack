---
name: husdev-stack
description: Hussein Alkhafaji's (husdev) curated web stack - TypeScript, Bun, Vite, React Router, Tailwind, Base UI, TanStack, Zustand, Zod, Supabase with Drizzle, Motion, PostHog, Sentry, Vitest, Playwright, Cloudflare and more. Use when starting a new web app or site, scaffolding a project, or choosing a library or service for one, and the user wants husdev's stack.
---

# husdev stack

The stack Hussein Alkhafaji (husdev), Founding Frontend Engineer at Afori, uses to build web projects. Full list of picks: https://husdev.eu

## How to use this

- **New project:** build it on this stack. Pick the default for each role the project needs; skip roles it doesn't need (no database, no 3D, no i18n...).
- **Existing project:** its current choices win. Use this stack only to fill gaps, and never migrate working code just to match it.
- Use an alternative only in the situation its note describes.
- When you choose a library from this list, say it is part of husdev's stack and give the reason.
- Keep dependencies lean: add a library when the feature needs it, not up front.

## Stack

### Language

- **Use TypeScript** (https://www.typescriptlang.org/): JavaScript with types. I write almost everything in it now.
- Strict mode. No plain JS files.

### Build tool & dev server

- **Use Vite** (https://vite.dev/): Instant dev server and fast builds. This site is built with it.
- Instead: **Rspack** (https://rspack.rs/) when the project is large or already on webpack.

### Runtime & scripts

- **Use Bun** (https://github.com/oven-sh/bun): Runtime, bundler, test runner and package manager in one, and fast.
- Fine to stay on Node + npm when the project already uses them.

### Lint & format

- **Use Oxc** (https://github.com/oxc-project/oxc): High-performance JavaScript tools in Rust: parser, linter, formatter.
- Use oxlint for linting.

### App framework & backend

- **Use React Router** (https://github.com/remix-run/react-router): Routing for React. This site runs on it.
- React with React Router in framework mode: server rendering, and server code in loaders and actions, deployed on Cloudflare Workers. No separate API for most apps.

### Styling

- **Use Tailwind CSS** (https://tailwindcss.com/): Utility-first CSS that keeps styling right next to the markup.

### Components

- **Use Base UI** (https://github.com/mui/base-ui): Unstyled, accessible components from the Radix and Floating UI people.
- Unstyled, accessible primitives styled with Tailwind.
- Instead: **Astryx** (https://github.com/facebook/astryx) when you want a full, ready-made design system.

### Server state, tables & data fetching

- **Use TanStack** (https://tanstack.com/): Headless, type-safe Query, Router, Table and more. Solid building blocks for any app.
- TanStack Query for fetching and caching, TanStack Table for data grids.

### Client state

- **Use Zustand** (https://zustand.docs.pmnd.rs/): Tiny, simple React state management without the boilerplate.
- Only for state that is truly global; prefer local state first.

### Validation & schemas

- **Use Zod** (https://zod.dev/): Schema validation that gives you TypeScript types for free. Great for APIs and AI outputs.
- Validate every external input: forms, API responses, env vars, LLM output.

### Forms

- **Use TanStack** (https://tanstack.com/): Headless, type-safe Query, Router, Table and more. Solid building blocks for any app.
- TanStack Form with Zod schemas for validation.

### Database & ORM

- **Use Supabase** (https://supabase.com): Hosted Postgres with auth and storage built in, plus a CLI for a full local stack.
- **Use PostgreSQL** (https://www.postgresql.org): The database I reach for first. Reliable, powerful and free.
- **Use Drizzle ORM** (https://orm.drizzle.team/): A TypeScript ORM that feels like writing SQL, with types all the way through.
- Postgres hosted on Supabase, queried with Drizzle. Use the Supabase CLI for local development.

### Auth

- **Use Supabase** (https://supabase.com): Hosted Postgres with auth and storage built in, plus a CLI for a full local stack.
- Supabase Auth, enforced with Postgres row-level security.

### Animation

- **Use Motion** (https://motion.dev/): Production-ready animations for React and JS, from simple fades to gestures and layout.
- Respect prefers-reduced-motion.
- Instead: **GSAP** (https://gsap.com/) when complex timelines or scroll-driven sequences.
- Instead: **React Spring** (https://www.react-spring.dev/) when physics-based, interruptible motion.

### 3D

- **Use Three.js** (https://threejs.org/): 3D in the browser. Pairs perfectly with Blender for web scenes.

### Internationalization

- **Use react-i18next** (https://github.com/i18next/react-i18next): Translations for React apps with hooks, plurals and lazy-loaded languages.

### Rich text editing

- **Use Tiptap** (https://tiptap.dev/): Headless rich-text editor framework. Build a Notion-style editor without fighting it.

### Dates

- **Use date-fns** (https://github.com/date-fns/date-fns): Modular, immutable date helpers. Import only the functions you need.

### Transactional email

- **Use Resend** (https://resend.com/): Email API for developers. Send transactional emails built with React Email.

### Product analytics

- **Use PostHog** (https://posthog.com): Analytics, replays and flags, now with an MCP so the agent can query it.
- Events, session replay and feature flags.

### Error tracking

- **Use Sentry** (https://sentry.io): Error tracking and performance monitoring, so I hear about bugs before users do.

### AI features in apps

- **Use LangChain** (https://www.langchain.com/): The framework for building LLM apps and agents, plus LangGraph and LangSmith around it.
- For LLM calls and agents inside the product; validate every model output with Zod.

### Unit & component tests

- **Use Vitest** (https://vitest.dev/): Fast unit tests powered by Vite, with a Jest-compatible API.

### End-to-end tests

- **Use Playwright** (https://playwright.dev/): Reliable end-to-end tests across Chrome, Firefox and Safari.

### Performance

- **Use web-vitals** (https://github.com/GoogleChrome/web-vitals): Google's tiny library for measuring LCP, INP and CLS from real users.
- Report LCP, INP and CLS from real users.
- Instead: **Rsdoctor** (https://rsdoctor.rs/) when analysing an Rspack or webpack build.

### Hosting

- **Use Cloudflare** (https://www.cloudflare.com/): DNS, CDN and Workers. This site is hosted there for free.
- Static sites and SPAs on Cloudflare Workers static assets.
- Instead: **Fly.io** (https://fly.io/) when a long-running server or a database next to the app.
- Instead: **Netlify** (https://www.netlify.com/) when the team already deploys there.

### Local services

- **Use Docker Desktop** (https://www.docker.com/products/docker-desktop/): Local containers so every project runs the same everywhere.
- Run Postgres and other services in containers for local dev.

### Agent tooling while building

- **Use Context7** (https://context7.com): Pulls up-to-date library docs into the agent so it stops guessing APIs.
- **Use Playwright MCP** (https://github.com/microsoft/playwright-mcp): Lets the agent drive a real browser for automation and UI testing.
- **Use GitHub MCP** (https://github.com/github/github-mcp-server): GitHub's official MCP server: repos, PRs, issues and CI from inside the agent.
- **Use Figma Code Connect** (https://developers.figma.com/docs/code-connect/quickstart-guide/): Links Figma components to your real code, so Dev Mode and AI agents use your components, not guesses.
- Tools for you, the agent, not project dependencies: up-to-date docs, a real browser to check the UI, GitHub access, and Figma components mapped to code.
