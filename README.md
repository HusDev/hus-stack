# hus-stack

The web stack [Hussein Alkhafaji (husdev)](https://husdev.eu) uses to build projects, packaged as a Claude Code skill. Install it and your agent builds new apps with these tools, and says why it picked each one.

TypeScript · Bun · Vite · React Router (framework mode) · Tailwind CSS · Base UI · TanStack · Zustand · Zod · Supabase + Drizzle · Motion · PostHog · Sentry · Vitest · Playwright · Cloudflare, and more. See the full list in [SKILL.md](plugins/hus-stack/skills/hus-stack/SKILL.md).

## Install

In Claude Code (2.1.275 or later):

```
/plugin install hus-stack --marketplace HusDev/hus-stack
```

On older versions:

```
/plugin marketplace add HusDev/hus-stack
/plugin install hus-stack@hus-stack
```

## How it behaves

- **New project:** the agent builds on this stack, using the default for each part the project needs and skipping the rest.
- **Existing project:** the project's current choices win. The skill only fills gaps and never migrates working code.
- Alternatives are used only in the situations they describe (for example GSAP for complex timelines, Fly.io for long-running servers).

## Where it comes from

`SKILL.md` is generated from the picks on [husdev.eu](https://husdev.eu) and synced here automatically on every deploy of [HusDev/husdev.eu](https://github.com/HusDev/husdev.eu). Don't edit it here; change `src/data/stack.ts` in that repo.

## License

MIT
