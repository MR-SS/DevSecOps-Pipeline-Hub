# DevSecOps-Pipeline-Hub


This repository contains ready-to-use GitLab CI templates for DevSecOps pipelines, fully integrated with **DefectDojo**.

## Tools Included
- [**Trivy**](https://www.aquasec.com/products/trivy/): Scans container images, filesystem, and configuration files for vulnerabilities.
- [**Semgrep**](https://semgrep.dev/): Performs SAST scans with customizable rules. Supports rulesets like `p/default` for general patterns and `p/security-audit` for security-specific findings.
- [**TruffleHog**](https://github.com/trufflesecurity/trufflehog): Detects secrets, API keys, and sensitive data in Git repositories.
- [**Checkov**](https://www.checkov.io/): Scans Infrastructure-as-Code files (Terraform, CloudFormation, Kubernetes manifests) for misconfigurations and compliance issues.

- [**DefectDojo**](https://docs.defectdojo.com/): Centralizes and manages all scan results, tracks vulnerabilities, and avoids duplicates.

## Usage
1. Fork or clone this repository.
2. Set environment variables for Docker registry, DefectDojo API, and package names.
3. Run the pipeline to scan the sample app.
4. Artifacts and reports are automatically imported into DefectDojo.

## Adding New Tools
- Place your new CI template in `ci-templates/`.
- Add a link to its official documentation and a short description in the README.
- Include it in `.gitlab-ci.yml` with the `include` directive.
