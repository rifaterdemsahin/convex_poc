# LLM Thinking Log — Convex.dev PoC

Each entry is logged **before** implementation and updated **after** with outcomes.

---

## 2026-06-04 — Initial Scaffold

**Intent:** Refactor empty `convex_poc` repo using `delivery-pilot-template` structure. Customise all branding and content for Convex.dev PoC. Store Convex deploy key in Azure Key Vault.

**Approach:**
1. Fetch template files from `rifaterdemsahin/delivery-pilot-template` via GitHub CLI
2. Create all 7 stage folders with Convex-specific content
3. Customise `index.html` with Convex branding (red/orange accent, bolt icon)
4. Create Convex-specific pages: schema, queries, mutations
5. Store deploy key `{"v2":"3ef9720ff1c741e69502e8a261d2bfe4"}` in Azure Key Vault as `CONVEX-DEPLOY-KEY`
6. Commit all structure files, then commit the key vault setup separately

**Design Decisions:**
- Keep template's two-menu architecture (Project Menu + Debug Menu) — it provides good separation between user-facing and developer navigation
- Use red/orange colour scheme (Convex brand colours) instead of violet/cyan
- Project Menu focuses on Convex features: Queries, Mutations, Architecture
- Debug Menu retains full 7-stage structure

**Outcome:** Full scaffold created. Azure Key Vault secret stored. First commit pushed with template structure.

---

## Template for future entries

```
## YYYY-MM-DD — Feature Name

**Intent:** What are we building and why?

**Approach:**
1. Step one
2. Step two

**Design Decisions:**
- Decision A: why this over that

**Outcome:** What actually happened. Any surprises?
```
