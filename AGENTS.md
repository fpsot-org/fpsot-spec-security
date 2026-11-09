# Instructions for agents

This repository holds the FPSOT security specification: secure development (an SSDF 1.1 profile, threat models, ASVS 5.0.0 levels), review and analysis in continuous integration, secrets, the supply chain (pinning, SBOM, provenance, signatures), vulnerability reporting and handling, pre-notice and disclosure, supported versions, `SECURITY.md`, flaws in specifications and security tests.

- The normative text is in `spec/en/` and `spec/fr/`. Every rule has an ID such as `SEC-001`.
- Follow `skill/SKILL.md` when you write or review security-relevant code, CI workflows, releases or security policies in any FPSOT project. The spec text wins on any difference.
- Never put a real vulnerability, a secret or a credential in an issue, a pull request, a commit or a test of a public repository. Vulnerabilities go through the private channels of SEC-040, never through a Working Group.
- The template `examples/SECURITY.md` holds English and French in one file. Change both languages in the same commit.
- Every page exists in English and in French, with the same file name and the same IDs.
- Terms and abbreviations come from the term base of `fpsot-spec-writing`. Add a missing term there first.
- This is a layer 1 specification. It may refer to the layer 0 specifications, to data types, vocabularies, data models, api-restful and testing. It never refers to the registry, code or capability specifications, except by topic as future work.
- Do not name a vendor tool or a paid service in a rule. Name the capability; tools may appear only as examples.
- Do not copy text from NIST, OWASP, ISO, FIRST or the Cyber Centre. Summarize in your own words and cite the exact version. ASVS text is CC BY-SA.
- Do not state a legal point as a rule. Points that need a lawyer go in an informative note.
- Commits follow Conventional Commits and are signed. Pull requests are squash-merged.
