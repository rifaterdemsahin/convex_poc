# Validation Report — Convex.dev PoC

Maps each hypothesis from `1_Real_Unknown/hypotheses.md` to evidence.

| ID | Hypothesis | Test Method | Evidence | Result | Date |
|----|------------|-------------|----------|--------|------|
| H1 | Real-time UI with zero WebSocket code | Count WebSocket lines in 5_Symbols | — | ⬜ Pending | — |
| H2 | TypeScript schema prevents runtime type errors | Pass wrong type; observe compile error | — | ⬜ Pending | — |
| H3 | Convex deploy key stored in Azure Key Vault | `az keyvault secret show` returns value | Key stored via `az keyvault secret set` | ✅ Done | 2026-06-04 |
| H4 | CRUD feature takes < 30 minutes | Time implementation | — | ⬜ Pending | — |
| H5 | Query latency < 100ms | Browser dev tools Network tab | — | ⬜ Pending | — |
