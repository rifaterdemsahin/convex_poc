# Convex Queries — Reactive Data Fetching

Queries are **pure, reactive functions** that run on the Convex runtime. They automatically re-execute and push results to all subscribed clients when underlying data changes.

## `convex/messages.ts` — Query Functions

```typescript
import { query } from "./_generated/server";
import { v } from "convex/values";

// List all messages, newest first
export const listMessages = query({
  args: {},
  handler: async (ctx) => {
    return await ctx.db
      .query("messages")
      .order("desc")
      .take(50);
  },
});

// List messages by channel
export const listByChannel = query({
  args: { channel: v.string() },
  handler: async (ctx, args) => {
    return await ctx.db
      .query("messages")
      .withIndex("by_channel", (q) => q.eq("channel", args.channel))
      .order("desc")
      .take(100);
  },
});

// Get a single message by ID
export const getMessage = query({
  args: { id: v.id("messages") },
  handler: async (ctx, args) => {
    return await ctx.db.get(args.id);
  },
});
```

## React Integration

```tsx
import { useQuery } from "convex/react";
import { api } from "../convex/_generated/api";

function MessageBoard() {
  // Reactive — re-renders automatically when data changes
  const messages = useQuery(api.messages.listMessages);

  if (messages === undefined) return <p>Loading...</p>;

  return (
    <ul>
      {messages.map((msg) => (
        <li key={msg._id}>
          <strong>{msg.author}</strong>: {msg.text}
        </li>
      ))}
    </ul>
  );
}
```

## Key Properties of Convex Queries

| Property | Details |
|----------|---------|
| **Reactive** | All subscribed clients receive updates the moment data changes |
| **Pure** | Queries have no side effects — they only read |
| **Cached** | Convex caches query results; identical args return instantly |
| **Type-safe** | Return type is inferred from schema — no casting needed |
| **No polling** | WebSocket subscription managed automatically by the SDK |
