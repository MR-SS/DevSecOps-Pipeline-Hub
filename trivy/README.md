# 🔐 Trivy – Container & Filesystem Scanning

[Trivy GitHub](https://github.com/aquasecurity/trivy)

## 📌 What It Does
- Container Image vulnerability scanning
- Filesystem and source-code dependency scanning
- Infrastructure-as-Code (IaC) misconfiguration detection

## 🚀 When to Use
- In CI/CD pipelines before pushing an image to registry
- For IaC scanning in Terraform, Kubernetes, Helm, Dockerfiles
- For dependency scanning in local source code

## ✅ Best Practices
- Use `--ignore-unfixed` to reduce noise
- Update DB cache (`trivy --download-db`) regularly
- Run both `trivy image` **and** `trivy fs` in pipelines
- Store results as JSON for later ingestion (DefectDojo or dashboards)

## ⚠️ Pitfalls
- Old DB = missed vulnerabilities
- Large images can take longer to scan
- Be careful with CI/CD timeouts

---
### 🔧 Example Pipelines
- [`trivy-image-scan.yml`](./trivy-image-scan.yml) → Scan a container image
- [`trivy-fs-scan.yml`](./trivy-fs-scan.yml) → Scan filesystem (source code)
