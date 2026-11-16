# FAIR-bioHeader-Tools-Janeway-Plugin

Janeway integration for verified FAIR-bioHeaders (FH*) metadata tables in genomic data-note papers.

**Status: planning scaffold.** This repository currently contains documentation and a work backlog, not an installable plugin. The New Prairie Press journal and deployment are prospective; publisher requirements and agreement remain to be confirmed.

## Intended workflow

An author submits a manuscript with an FH* data file. The plugin preserves the original revision, calls the family toolkit to validate metadata and verify file integrity, and presents a generated table and report for author/editor review. Approved outputs feed JATS XML tables, the tested HTML/microdata rendering and compatible DOI registration metadata.

Replacing a source file or editing publication context invalidates its earlier verification/table approval. Corrections create new revisions; the plugin must not silently edit submitted headers or checksums.

“Verified” reports individual checks actually run: schema validity, exact-file checksum, available parent-file checks and separately executed biological checks. JATS validity and DOI deposit readiness are separate results. A checksum match is not scientific certification. Remote references or header-only records cannot establish file integrity without the identified bytes.

## Architecture

- **This repository:** Janeway registration/settings, upload/revision handling, jobs, permissions, editorial approval, production integration and operations guidance.
- [FAIR-bioHeaders-Tools](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Tools): reusable parsing, schema selection, checksum verification and deterministic JATS/DOI exporters.
- [FAIR-bioHeaders-Specification](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Specification): published contracts, reviewed mapping semantics and normative fixtures.
- [Family website](https://github.com/FAIR-bioHeaders/fair-bioheaders.github.io): public documentation and worked examples.

Use [mapping issue #56](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Specification/issues/56) as the semantic foundation. JATS, HTML and DOI outputs should reuse reviewed source/context values while reporting target-specific omissions and conflicts. Keep the paper, dataset and metadata record distinct, including their creators, identifiers, dates and versions. DOI registration metadata is agency-specific; preparing an export does not register a DOI or authorize publication.

Begin with FHR. Other types require demonstrated contract, toolkit and binding support. FHT/FHGM retain their own release/adoption gates.

## Work plan

Coordination: [Project 13](https://github.com/orgs/FAIR-bioHeaders/projects/13). Parent tracker: [specification #248](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Specification/issues/248).

| Step | Deliverable | Issue |
| --- | --- | --- |
| 1 | Confirm NPP editorial workflow, Janeway extension points and deployment targets | [FAIR-bioHeader-Tools-Janeway-Plugin#1](https://github.com/FAIR-bioHeaders/FAIR-bioHeader-Tools-Janeway-Plugin/issues/1) |
| 2 | Define the NPP/Janeway JATS, HTML and DOI metadata mapping slice | [FAIR-bioHeaders-Specification#249](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Specification/issues/249) |
| 3 | Build a standalone FHR verification and JATS table export prototype for Janeway | [FAIR-bioHeaders-Tools#169](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Tools/issues/169) |
| 4 | Prepare DOI metadata from the reviewed genomic data-note source and context | [FAIR-bioHeaders-Tools#170](https://github.com/FAIR-bioHeaders/FAIR-bioHeaders-Tools/issues/170) |
| 5 | Implement revision-aware FH* submission verification and editorial approval | [FAIR-bioHeader-Tools-Janeway-Plugin#2](https://github.com/FAIR-bioHeaders/FAIR-bioHeader-Tools-Janeway-Plugin/issues/2) |
| 6 | Integrate approved JATS tables, HTML microdata and DOI metadata in production | [FAIR-bioHeader-Tools-Janeway-Plugin#3](https://github.com/FAIR-bioHeaders/FAIR-bioHeader-Tools-Janeway-Plugin/issues/3) |
| 7 | Run an agreed NPP staging genomic data-note pilot | [FAIR-bioHeader-Tools-Janeway-Plugin#4](https://github.com/FAIR-bioHeaders/FAIR-bioHeader-Tools-Janeway-Plugin/issues/4) |
| 8 | Document and prepare the supported Janeway plugin release | [FAIR-bioHeader-Tools-Janeway-Plugin#5](https://github.com/FAIR-bioHeaders/FAIR-bioHeader-Tools-Janeway-Plugin/issues/5) |

Each issue records prerequisites and acceptance evidence. First confirm the target Janeway release, extension points, JATS flavor/version, NPP editorial/file-hosting requirements and DOI deposit route. Then demonstrate one complete standalone FHR fixture before production integration. Staging acceptance, release publication, DOI deposit and production deployment have their own explicit decisions.

## Development

No installation command or supported runtime matrix exists yet. See [discovery issue #1](https://github.com/FAIR-bioHeaders/FAIR-bioHeader-Tools-Janeway-Plugin/issues/1) for the local spike and dependency/version decisions.

Implementation should reuse pinned toolkit capabilities; preserve source bytes and source/context provenance; bound jobs, decompression and parsing; keep confidential review files permission-controlled; disable XML external-entity/network resolution; and test the actual JATS-to-HTML rendering path. Every generated table/report must identify the approved input revision and relevant tool/schema/profile versions.

Contribute through linked, reviewable PRs with validation evidence. Do not introduce FH* core fields or claim draft mappings are released as incidental plugin work.

## License and provenance

New project contributions from March 2025 onward use **MPL-2.0**, subject to the historical and third-party exceptions in [LICENSE](LICENSE). Historical USDA-ARS public-domain portions, where present or later imported, retain their existing status within the United States. This does not classify current contributors or this newly authored scaffold as government work.

The license notice and unmodified MPL text are adapted from FAIR-bioHeaders-Tools LICENSE at blob `2e942bbd11cf4b4dfffc28ac1be15945fa6722bf`, retaining the historical USDA notice verbatim. Previously distributed versions retain their existing permissions.

[Janeway](https://github.com/openlibhums/janeway) is licensed under [AGPL-3.0](https://github.com/openlibhums/janeway/blob/master/LICENSE). No Janeway source is bundled in this scaffold, and this repository's license does not relicense Janeway. Future copied/modified upstream files retain their own notices. Distribution or hosting of a combined work must comply with the applicable licenses; record the integration/dependency boundary in issue #1 before adding implementation.

## References

- [New Prairie Press](https://journals.newprairiepress.org/)
- [Janeway plugin/events/hooks documentation](https://janeway.readthedocs.io/en/v1.7.2/dev/plugins.html)
- [Janeway JATS import documentation](https://janeway.systems/pages/support/plugins/imports-jats)

