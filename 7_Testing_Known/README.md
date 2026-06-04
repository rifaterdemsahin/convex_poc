# 7️⃣ Testing Known — Validation & Proof

> **Stage 7 of 7:** Close the loop — validate every hypothesis from Stage 1.

## Files

| File | Description |
|------|-------------|
| [`validation_report.md`](validation_report.md) | Maps each Stage 1 hypothesis to evidence |

## Master Testing Checklist

### GitHub Pages & Deployment
- [ ] GitHub Pages enabled and live at `https://rifaterdemsahin.github.io/convex_poc/`
- [ ] `index.html` loads correctly

### Navigation & UI
- [ ] Project Menu shows: Home, Queries, Mutations, Architecture
- [ ] Debug button visible at bottom-right
- [ ] Debug Menu shows all 7 stages
- [ ] Search autocomplete works in Debug Menu
- [ ] Debug mode persists via cookie

### Content & Convex Pages
- [ ] Queries page renders with syntax highlighting
- [ ] Mutations page renders with syntax highlighting
- [ ] Architecture page renders Mermaid diagram
- [ ] All 7 stage READMEs accessible via debug menu

### Secrets & Security
- [ ] `CONVEX-DEPLOY-KEY` stored in Azure Key Vault `dp-kv-deliverypilot`
- [ ] No secrets in any committed file
- [ ] `.env` listed in `.gitignore`
