# 2️⃣ Environment — Convex Setup & Context

> **Stage 2 of 7:** Establish the context before writing a single line of code.

## Files

| File | Description |
|------|-------------|
| [`architecture.md`](architecture.md) | System architecture with Mermaid diagrams |
| [`setup_mac.md`](setup_mac.md) | macOS environment setup for Convex development |
| [`setup_azure.md`](setup_azure.md) | Azure Key Vault configuration for Convex secrets |

## Quick Start (macOS)

```bash
# Install Convex CLI
npm install -g convex

# Authenticate
npx convex login

# Initialise project
npx convex dev
```

## Secrets

The Convex deploy key is stored in Azure Key Vault (`dp-kv-deliverypilot`) as secret `CONVEX-DEPLOY-KEY`. See [`setup_azure.md`](setup_azure.md) for retrieval instructions.

## Testing Checklist

- [ ] Convex CLI installed and authenticated
- [ ] Azure Key Vault created with deploy key stored
- [ ] Architecture diagram renders via Mermaid
- [ ] Local `npx convex dev` starts without errors
