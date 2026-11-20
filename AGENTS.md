# Agent instructions

## Independent review and human-only merges (maintainer direction, 2026-11-20)

The [Round 16 policy](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Specification/issues/211#issuecomment-7042896529)
supersedes the former conditional agent-merge authorization of 2026-11-16/18.
**Agents must never merge pull requests in this repository; a human performs
every merge.** Do not enable auto-merge, enter a merge queue, use another agent
or service as a merge proxy, or push directly to the default branch as a
substitute for merging a PR. Model review never grants an agent merge authority;
preserve platform protections and do not forge approval.

Every PR receives independent review from another actual model. A different
model family is preferred (for example Codex or Gemini reviewing Qwen work),
but family diversity is a preference, not a hard requirement; a second session
of the same model is not another model. Record actual author/reviewer model
identities and never invent review provenance.

Agents keep monitoring CI and fixing failures and actionable review findings:
read the overall review and every inline finding, fix in new commits, reply with
disposition and evidence, resolve handled threads and acknowledge clean reviews.
Validate the current head after changes and hand the human exact head/base,
review, CI, dependency and remaining-risk information. Missing, failed and
NOT_RUN checks are not passes. Earlier rounds' authorized merges and dated
receipts remain accurate history, not future permission.

## What this repository is (and is not)

A **planning scaffold**: README.md, LICENSE and this file. There is no plugin
code, no installable package, no supported runtime matrix and no deployment.
Do not present any part of it as shipped functionality, and do not invent an
installer, version or compatibility claim. The New Prairie Press journal, its
deployment and its editorial requirements are **prospective**, not confirmed.

## Scope discipline

- Feature work belongs to Project 13 and its tracked issues
  (Janeway-Plugin #1–#5, specification #248/#249, Tools #169/#170). This
  Round 16 documentation and policy lane must **not** implement them.
- Verification, table generation and JATS/HTML/DOI exporters belong to
  FAIR-bioHeaders-Tools; contracts and mappings belong to
  FAIR-bioHeaders-Specification. Keep the split shown in README.md.
- Do not add or rename FH* core fields, claim draft (FHT/FHGM) mappings are
  released, or make schema decisions from plugin work (rule V7: drafts take
  no release form).
- DOI deposit, staging acceptance, release publication and production
  deployment are separate explicit human decisions.

## Licensing

MPL-2.0 for new contributions from March 2025 onward, with the historical
USDA-ARS public-domain split recorded verbatim in LICENSE (adapted from the
toolkit LICENSE blob `2e942bbd11cf4b4dfffc28ac1be15945fa6722bf`). Do not
normalize the historical notice, relicense the scaffold, or imply that this
license covers Janeway itself (upstream Janeway is AGPL-3.0; nothing of it is
bundled here — record the integration/dependency boundary in issue #1 before
any implementation lands).

## Security posture for future work (planning only, nothing to run yet)

Any future plugin code must: preserve submitted source bytes (never silently
edit headers or checksums); bind jobs, decompression and parsing
(resource limits); disable XML external-entity resolution and network fetches
in parsers; keep confidential review files permission-controlled; and require
that every generated table/report name the exact input revision and the
tool/schema versions used. Replacements of source files or publication
context invalidate prior verifications — verification results are
revision-scoped.

## Working conventions

- Link every PR to its issue (`Closes #N` only when merge fulfills complete
  acceptance; `Refs #N` otherwise) and keep Project 9 / Project 13 cards
  truthful.
- Docs-only changes here still get another-model review; record the models.
- No force-pushes, no history rewrites, no remote branch purges.
