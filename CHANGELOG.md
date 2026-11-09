# Changelog

All notable changes to this specification are listed here.
The format follows [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/),
and versions follow [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.1.0] - 2026-11-08

### Added

- Secure development rules SEC-001 to SEC-006: a profile of NIST SP 800-218 SSDF 1.1, two security contacts per project, a threat model in each product repository, and an OWASP ASVS 5.0.0 level per product, Level 2 by default for public-sector products, with versioned requirement IDs.
- Review and analysis rules SEC-010 to SEC-017: a second maintainer approves each security-relevant change, code owners for those parts, static analysis, secret scanning and dependency checks as required checks, reviewed update pull requests, exceptions with an end date, and no required vendor tool or paid service.
- Secrets rules SEC-020 to SEC-024: no secret in repositories, images or logs, push-blocking scanning, revocation of a leaked secret, rotation and scoped secrets in continuous integration.
- Supply chain rules SEC-030 to SEC-037: pinned dependencies with hashes, outside actions pinned by commit hash and images by digest, a CycloneDX 1.7 SBOM per artifact with SPDX 3.0.1 as an option, SLSA v1.2 Build Level 2 provenance with Level 3 as the target, signed artifacts and reproducible builds as a recommendation.
- Reporting rules SEC-040 to SEC-048: private channels outside Working Group activity, the FPSOT security team, acknowledgment within 3 business days and assessment within 10, CVSS v4.0, a CVE per fix, OSV advisories, root-cause analysis and records.
- Disclosure rules SEC-050 to SEC-058: a free pre-notice list open to every public-sector adopter on published criteria, with a published member list; the details and the fix in each pre-notice; a head start of 7 days, from 72 hours to 14 days; a public date notice about a week ahead; public release within 90 days, or at once when exploited or leaked; and the duties of members.
- Release rules SEC-060 to SEC-065: supported versions, end-of-support notice, security patch releases, the `SECURITY.md` file of each repository, private vulnerability reporting and `security.txt`.
- Rules SEC-070 to SEC-073 on security flaws in specifications: private reports, a fix prepared outside the Working Group and a patch release.
- Security test rules SEC-080 to SEC-084, tied to the testing specification: required checks, a dynamic scan of each API, tests of the API security rules, no public test before the fix and synthetic credentials.
- An informative page on laws and the deadlines of recipients, with the likely steward role of FPSOT under the Cyber Resilience Act. It is not legal advice.
- The bilingual template `examples/SECURITY.md`.
- Comparison data with Canada and Québec rows.
- How-to guide that handles one report from receipt to public release.

[Unreleased]: https://github.com/fpsot-org/fpsot-spec-security/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/fpsot-org/fpsot-spec-security/releases/tag/v0.1.0
