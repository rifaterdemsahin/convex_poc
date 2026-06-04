# Agents — Convex.dev PoC

This file defines how AI agents interact with the **Convex.dev PoC** project.

## Supported Agents

| Agent | File | Purpose |
|-------|------|---------|
| Claude | `claude.md` | Full-stack dev, Convex functions, 7-stage framework |

## Agent Rules

- Always follow the 7-stage folder structure (`1_Real_Unknown` through `7_Testing_Known`)
- Never commit secrets — use Azure Key Vault for all sensitive values (CONVEX_DEPLOY_KEY, etc.)
- **After every command, commit and push** — do not batch changes; each step gets its own commit.
- Place files in the correct numbered folder:
  - **1_Real_Unknown**: Convex PoC objectives and open questions
  - **2_Environment**: Setup guides, Convex environment config, architecture diagrams
  - **3_Simulation**: UI mockups for real-time demo pages
  - **4_Formula**: Plan Convex function design before writing code; log LLM reasoning in `llm_thinking_log.md`
  - **5_Symbols**: All Convex source files — schema, queries, mutations, actions
  - **6_Semblance**: Document Convex-specific errors, TypeScript type issues, deployment failures
  - **7_Testing_Known**: Validation that each Convex feature works end-to-end
- **Thinking & Planning Gate** — Before writing any Convex functions, document the approach in `4_Formula/llm_thinking_log.md`
- **Error & Fix Logging** — Append to `6_Semblance/error.log` and `6_Semblance/fix.log`
- **Record every prompt** in `prompts.md`
- **README.md must include the public GitHub Pages URL**: `https://rifaterdemsahin.github.io/convex_poc/`
- **Two menus required** — Project Menu (Home, Queries, Mutations, Architecture) + Debug Menu (7 stages)

## Secrets Management

All agents use **Azure Key Vault** (`dp-kv-deliverypilot`) for secrets:

- `CONVEX-DEPLOY-KEY` — Convex deployment key JSON
- `CONVEX-URL` — Deployment endpoint URL

Never store these in code, config files, or git history.
