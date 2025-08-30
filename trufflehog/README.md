# 🔍 TruffleHog – Secret Scanning

[TruffleHog GitHub](https://github.com/trufflesecurity/trufflehog)

## 📌 What It Does
- Detects hardcoded secrets, API keys, and tokens
- Can scan filesystem and git history

## 🚀 When to Use
- On every commit/merge before pushing code
- During historical repo audits for leaked credentials

## ✅ Best Practices
- Enable entropy detection (`--entropy=True`)
- Maintain allowlist for known test/fake secrets
- Scan both repo **and** git history for coverage

## ⚠️ Pitfalls
- Many false positives without allowlist
- Large repo histories = slow scans

---
### 🔧 Example Pipelines
- [`trufflehog-scan.yml`](./trufflehog-scan.yml)
