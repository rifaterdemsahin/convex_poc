# 3️⃣ Simulation — Convex PoC Mockups

> **Stage 3 of 7:** Make the invisible visible before writing production code.

## Purpose

Visual representations of what the Convex PoC demo pages will look like and how real-time data flow will appear to the user.

## Planned Mockups

| Mockup | Description |
|--------|-------------|
| `mockup_realtime_board.png` | Real-time message board — messages appear instantly |
| `mockup_schema_view.png` | Schema visualisation — tables, fields, indexes |
| `mockup_dashboard.png` | Convex dashboard time-travel debugging view |

## User Journey

1. User lands on home page → sees PoC feature list and live status indicator
2. User clicks **Queries** → reads reactive query code with syntax highlighting
3. User clicks **Mutations** → reads mutation code and sees type-safe patterns
4. User clicks **Architecture** → views Mermaid system diagram

## Carousel Slides (current)

The `index.html` carousel shows:
1. Real-Time Query Demo — live subscription concept
2. Schema Definition — TypeScript schema preview
3. Serverless Actions — background job concept
4. Auth Integration — identity flow

## Testing Checklist

- [ ] Carousel cycles through all 4 slides automatically
- [ ] User journey is achievable via top navigation
- [ ] All mockup descriptions match actual implemented pages
