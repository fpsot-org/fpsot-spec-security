---
name: fpsot-security
description: Security rules for FPSOT projects. Use when writing or reviewing threat models, security requirements, security-relevant pull requests, CI security checks, secrets handling, dependency pinning, SBOMs, provenance, release signing, SECURITY.md files, vulnerability reports and advisories, or the pre-notice and disclosure of a fix.
---

# FPSOT security

Summary of the FPSOT security specification. It adds no rules of its own.
The spec text in `spec/` wins on any difference. Each line cites its requirement ID.
The `SECURITY.md` template is in `examples/SECURITY.md`.

Each line keeps the strength of its rule: "must" and "must not" are MUST and MUST NOT, "should" and "should not" are SHOULD and SHOULD NOT, "may" is MAY.

Never send a vulnerability to a Working Group, a public issue, a public discussion or a meeting: information shared in Working Group activity is not confidential under CS 1.0 GOVERNANCE.md §5 (SEC-040, SEC-070).
See the applicability table in `spec/en/index.adoc`: SEC-033 and SEC-034 apply to software components only, and SEC-035 and SEC-036 are SHOULD for specification books.

## Secure development

- Each project must meet the SSDF 1.1 practices as the spec profiles them; it may go further; it must not claim SSDF conformance on this spec alone (SEC-001).
- Each project must name at least two maintainers as security contacts, who can reach the FPSOT security team in private and take part in each report on their project (SEC-002).
- Each product must keep a text threat model in its repository, written before the first release, updated when a trust boundary changes, reviewed at least yearly with the date recorded (SEC-003).
- A threat model must name assets, actors, trust boundaries, threats and the response to each: a product control, an operator control, or an accepted risk with its reason; any method may be used; diagrams as code under DOC-030 (SEC-004).
- Each product must choose and record an ASVS 5.0.0 level with its reason; a product that serves the public or handles personal information for a public body must choose Level 2 or 3, Level 2 being the default; a library or tool with no UI and no stored data may choose Level 1 (SEC-005).
- Requirements must be cited by versioned ASVS ID, such as `v5.0.0-1.2.5`; each unmet requirement of the level must be recorded with reason and compensating control; ASVS text must not be copied (SEC-006).

## Code, review and analysis

- A security-relevant change (identity, access, input, crypto, secrets, personal information, dependency manifests, build and CI files, SECURITY.md, threat model, code owners) must have the approval of a maintainer other than the author; other changes should too; nobody may approve their own change (SEC-010).
- The code owners file must cover each security-relevant part, and protected branches must require code-owner review there (SEC-011).
- CI must run static analysis on every pull request as a required check; high or critical findings must block the merge; a finding must not be turned off without a record under SEC-016 (SEC-012).
- CI must scan each pull request for secrets as a required check, and the whole history at least weekly (SEC-013).
- CI must check dependencies against a public vulnerability database on each pull request and daily on `main`; a high or critical known vulnerability must block the merge unless SEC-016 records an exception (SEC-014).
- A project must use a tool that opens update pull requests for dependencies and CI actions; each must pass the required checks and get a maintainer's approval; updates must not merge without review (SEC-015).
- Each exception must record reason, owner and an end date at most 90 days out, approved by another maintainer; it may be renewed once after a new review and approval (SEC-016).
- Any tool, free or paid, may meet these rules; contributors must not have to buy a tool or service; the tools should be named in the repository (SEC-017).

## Secrets

- No secret in a repository, its history, an image, a release artifact, a log, a test report or an error message; read secrets at run time; no default password or key; test fixtures hold no real credential (SEC-020, SEC-084).
- Each repository must turn on push-blocking secret scanning; a bypass may happen only for a non-secret value, with a reason recorded (SEC-021).
- A leaked secret must be revoked at once, replaced, and its use checked in the logs; a history rewrite must not count as a fix; report the leak under SEC-040 when the secret protects a shared system (SEC-022).
- Each secret must have an owner and a rotation period, rotated at least yearly and when a person with access leaves; short-lived credentials should be preferred (SEC-023).
- CI secrets must sit in the CI secret store, scoped to the jobs that need them; jobs must get least privilege, with read-only default workflow permissions; secrets must not reach jobs that run code from outside forks; release secrets should sit in a protected environment (SEC-024).

## Supply chain

- Every direct and transitive release dependency must be pinned to an exact version, in a lock file or an equivalent that fixes every version, such as a managed version list; the build must verify package checksums where its tool supports it; a release must not depend on a version range (SEC-030).
- Each outside CI action must be pinned by full commit hash with its version in a comment; FPSOT reusable workflows may use their major tag; container images must be pinned by digest (SEC-031).
- Dependencies must come only from declared registries; no unpinned, unchecked network scripts; other downloaded inputs must be checked against the publisher's signature or hash; supported components without high or critical vulnerabilities should be preferred; an unsupported component must be replaced or recorded under SEC-016 (SEC-032).
- Each release of a software component must include a JSON SBOM per artifact in CycloneDX 1.7 or a later ECMA-424 version, listing every component with version and package URL; CycloneDX 1.6 may be used until 2027-06-30; SPDX 3.0.1 may also be published (SEC-033).
- The SBOM must come from the build's resolved dependencies, not only from a scan of the artifact (SEC-034).
- Each software artifact must have SLSA v1.2 Build Level 2 provenance, published with the release; Level 3 should be reached; builds must run on a hosted service from a signed tag (VCS-106), never on a personal computer; a specification release should publish provenance for its books (SEC-035).
- Each software artifact must be signed or listed with its hash in a signed manifest; the project must publish how to verify signature and signer; a specification release should also sign its books (SEC-036).
- Builds should be reproducible, the build environment should be recorded and known differences stated (SEC-037).

## Reporting and handling

- Each repository must offer a private reporting channel, delivered only to the security contacts and the FPSOT security team; FPSOT must offer a second private channel for people without a forge account; reports must not go through a Working Group, public issue, public discussion, mailing list or meeting (SEC-040).
- A report found in public must be hidden or removed at once, the reporter asked to use the private channel, and the security team told; the team must treat it as possibly public (SEC-041).
- FPSOT must have a security team of at least three, with published roles and contact, each bound in writing to confidentiality; anyone else who can see private reports, such as an administrator or organization owner, must sign the same pledge; the team decides severity, dates and early release (SEC-042).
- Acknowledge within 3 business days; first assessment within 10 business days; progress updates should come at least every 14 days (SEC-043).
- Score each vulnerability in software with CVSS v4.0 and record the full `CVSS:4.0/` vector; publish the base score labeled `CVSS-B`; threat metrics may be added as `CVSS-BT`; older CVSS versions must not be used for new vulnerabilities (SEC-044).
- Obtain a CVE ID through a CNA for each vulnerability fixed in software, one per independently fixable flaw (SEC-045).
- Publish an advisory at public release in the OSV schema and in the forge's advisory database if it has one, with CVE, affected and fixed versions, CVSS vector, description, workarounds and dates; credit the reporter as they choose unless they decline (SEC-046).
- Add a test that fails on the flaw; look for the root cause and the same flaw elsewhere; should record process changes (SEC-047).
- Keep a private record of each report, its dates and decisions, for at least 5 years (SEC-048).
- For a flaw in an outside component, the security team must follow its maintainers' embargo, must not disclose before their date, may pre-notify members only as they permit, and should report the flaw to them first (SEC-049).

## Pre-notice and disclosure

- Each pre-notice must go to all list members at once; every known adopter meeting the criteria must be able to join; membership must be free; early access must not be sold or tied to any fee, donation, contract or paid service (SEC-050).
- Membership criteria must be published and objective; a member must be a public body (per the statutes and lists of the page; Canada, its provinces and territories only; no foreign governments) that uses an FPSOT component or spec, or a hosting provider or integrator that runs one in production for such a body; it must give a monitored contact that receives encrypted messages and accept SEC-057 to SEC-059 in writing; a vendor that only resells must not be a member; a shared-service body may join in its own right; each refusal must be reasoned in writing (SEC-051).
- The list of member organizations must be published and kept current, without naming contacts (SEC-052).
- A pre-notice must hold the details and the fix, the severity (SEC-044 or SEC-073), affected and fixed versions, workarounds, release date and time, and the duties of SEC-057; it should carry a label limiting it to the member and its named operators, such as `TLP:AMBER` limited to them; it must travel over an encrypted or access-controlled channel (SEC-053).
- Head start: 7 days by default; may be shortened to no less than 72 hours for a simple fix or a suspected leak; may be lengthened to no more than 14 days for a fix that needs integration testing; the limit of SEC-055 wins, so the pre-notice should go out at least 72 hours before it; any other value must be recorded with its reason (SEC-054).
- Public release must happen no later than 90 days after the report; the team may extend it once, by at most 30 days, if the reporter agrees on record; without a fix at the limit, the advisory still goes public with workarounds; release at once when the security team finds the flaw exploited or leaked, and without a fix that release is the advisory with workarounds, with members pre-notified first or at the same time; only the team decides, and members must report signs of either (SEC-055).
- A public date notice must go out about 7 days before release, with date, component and severity only; with a shorter head start it goes out with the pre-notice; an immediate release needs none (SEC-056).
- Members may deploy the fix to systems they operate; they may share the pre-notice with their staff and with the contractors or shared-service bodies that operate their systems, which they must name and which must accept the rules in writing; the member answers for their leaks; members must not share or republish the pre-notice, fix or a fixed image with anyone else before release; they may say a fix is coming and give the release date (SEC-057).
- Members must report a known or suspected leak at once; the team must then assess whether the details leaked, and SEC-055 applies if so; a suspicion alone must not lead to removal (SEC-058).
- The team must remove a member only after a short review shows the leak came through it, with the finding recorded and reasons given in writing; the member may appeal through FPSOT governance and may apply again after 12 months with its corrective steps; a member that reports its own first leak must get a written warning instead of removal, must show corrective steps within 30 days, and a second leak within 24 months leads to removal (SEC-059).

## Supported versions and security files

- Each project must publish its supported versions in `SECURITY.md`, at least the latest minor of the latest major; the previous major should get fixes for at least 12 months on a `release/N.x` branch (SEC-060).
- End of support for a major version must be announced at least 6 months ahead in `SECURITY.md`, release notes and the date-notice channel; no fixes are promised after it, though the team may fix an exploited critical flaw once (SEC-061).
- Each security fix must ship as a patch release of each affected supported version, which should hold nothing else; the changelog must list it under `Security` with its advisory ID (SEC-062).
- Every repository, code or spec, must have a `SECURITY.md` at its root or in `.github/`, in English and French, with the channels, supported versions, times, CVSS version, a disclosure summary with links to the criteria and member list, how to verify a release, and how reporters are credited; the template may be copied (SEC-063).
- Each repository must turn on the forge's private vulnerability reporting or an equal channel; otherwise `SECURITY.md` must point to the second channel (SEC-064).
- Each FPSOT website should publish an RFC 9116 `security.txt` pointing to the same channels (SEC-065).

## Flaws in specifications

- Report a spec flaw through the private channels; the Working Group must not receive or discuss it before release (SEC-070).
- The security team must prepare the fix outside Working Group repositories, such as a private fork; it may ask a spec maintainer to help, who signs the SEC-042 pledge, is named in the SEC-048 record, acts as an individual, does not count toward the three members, and does not use the information for an employer before the pre-notice (SEC-071).
- The fix must ship as a patch release of each supported spec version, even when a rule changes; the changelog must list it under `Security` with each changed rule (SEC-072).
- A spec flaw must follow SEC-050 to SEC-059; the advisory must name the spec, versions and rules at fault; the team may give a low-to-critical rating or score a conforming implementation; a CVE should be requested when a conforming implementation is vulnerable (SEC-073).

## Security tests

- The checks of SEC-012 to SEC-014 must be required checks under TST-060, and failures must block the merge under TST-061 (SEC-080).
- Each product with an API must run a dynamic scan against a running build before each release, using the published description (API-021), against the built artifact (TST-065) with synthetic data only; high or critical findings must block the release unless SEC-016 records an exception (SEC-081).
- Functional or contract tests must check the API security rules the product must meet, including API-080 to API-083 and API-092; a test should prove a caller cannot act on another caller's item (SEC-082).
- The test of a fixed vulnerability must not reach a public repository before the public release; it must merge with or after the fix (SEC-083).
- Security tests must use synthetic data and test credentials only (TST-050); a test credential must not grant access outside the test run (SEC-084).
