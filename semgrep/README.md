# 🧾 Semgrep – Static Application Security Testing (SAST)

[Semgrep GitHub](https://github.com/returntocorp/semgrep)

## 📌 What It Does
- Pattern-based static analysis for source code
- Finds bugs, anti-patterns, and security vulnerabilities

## 🚀 When to Use
- On every Merge Request (MR) / Pull Request (PR)
- To enforce security guidelines (e.g., prevent unsafe functions)

## ✅ Best Practices
- Use rule sets:
  - `p/default` → General coding issues
  - `p/security-audit` → Security vulnerabilities
- Add **custom org-specific rules**
- Use `--baseline-ref=main` to scan only new code
- Export JSON for DefectDojo integration

## ⚠️ Pitfalls
- Overly generic rules = false positives
- Requires developer buy-in for fixing issues

---
### 🔧 Example Pipelines
- [`semgrep-scan.yml`](./semgrep-scan.yml)
