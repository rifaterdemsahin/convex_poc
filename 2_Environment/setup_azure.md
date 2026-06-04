# Azure Key Vault Setup — Convex PoC

## Key Vault: `dp-kv-deliverypilot`

The Convex deploy key is stored here to avoid committing secrets to git.

## Existing Key Vault

Uses the shared delivery pilot vault in `deliverypilot-rg` (already provisioned — no creation needed).

```
Subscription: b85b029d-9f7c-4c5a-8939-819480780c5d
Resource Group: deliverypilot-rg
Vault: dp-kv-deliverypilot
```

## Store the Convex deploy key

```bash
az keyvault secret set \
  --vault-name dp-kv-deliverypilot \
  --name CONVEX-DEPLOY-KEY \
  --value '{"v2":"3ef9720ff1c741e69502e8a261d2bfe4"}'
```

## Retrieve at runtime

```bash
az keyvault secret show \
  --vault-name dp-kv-deliverypilot \
  --name CONVEX-DEPLOY-KEY \
  --query value -o tsv
```

## GitHub Actions integration

```yaml
- uses: Azure/get-keyvault-secrets@v1
  with:
    keyvault: dp-kv-deliverypilot
    secrets: 'CONVEX-DEPLOY-KEY'
  id: kvSecrets

- name: Deploy to Convex
  env:
    CONVEX_DEPLOY_KEY: ${{ steps.kvSecrets.outputs.CONVEX-DEPLOY-KEY }}
  run: npx convex deploy
```

## Access Policy

Grant only the GitHub Actions service principal `get` permission on secrets. No `list` or `set` in CI.
