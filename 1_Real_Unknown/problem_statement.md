# Problem Statement

## Core Problem

Building real-time collaborative applications traditionally requires significant WebSocket boilerplate, manual cache invalidation, complex state synchronisation, and separate backend infrastructure. These concerns consume development time that should go to product logic.

## Hypothesis

Convex.dev eliminates this overhead by providing:
- Reactive queries that automatically push updates to clients
- ACID-compliant mutations that handle optimistic updates
- A TypeScript-first schema that eliminates runtime type errors
- Zero-config serverless deployment

## Who Benefits

- **Solo developers** building MVPs — ship real-time features in hours, not days
- **Small teams** — reduce DevOps overhead; no WebSocket server to maintain
- **Enterprises evaluating alternatives** to Firebase/Supabase with stronger TypeScript guarantees

## Success Criteria

A successful PoC will prove that a real-time message board (create, read, delete) can be built with Convex in under 2 hours with zero custom WebSocket code.
