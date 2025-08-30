# DefectDojo Integration Guide

This folder contains GitLab CI templates and guidance for importing scan results into **DefectDojo**.  
It provides both **native integrations** for supported tools and instructions for **generic imports** from unsupported tools.

---

## Supported Tools (Native Integration)

These tools are natively recognized by DefectDojo and can be imported directly using the provided CI templates.

| Tool | Purpose | CI Template | DefectDojo Docs |
|------|---------|------------|----------------|
| **Trivy** | Container image, filesystem, and config scanning for vulnerabilities | `trivy/trivy-image-scan.yml`, `trivy/trivy-fs-scan.yml`, `trivy/trivy-config-scan.yml` | [Trivy Docs](https://www.aquasec.com/products/trivy/) |
| **Semgrep** | Static Application Security Testing (SAST) with customizable rules | `semgrep/semgrep-scan.yml` | [Semgrep Docs](https://semgrep.dev/docs/) |
| **TruffleHog** | Secret scanning in Git repositories | `trufflehog/trufflehog-scan.yml` | [TruffleHog Docs](https://github.com/trufflesecurity/trufflehog) |

### Notes for Native Integration
- Use `skip_duplicates=true` in the API import call to avoid duplicate findings.
- Always provide a clear `scan_type` and `engagement` name.
- Artifacts should be generated in **JSON format** compatible with DefectDojo.
- Keep scan reports under version control to maintain traceability and reproducibility.

---

## Unsupported Tools (Generic Import)

Some tools do not have native DefectDojo support. Examples include Checkov, custom linters, or other security scanners.  

### How to Import Results
1. Generate a **JSON or CSV report** from the tool.
2. Use the DefectDojo **API `import-scan` endpoint**:
   ```bash
   curl -X POST -H "Authorization: Token $DEFECTDOJO_API_KEY" \
        -F "product=$PRODUCT_ID" \
        -F "engagement=$ENGAGEMENT_ID" \
        -F "file=@scan-report.json" \
        -F "skip_duplicates=true" \
        -F "scan_type='Custom Scan'" \
        "$DEFECTDOJO_URL/api/v2/import-scan/"
