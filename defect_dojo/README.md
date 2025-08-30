# 📊 DefectDojo – Vulnerability Management

[DefectDojo GitHub](https://github.com/DefectDojo/django-DefectDojo)

## 📌 What It Does
- Central hub for vulnerability results
- Deduplicates, tracks, and manages security findings
- Supports **native integrations** and **generic JSON imports**

## 🚀 When to Use
- When multiple scanners are used in your CI/CD
- To track vulnerabilities across projects/teams

## ✅ Best Practices
- Always export scanner reports in JSON format
- Use native parsers for Trivy, Semgrep, TruffleHog
- Use **Generic JSON Importer** for unsupported tools
- Deduplicate findings to avoid alert fatigue
- Connect with GitLab/Jira for ticketing workflows

## ⚠️ Pitfalls
- Needs regular triage, otherwise findings backlog grows
- Requires dedicated setup and database management

---
### 🔧 Example Pipelines
- [`defectdojo-import.yml`](./defectdojo-import.yml)
