# Convex Mutations — Transactional Writes

Mutations are **ACID-transactional** write functions. They either fully succeed or fully roll back. After a mutation commits, all affected queries automatically push updates to their subscribers.

## `convex/messages.ts` — Mutation Functions

```typescript
import { mutation } from "./_generated/server";
import { v } from "convex/values";

// Send a new message
export const sendMessage = mutation({
  args: {
    text: v.string(),
    author: v.string(),
    channel: v.optional(v.string()),
  },
  handler: async (ctx, args) => {
    const messageId = await ctx.db.insert("messages", {
      text: args.text,
      author: args.author,
      channel: args.channel,
    });
    return messageId;
  },
});

// Delete a message by ID
export const deleteMessage = mutation({
  args: { id: v.id("messages") },
  handler: async (ctx, args) => {
    await ctx.db.delete(args.id);
  },
});

// Update message text
export const editMessage = mutation({
  args: {
    id: v.id("messages"),
    text: v.string(),
  },
  handler: async (ctx, args) => {
    await ctx.db.patch(args.id, { text: args.text });
  },
});
```

## React Integration

```tsx
import { useMutation } from "convex/react";
import { api } from "../convex/_generated/api";

function MessageInput() {
  const sendMessage = useMutation(api.messages.sendMessage);

  const handleSubmit = async (text: string) => {
    // Optimistic update happens automatically
    await sendMessage({ text, author: "alice", channel: "general" });
  };

  return (
    <button onClick={() => handleSubmit("Hello, Convex!")}>
      Send Message
    </button>
  );
}
```

## Key Properties of Convex Mutations

| Property | Details |
|----------|---------|
| **ACID** | Fully transactional — partial writes never committed |
| **Optimistic updates** | SDK shows result immediately; rolls back on failure |
| **Reactive trigger** | All queries depending on changed data re-run automatically |
| **Serialised** | Mutations on the same document run serially — no race conditions |
| **Type-safe** | Argument validators (`v.`) enforce types at the Convex boundary |

## Transactional Example

```typescript
// Both inserts succeed or both fail — never partial
export const sendAndLog = mutation({
  args: { text: v.string(), author: v.string() },
  handler: async (ctx, args) => {
    const msgId = await ctx.db.insert("messages", {
      text: args.text,
      author: args.author,
    });
    await ctx.db.insert("audit_log", {
      action: "message_sent",
      targetId: msgId,
      actor: args.author,
    });
    return msgId;
  },
});
```
