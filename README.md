# DevSecOps Pipeline Hub

**GitLab CI security template collection** for integrating application and infrastructure security checks into development workflows.

This repository documents reusable pipeline patterns involving Semgrep (SAST), Trivy (dependency/container scanning), TruffleHog (secret detection), Checkov (IaC), and DefectDojo (finding intake).

> **Validation scope:** This README describes the intended integrations and examples. It is not evidence that every template has passed a production deployment, that scanners prevent every vulnerability, or that DefectDojo imports have been verified end-to-end on a clean installation. Review the actual CI configuration and test results before adopting these templates.

## Security engineering objectives

- Introduce repeatable security checks into GitLab-based software delivery.
- Produce scanner output that teams can inspect and triage.
- Consolidate findings for follow-up and remediation workflows.
- Provide building blocks that teams can adapt to their own release processes.

## Components

| Component | Purpose |
| --- | --- |
| Semgrep | Static analysis, with rules selected per language and risk |
| Trivy | Container, filesystem, configuration and dependency checks as configured |
| TruffleHog | Candidate secret detection |
| Checkov | Infrastructure-as-Code policy checks |
| DefectDojo | Intake and management of findings where integration is configured |

## Getting started

1. Review the `ci-templates/` directory and the root GitLab CI configuration to identify the templates actually present.
2. Pin scanner versions and review each tool's output and failure policy before deployment.
3. Configure required credentials in protected CI variables or an approved secrets manager; never commit them.
4. Start with report-only operation and test the pipeline on a controlled project.
5. Verify import semantics and deduplication before enabling automatic DefectDojo synchronization or release blocking.

## Adoption limitations

The templates are examples rather than a drop-in compliance or production security guarantee. Missing scan coverage, timeouts, artifact integrity and false-clean results need explicit handling. Review privileged runners, network access and external integrations in your environment.

## Related public work

- [DefectDojo Security Research Lab](https://github.com/MR-SS/defectdojo-security-lab)
- [DefectDojo Helm SMTP Lab](https://github.com/MR-SS/defectdojo-helm-smtp-lab)

Maintained by [Sajjad Rahim Nouri](https://github.com/MR-SS).
