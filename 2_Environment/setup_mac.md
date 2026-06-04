# macOS Setup — Convex.dev PoC

## Prerequisites

```bash
# Node.js 18+
node --version

# npm 9+
npm --version
```

## Install Convex CLI

```bash
npm install -g convex
```

## Authenticate with Convex

```bash
npx convex login
# Opens browser for OAuth login
```

## Initialise a new Convex project

```bash
npx convex dev
# Creates convex/ folder with schema.ts and functions
```

## Load deploy key from Azure Key Vault

```bash
# Requires az CLI and login
az keyvault secret show \
  --vault-name dp-kv-deliverypilot \
  --name CONVEX-DEPLOY-KEY \
  --query value -o tsv
```

## Environment file

Create `.env` (never committed):
```bash
CONVEX_DEPLOY_KEY={"v2":"...your-key-from-vault..."}
```
