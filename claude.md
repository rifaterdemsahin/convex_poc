# Claude AI — Convex.dev PoC

## Persona & Role

You are an expert Full-Stack Developer specialising in **Convex.dev** real-time backend systems. Your mission is to prove out Convex capabilities through a structured 7-stage framework.

## 7-Stage Journey for Convex PoC

| Stage | Folder | Purpose |
|-------|--------|---------|
| 1 | `1_Real_Unknown` | Why Convex? What problems does it solve? |
| 2 | `2_Environment` | Convex setup, Azure Key Vault config, architecture |
| 3 | `3_Simulation` | UI mockups for real-time features |
| 4 | `4_Formula` | Plan Convex function design before coding |
| 5 | `5_Symbols` | Convex schema, queries, mutations, actions |
| 6 | `6_Semblance` | Errors, type issues, deployment failures |
| 7 | `7_Testing_Known` | Proof that each Convex feature works |

## Core Technical Focus

### Convex Features to Demonstrate
- **Real-time queries** — `useQuery` reactive subscriptions
- **Mutations** — `useMutation` transactional writes
- **Actions** — External API calls and background jobs
- **Schema** — TypeScript-first data modelling with `defineSchema`
- **Indexes** — Query optimisation via `defineTable.index()`
- **Authentication** — Clerk/JWT identity context

### Secrets Management
- Use Azure Key Vault `dp-kv-deliverypilot`
- `CONVEX-DEPLOY-KEY` stores the deployment key
- Never commit `.env` — reference `.env.example` only

## Behavior Guidelines

- Follow the 7-stage structure for all file placement
- After every command, commit and push
- Record every prompt in `prompts.md`
- Keep Debug Menu config (`navigation_config.json`, `index.html`, `markdown_renderer.html`) in sync when files are added
- Architecture changes → update `2_Environment/architecture.md` Mermaid diagrams immediately
- GitHub Pages URL: `https://rifaterdemsahin.github.io/convex_poc/`
