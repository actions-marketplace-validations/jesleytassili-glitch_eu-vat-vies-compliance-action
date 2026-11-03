# 🛡️ EU VIES VAT, Brazil Tax NCM & Global Invoice Tax ID Gate

[![Marketplace Release](https://img.shields.io/github/v/release/jesleytassili-glitch/eu-vat-vies-compliance-action?color=brightgreen&label=Marketplace%20Release)](https://github.com/jesleytassili-glitch/eu-vat-vies-compliance-action/releases/tag/v1.0.1)
[![Official MCP Registry](https://img.shields.io/badge/Official_MCP_Registry-io.github.jesleytassili--glitch-6366F1)](https://registry.modelcontextprotocol.io/v0/servers?search=io.github.jesleytassili-glitch)
[![RapidAPI Hub](https://img.shields.io/badge/RapidAPI-@b2bquantapis-0055FF)](https://rapidapi.com/b2bquantapis/api/eu-vies-vat-tax-compliance-auditor)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)

Automated B2B ERP & billing pipeline gate for European VIES VAT IDs, Brazil LC 214 IBS/CBS NCM & CNPJ QSA tax audits.

## 🚀 Quick Start (`.github/workflows/compliance.yml`)

```yaml
name: Automated Compliance Audit
on:
  pull_request:
  schedule:
    - cron: '0 7 * * 1'

jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run EU VIES VAT, Brazil Tax NCM & Global Invoice Tax ID Gate
        uses: jesleytassili-glitch/eu-vat-vies-compliance-action@v1
        with:
          mode: 'eu-vies-vat'
          targets: 'IE6388047V,DE811128135'
          rapidapi_key: ${{ secrets.RAPIDAPI_KEY }}
```

## 📊 Available Audit Modes

- `eu-vies-vat` — EU VIES Cross-Border VAT Number & Reverse-Charge Audit ([RapidAPI](https://rapidapi.com/b2bquantapis/api/eu-vies-vat-tax-compliance-auditor) | [Apify](https://apify.com/b2b-quant-apis/eu-vies-vat-tax-compliance-auditor))
- `brazil-ncm-ibscbs` — Brazil Tax Reform LC 214 IBS/CBS NCM & cClassTrib Audit ([RapidAPI](https://rapidapi.com/b2bquantapis/api/brazil-tax-reform-ncm-classtrib-auditor) | [Apify](https://apify.com/b2b-quant-apis/brazil-tax-reform-ncm-classtrib-auditor))
- `brazil-cnpj-qsa` — Brazil Receita Federal CNPJ & Corporate Partners (QSA) Audit ([RapidAPI](https://rapidapi.com/b2bquantapis/api/brazil-b2b-cnpj-qsa-lead-enricher) | [Apify](https://apify.com/b2b-quant-apis/brazil-b2b-cnpj-qsa-lead-enricher))

## 📦 Programmatic SDKs & Local MCP Server

- **Python SDK (PyPI):** `pip install b2b-compliance-sdk`
- **Node.js / Claude / Cursor MCP (`stdio`):** `npx -y b2b-compliance-mcp-cli`
