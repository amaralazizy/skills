---
name: nextjs-folder-structure
description: Design and organize Next.js project folder structures following App Router conventions. Use when user asks about Next.js folder structure, organizing routes, or structuring components/hooks/utils in a Next.js project.
---

# Folder Structure (Next.js)

Design clean, scalable Next.js folder structures using App Router conventions.

## Quick Start

A basic Next.js App Router structure:

```
project-root/
├── app/                    # Routes & layouts (only what Next.js needs here)
│   ├── (routes)/           # Route groups
│   │   ├── page.tsx
│   │   └── layout.tsx
│   ├── api/               # API routes
│   ├── loading.tsx
│   ├── error.tsx
│   ├── layout.tsx
│   └── globals.css        # Global styles
├── public/                # Static assets - at ROOT
├── src/                   # Optional - can put app/ directly at root too
│   └── app/
├── package.json
├── tsconfig.json
├── next.config.ts
└── postcss.config.mjs
```

**Default after `create-next-app`**: Just `app/` inside `src/` with `page.tsx`, `layout.tsx`, `globals.css`, and `favicon.ico`. Add other folders only when needed.

**Important rules**:
- **Inside `app/`**: Only files Next.js needs to handle routes/layouts (page.tsx, layout.tsx, loading.tsx, error.tsx, not-found.tsx, route.ts). Everything else works fine outside `app/`.
- **Outside `app/`**: components, hooks, lib, services, types—put these at src/ root or alongside app/. They don't need to be in app/ to work.
- **`public/`**: Goes at project root, not inside src/. Next.js serves it from `/` automatically.
- **`middleware.ts` / `proxy.ts`**: In src/ (not root or app/). Next.js 16 uses `proxy.ts` instead of `middleware.ts`.
- **`.env*` files**: At root, not in app/. Next.js loads them automatically.
- **Lazy components**: Use `next/dynamic` for code splitting, keep lazy components in `components/` (not app/).
- **Suspense boundaries**: Use `loading.tsx` in app/ routes to enable streaming.

## Workflows

### 1. Analyze requirements
Ask the user:
- What routes/pages are needed?
- Any API endpoints?
- Shared vs feature-specific components?
- External services/integrations?

### 2. Propose structure
Present a folder tree with rationale:
- Group by feature for large apps
- Keep shared utilities at root
- Use `(routes)` groups for shared layouts
- Co-locate related files (component + tests + types)

### 3. Explain decisions
For each section, explain:
- Why this separation
- When to add more directories
- Common patterns to follow

## Patterns

| Pattern | Use When |
|---------|----------|
| `(routes)` groups | Multiple routes share layout |
| `features/` | Complex app with many domains |
| `app/api/` | Backend-for-frontend or API routes |
| `lib/` | Singleton utilities (auth, DB) |
| `hooks/` | Shared custom hooks |

## Advanced

For scaling: See [REFERENCE.md](REFERENCE.md) for enterprise patterns, monorepo setups, and scaling strategies.
