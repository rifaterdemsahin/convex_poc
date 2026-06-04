# 4️⃣ Formula — Thinking & Planning

> **Stage 4 of 7:** Think and plan before acting. Mandatory gate before writing Convex functions.

## Purpose

Document the reasoning, approach, and design decisions for each Convex feature **before** writing code in `5_Symbols`.

## Files

| File | Description |
|------|-------------|
| [`llm_thinking_log.md`](llm_thinking_log.md) | LLM reasoning logged before and after each implementation |
| [`decisions.md`](decisions.md) | Architecture Decision Records — why Convex over alternatives |

## Planning Gate Rule

Before writing any Convex function:
1. Log the intent and approach in `llm_thinking_log.md`
2. Document any design choices in `decisions.md`
3. Only then create/edit files in `5_Symbols`

## Testing Checklist

- [ ] All major Convex design decisions have an ADR entry
- [ ] `llm_thinking_log.md` has an entry for each feature implemented
- [ ] Planning entries predate their corresponding `5_Symbols` commits
