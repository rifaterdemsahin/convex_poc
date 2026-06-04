# Hypotheses

Initial assumptions to validate against evidence in `7_Testing_Known`.

| ID | Hypothesis | Validation Method | Result |
|----|------------|-------------------|--------|
| H1 | Real-time UI updates work with zero WebSocket code | Build a message board; count WebSocket lines | ⬜ |
| H2 | TypeScript schema prevents runtime type errors | Intentionally pass wrong type; observe compile error | ⬜ |
| H3 | Convex deploy key can be stored in Azure Key Vault | `az keyvault secret set` + runtime retrieval | ⬜ |
| H4 | A CRUD feature takes < 30 minutes to build | Time the message board implementation | ⬜ |
| H5 | Convex query latency is < 100ms in practice | Measure with browser dev tools | ⬜ |
