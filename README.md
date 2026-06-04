# convex_poc

Proof of concept implementations for [Convex.dev](https://www.convex.dev/) — a real-time backend platform with reactive queries, type-safe mutations, and serverless functions.

## Live Site

**GitHub Pages:** https://rifaterdemsahin.github.io/convex_poc/

## What This PoC Demonstrates

| Feature | Status |
|---------|--------|
| Real-time reactive queries | Documented in `5_Symbols/convex_queries.md` |
| Type-safe mutations | Documented in `5_Symbols/convex_mutations.md` |
| TypeScript schema with indexes | Documented in `5_Symbols/convex_schema.md` |
| Azure Key Vault secrets management | Configured — `dp-kv-deliverypilot` |
| 7-stage delivery framework | Full structure in place |

## Project Structure

This project follows the [delivery-pilot-template](https://github.com/rifaterdemsahin/delivery-pilot-template) 7-stage framework:

```
1_Real_Unknown/   # Why Convex? OKRs, questions, hypotheses
2_Environment/    # Setup guides, architecture diagrams
3_Simulation/     # UI mockups and user journey
4_Formula/        # Planning, decisions, LLM thinking log
5_Symbols/        # Convex schema, queries, mutations
6_Semblance/      # Errors, workarounds, lessons learned
7_Testing_Known/  # Validation and proof
```

## Quick Start

```bash
# Clone
git clone https://github.com/rifaterdemsahin/convex_poc.git

# Install Convex CLI
npm install -g convex

# Retrieve deploy key from Azure Key Vault
az keyvault secret show \
  --vault-name dp-kv-deliverypilot \
  --name CONVEX-DEPLOY-KEY \
  --query value -o tsv

# Start Convex dev server
CONVEX_DEPLOY_KEY=<key> npx convex dev
```

## Links

- **GitHub:** [rifaterdemsahin/convex_poc](https://github.com/rifaterdemsahin/convex_poc)
- **Convex.dev:** [convex.dev](https://www.convex.dev/)
- **LinkedIn:** [rifaterdemsahin](https://www.linkedin.com/in/rifaterdemsahin/)
- **YouTube:** [@RifatErdemSahin](https://www.youtube.com/@RifatErdemSahin)
