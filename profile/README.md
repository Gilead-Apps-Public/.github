# Gilead Sciences Public Repositories

This GitHub organization is for source code and assets that Gilead explicitly designates as public. All content here must be safe to disclose externally.

## 1. Purpose
Provide a controlled, auditable space for:
- Open source tooling we maintain.
- Reference implementations, SDK helpers, and examples.
- Community collaboration (issues, discussions, PRs) on approved projects.

## 2. Before Creating a Repository
You must:
1. Confirm the project is appropriate for public release (no internal competitive IP).
2. Complete internal Open Source Review (Engineering + Legal / Compliance).
3. Obtain a SPDX‑compatible license approval.
4. Identify at least 2 active maintainers (GitHub usernames).
5. Ensure no embedded secrets (scan locally).

Creation request should include:
- Proposed name
- Short description
- Intended license
- Primary language / stack
- Maintenance owners
- External dependency list (high level)

## 3. Repository Naming
Format: product-or-domain[-purpose]
Examples: data-pipeline-sdk, bioinformatics-tools, infra-automation-examples
Avoid: internal codes, patient references, confidential abbreviations.

## 4. Mandatory Top-Level Files
| File | Requirement |
|------|-------------|
| README.md | Project overview, quickstart, support, contribution link |
| LICENSE | Approved OSS license (MIT / Apache-2.0 / BSD-3-Clause unless otherwise approved) |
| SECURITY.md | How to report vulnerabilities (direct to security@gilead.com or defined channel) |
| CODE_OF_CONDUCT.md | Reference to Contributor Covenant v2.1 (or internally approved variant) |
| CONTRIBUTING.md | PR guidelines, DCO / sign-off rules, branching model |
| CODEOWNERS | At least two owners (teams preferred) |
| .github/ISSUE_TEMPLATE/* | (Optional) Standard issue templates |
| .github/PULL_REQUEST_TEMPLATE.md | (Recommended) PR checklist |

## 5. Content Restrictions
Do NOT include:
- Secrets: API keys, tokens, certs, passwords, private endpoints.
- Regulated / personal / patient / clinical trial data (even anonymized).
- Licensing-restricted third-party binaries.
- Internal architecture diagrams revealing privileged infrastructure.
- Proprietary algorithms not cleared for public release.
- Vendor contracts, pricing, or confidential legal text.

## 6. Security & Compliance
- Dependabot (or equivalent) must be enabled for dependency updates (PRs auto-label: security).
- GitHub Advanced Security (secret scanning, code scanning) enabled where licensed.
- Block force pushes & branch deletions on default branch.
- Require status checks + at least 1 reviewer (not the author).
- Signed commits recommended; apply organization-level enforcement when available.
- Release artifacts should be reproducible (document build steps).

## 7. Branch & Release Model
Recommended:
- main: always releasable.
- feature/*: short‑lived branches.
- release tags: vMAJOR.MINOR.PATCH (Semantic Versioning).
- Keep CHANGELOG.md (Keep a Changelog format) or GitHub Releases notes.

## 8. Contribution Workflow
1. Fork + branch.
2. Lint / test locally (provide make or script targets).
3. Pull request:
   - Linked issue (if applicable).
   - Pass CI (tests + linters + security scans).
4. Reviewer merges (no self-merge unless emergency with retro review).

## 9. Handling Vulnerabilities
- Report via SECURITY.md instructions (private channel).
- Acknowledge receipt within 2 business days.
- Triage severity; patch branch + security release tag.
- Public disclosure only after fix released.

## 10. Licenses
Preferred: Apache-2.0 (default), MIT (simple libs), BSD-3-Clause (legacy compatibility).
Attribution / notice files must remain intact.
Third-party license summaries should live in THIRD_PARTY_NOTICES.md when required.

## 11. Attribution & Trademarks
Do not use third-party logos without permission.
Include: (c) Gilead Sciences, Inc. YEAR in NOTICE or LICENSE if license format supports.

## 12. Archiving / Sunsetting
If unmaintained:
- Update README with Archived notice.
- Disable issues and PRs.
- Apply archive state in GitHub.
- Retain license and SECURITY.md for historical clarity.

## 13. Automation Checklist (Recommended)
- CI: lint, unit tests, SAST (code scanning), secret scan.
- Infrastructure as Code scanning if IaC present.
- Dependency update schedule (weekly).
- Release pipeline (tag -> build -> publish).

## 14. Maintainer Responsibilities
- Triage issues < 5 business days.
- Review PRs < 10 business days.
- Keep dependencies current (no critical CVE >30 days).
- Monitor GitHub security advisories.

## 15. Quick Maintainer Checklist
[ ] LICENSE present & approved
[ ] SECURITY.md instructs disclosure path
[ ] CODEOWNERS with two maintainers / team aliases
[ ] No secrets (scanned)
[ ] CI passing / tests documented
[ ] Dependabot enabled
[ ] Default branch protections enforced
[ ] README contains: overview, install, usage, support

## 16. Getting Help
Internal: #open-source Slack channel / OSS program contacts
External: Use repository Issues (if enabled) or SECURITY.md for vulnerabilities only.

---

By contributing you agree to the repository’s license and policies above.
