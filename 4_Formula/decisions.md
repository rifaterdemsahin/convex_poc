# Architecture Decisions — Convex.dev PoC

## ADR-001: Convex over Firebase/Supabase

**Date:** 2026-06-04
**Status:** Accepted

**Context:** Need a real-time backend for a PoC that demonstrates reactive data without WebSocket boilerplate.

**Decision:** Use Convex.dev

**Reasons:**
- TypeScript-first schema with end-to-end type safety (vs. Firebase's loosely typed SDK)
- Reactive queries with automatic re-subscription (vs. Supabase's manual subscription setup)
- ACID transactions with optimistic updates built in
- Time-travel debugging in dashboard — invaluable for a PoC
- No server to manage; scales to zero

**Trade-offs:**
- Smaller ecosystem than Firebase
- Vendor lock-in for the DB layer
- Less mature than Supabase for SQL-style queries

---

## ADR-002: Azure Key Vault for Secrets

**Date:** 2026-06-04
**Status:** Accepted

**Context:** Convex deploy key must not be committed to git.

**Decision:** Store `CONVEX-DEPLOY-KEY` in Azure Key Vault `dp-kv-deliverypilot`

**Reasons:**
- Enterprise-grade FIPS 140-2 validated HSMs
- Native GitHub Actions integration via `Azure/get-keyvault-secrets`
- Audit logs track every secret access
- Free tier sufficient for PoC (~$0/month at < 10K operations)

---

## ADR-003: Static GitHub Pages for Documentation

**Date:** 2026-06-04
**Status:** Accepted

**Context:** Need to publish PoC documentation and showcase without a backend.

**Decision:** Use GitHub Pages with the 7-stage template structure

**Reasons:**
- Free hosting, no infra to manage
- Markdown files rendered client-side via `marked.js`
- Navigation config in JSON — easy to update without touching HTML
