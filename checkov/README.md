# Checkov - Infrastructure as Code Security Scanner

**Description:**  
Checkov is an open-source static analysis tool for Infrastructure as Code (IaC). It scans Terraform, CloudFormation, Kubernetes manifests, and other IaC files for security and compliance issues.

**Best Practices:**
- Run Checkov on every merge request to catch IaC misconfigurations early.
- Use `--soft-fail` in pipelines if you want to collect issues without blocking CI.
- Use Checkov with DefectDojo to centralize and track vulnerabilities.
- For performance, scan only directories containing IaC files.

**GitLab CI Integration:**
- YAML template: `checkov/checkov-scan.yml`
- Output: JSON report stored as GitLab artifact for DefectDojo import.
- Tags: `semgrep` (or adjust according to your runner)

**Useful links:**
- [Checkov Official](https://www.checkov.io/)
- [Checkov GitHub](https://github.com/bridgecrewio/checkov)
