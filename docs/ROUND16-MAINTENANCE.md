# Round 16 scaffold maintenance and audit — 2026-11-20

This repository contains README, LICENSE and AGENTS plus this dated documentation.
There are no important executable functions, package manifests, installer,
runtime matrix, plugin code or deployed website to document or test. No setup
command is invented. Start with [README](../README.md), and confirm the target
Janeway release/extension points in discovery issue #1 before implementation.

Manual review covered every source file, the prospective architecture, revision
and approval semantics and the MPL/historical/Janeway license boundary. Gitleaks
8.30.1 default tree and all-ref history scans (fully redacted output) report zero
matches. Dependency audit, language SAST and workflow audit are **not applicable**:
there is no executable dependency graph or workflow. This is not a tested plugin
or a claim about upstream Janeway's security. Future implementation needs bounded
parsing/decompression/jobs, safe XML with no external-entity/network resolution,
confidential-file permissions and revision-bound validation/approval evidence.

The Project 13 feature backlog remains prospective. FHT/native FHGM contract
publication does not produce a Janeway integration. DOI deposits, staging,
release publication and production deployment need their own human decisions.
No historical branches are deleted, source metadata changed or new product
feature implemented. Every PR receives independent review from another actual
model (another family preferred), and a human alone merges; agents never merge,
auto-merge, queue or bypass a PR with a default-branch push. The policy branch
is reviewable backwork, not completion of implementation issues #1–#5.

Reproducible scan shapes (run from the declared repository/source scope):
`bandit -r SOURCE -f json`, `zizmor --format json .github/workflows`,
`gitleaks dir SCOPE --redact=100 --report-format json` and
`gitleaks git . --log-opts=--all --redact=100 --report-format json`.
Bioconda history additionally restricts log paths to owned FAIR docs/scripts and
recipes; scaffold-inapplicable tools are not claimed as passes.
[Redacted source/finding inventory](audit-2026-11-20.json) records actual coverage
and locations. No raw credential values are committed.
