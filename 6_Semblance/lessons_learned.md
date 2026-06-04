# Lessons Learned — Convex.dev PoC

## 2026-06-04 — Initial Scaffold

**What went well:**
- Using `delivery-pilot-template` as a base gave immediate structure
- The 7-stage framework maps cleanly onto a PoC evaluation workflow
- GitHub CLI (`gh api`) is efficient for fetching template files without cloning

**What to improve:**
- Future scaffolds should start with Convex CLI init first, then overlay the 7-stage docs structure
- The Azure Key Vault creation requires an active `az login` session — document this dependency upfront

**Apply next time:**
1. Run `az login` before any Key Vault operations
2. Run `npx convex dev` to initialise the `convex/` folder structure before adding custom functions
