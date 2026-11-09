# Terms needed

Entries to add to `termbase/terms.yaml` of `fpsot-spec-writing`, in its format.
TERMIUM Plus could not be read (HTTP 403), so the French comes from the GDT where it has a record.
The GDT has records for "vulnérabilité" and "nomenclature logicielle", the latter with "SBOM" accepted as a loan.
It has no record for CVE, CVSS, NIST, SSDF, ASVS or OSV.
These are names of programs, standards or bodies, so their full form stays in English in French, like the CSV, BCP and CLDR entries.
For CVE and CVSS, the French guideline of the Treasury Board of Canada Secretariat writes "vulnérabilités et expositions communes" and "Système commun de notation des vulnérabilités"; the project lead may prefer these as French full forms.

```yaml
  - id: asvs
    kind: abbreviation
    en: {short: "ASVS", full: "Application Security Verification Standard", definition: "An OWASP standard that lists security requirements for applications, in three levels of assurance."}
    fr: {short: "ASVS", full: "Application Security Verification Standard", definition: "Norme de l'OWASP qui énumère des exigences de sécurité pour les applications, selon trois niveaux d'assurance."}
    source: {name: "OWASP, ASVS 5.0.0 (no GDT record found; TERMIUM Plus could not be read)", url: "https://asvs.owasp.org/", checked: "2026-11-08"}
  - id: cve
    kind: abbreviation
    en: {short: "CVE", full: "Common Vulnerabilities and Exposures", definition: "The program that gives each publicly known vulnerability a unique identifier, such as CVE-2026-12345."}
    fr: {short: "CVE", full: "Common Vulnerabilities and Exposures", definition: "Programme qui donne à chaque vulnérabilité connue du public un identifiant unique, comme CVE-2026-12345."}
    source: {name: "CVE Program (no GDT record found; TERMIUM Plus could not be read; TBS writes « vulnérabilités et expositions communes »)", url: "https://www.cve.org/", checked: "2026-11-08"}
  - id: cvss
    kind: abbreviation
    en: {short: "CVSS", full: "Common Vulnerability Scoring System", definition: "A FIRST standard that scores the severity of a vulnerability from 0 to 10, with a vector string that records each metric."}
    fr: {short: "CVSS", full: "Common Vulnerability Scoring System", definition: "Norme du FIRST qui cote la gravité d'une vulnérabilité de 0 à 10, avec une chaîne vectorielle qui consigne chaque métrique."}
    source: {name: "FIRST, CVSS v4.0 Specification Document (no GDT record found; TERMIUM Plus could not be read; TBS writes « Système commun de notation des vulnérabilités »)", url: "https://www.first.org/cvss/v4.0/specification-document", checked: "2026-11-08"}
  - id: nist
    kind: abbreviation
    en: {short: "NIST", full: "National Institute of Standards and Technology", definition: "The United States federal agency that publishes standards and guidance, including on cybersecurity."}
    fr: {short: "NIST", full: "National Institute of Standards and Technology", definition: "Organisme fédéral des États-Unis qui publie des normes et des lignes directrices, notamment en cybersécurité."}
    source: {name: "NIST (no GDT record found; TERMIUM Plus could not be read)", url: "https://www.nist.gov/", checked: "2026-11-08"}
  - id: osv
    kind: abbreviation
    en: {short: "OSV", full: "Open Source Vulnerability", definition: "An OpenSSF format and database that describe vulnerabilities in open-source packages so that machines can read them."}
    fr: {short: "OSV", full: "Open Source Vulnerability", definition: "Format et base de données de l'OpenSSF qui décrivent les vulnérabilités des paquets libres de façon lisible par machine."}
    source: {name: "OpenSSF, OSV schema 1.9.2 (no GDT record found; TERMIUM Plus could not be read)", url: "https://ossf.github.io/osv-schema/", checked: "2026-11-08"}
  - id: sbom
    kind: abbreviation
    en: {short: "SBOM", full: "software bill of materials", definition: "A machine-readable list of the components of a piece of software, with their versions and origin."}
    fr: {short: "SBOM", full: "nomenclature logicielle", definition: "Liste lisible par machine des composants d'un logiciel, avec leurs versions et leur origine."}
    source: {name: "Grand dictionnaire terminologique (SBOM accepted as a loan)", url: "https://vitrinelinguistique.oqlf.gouv.qc.ca/fiche-gdt/fiche/26584382/nomenclature-logicielle", checked: "2026-11-08"}
  - id: ssdf
    kind: abbreviation
    en: {short: "SSDF", full: "Secure Software Development Framework", definition: "A NIST framework of practices that lower the number and the impact of vulnerabilities in software."}
    fr: {short: "SSDF", full: "Secure Software Development Framework", definition: "Cadre du NIST qui regroupe des pratiques pour réduire le nombre et l'impact des vulnérabilités des logiciels."}
    source: {name: "NIST SP 800-218, version 1.1 (no GDT record found; TERMIUM Plus could not be read)", url: "https://csrc.nist.gov/pubs/sp/800/218/final", checked: "2026-11-08"}
  - id: vulnerability
    kind: term
    en: {full: "vulnerability", definition: "A weakness in software or in a specification that an attacker can exploit to harm its security."}
    fr: {full: "vulnérabilité", definition: "Faiblesse d'un logiciel ou d'une spécification qu'un attaquant peut exploiter pour nuire à sa sécurité."}
    source: {name: "Grand dictionnaire terminologique", url: "https://vitrinelinguistique.oqlf.gouv.qc.ca/fiche-gdt/fiche/26578865/vulnerabilite", checked: "2026-11-08"}
```
