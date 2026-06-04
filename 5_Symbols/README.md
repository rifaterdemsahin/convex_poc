# 5️⃣ Symbols — Convex Source Code

> **Stage 5 of 7:** The actual Convex functions and schema — where vision becomes working software.

## Files

| File | Description |
|------|-------------|
| [`convex_schema.md`](convex_schema.md) | TypeScript schema definition with indexes |
| [`convex_queries.md`](convex_queries.md) | Reactive query functions |
| [`convex_mutations.md`](convex_mutations.md) | Transactional mutation functions |

## Convex Project Structure

```
convex/
├── schema.ts          # Database schema definition
├── messages.ts        # Query and mutation functions
└── _generated/        # Auto-generated type files (git-ignored)
```

## Code Standards

- All functions use `v.` validators from `convex/values`
- Queries are pure (no side effects) — safe to re-run reactively
- Mutations use transactions — never partial writes
- Actions are used only for external API calls

## Testing Checklist

- [ ] Schema validates correctly — `npx convex dev` starts without errors
- [ ] `listMessages` query returns results in Convex dashboard
- [ ] `sendMessage` mutation creates a document
- [ ] `deleteMessage` mutation removes by ID
- [ ] No secrets in any file in this folder
