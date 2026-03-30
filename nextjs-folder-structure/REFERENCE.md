# Next.js Folder Structure Reference

## Enterprise Patterns

### Feature-Based Structure

```
src/
├── app/
├── components/
│   ├── ui/              # shadcn/ui, buttons, inputs
│   └── features/        # Feature-scoped components
│       ├── auth/
│       ├── dashboard/
│       └── settings/
├── features/            # Feature logic
│   ├── auth/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── types.ts
│   │   └── index.ts
│   └── dashboard/
├── hooks/               # Global shared hooks
├── lib/                 # Global utilities
└── services/            # API clients
```

### Monorepo Structure

```
apps/
├── web/                 # Next.js app
│   ├── src/app/
│   └── package.json
├── shared/              # Shared packages
│   ├── ui/              # Component library
│   └── utils/
└── package.json
```

## Scaling Strategies

1. **Colocation**: Keep tests, types, and styles next to components
2. **Barrels**: Use `index.ts` files for clean imports
3. **Absolute imports**: Configure `tsconfig.json` paths
4. **Domain-driven**: Group by business domain, not file type

## API Routes

```
app/api/
├── auth/[...nextauth]/route.ts
├── users/route.ts
└── users/[id]/route.ts
```

## Testing Structure

```
components/
├── Button/
│   ├── Button.tsx
│   ├── Button.test.tsx
│   └── index.ts
```
