<!--
Template of the FPSOT security specification (SEC-063). Copy this file to the root of a repository,
or to its .github/ folder, and replace each <placeholder>. Keep both languages, and keep them in step.
In "Verify a release", keep only the paragraph for the kind of repository: software component or specification.
Gabarit de la spécification FPSOT sur la sécurité (SEC-063). Copiez ce fichier à la racine d'un dépôt,
ou dans son dossier .github/, et remplacez chaque <espace réservé>. Gardez les deux langues à jour ensemble.
Dans « Vérifier une version », gardez seulement le paragraphe du type de dépôt : composant logiciel ou spécification.
-->

# Security policy / Politique de sécurité

[English](#english) · [Français](#français)

## English

### Report a vulnerability

Report a vulnerability in private. **Do not open a public issue, pull request or discussion. Do not tell a Working Group, its meetings or its mailing lists.** Under section 5 of the Community Specification 1.0 governance, information shared in Working Group activity is not confidential.

Use one of these private channels:

1. The private vulnerability reporting of this repository: **Security** tab, then **Report a vulnerability**.
2. Email <security contact address>, encrypted with the key at <key URL> if you can.

Please give the affected version, the steps to reproduce the flaw and its impact as you see it. You may write in English or in French.

If you find a vulnerability in a specification, report it the same way.

### What happens next

- We acknowledge your report within **3 business days**.
- Within **10 business days**, we tell you whether we accept it and how severe we think it is. We score a vulnerability in software with **CVSS v4.0**. For a flaw in a specification, we give a rating from low to critical, or score a conforming implementation.
- We tell you of our progress at least every **14 days**.
- For a vulnerability in software, we obtain a CVE identifier. For a flaw in a specification, we request one when a conforming implementation is vulnerable.
- We publish an advisory in the OSV format at the public release.
- We credit you in the advisory, under the name you choose, unless you ask us not to.

### Disclosure

FPSOT follows coordinated disclosure:

1. We fix the vulnerability in private.
2. We send a **pre-notice**, with the details and the fix, to all members of the pre-notice list at the same time. The list is free of charge. It is open to public bodies that use an FPSOT component, and to the hosting providers and integrators that run it in production for them, under the published criteria. Nobody can buy early access.
3. About **7 days** before the release, we publish a **public date notice** at <notice channel URL>. It gives the date, the component and the severity, and no details. When the head start is shorter, the notice goes out with the pre-notice.
4. The **public release** comes 7 days after the pre-notice by default. That head start is never shorter than 72 hours, nor longer than 14 days, unless the 90-day limit below leaves less time.
5. Every vulnerability becomes public no later than **90 days** after we receive the report. With your agreement, we may extend this once, by at most 30 days. Without a fix by then, we publish the advisory with the known workarounds.
6. If the vulnerability is exploited, or its details leak, the FPSOT security team releases at once, with no date notice. Without a fix, that release is the advisory with the known workarounds.

If the flaw is in an outside component, we follow the embargo of its maintainers.

The criteria of the pre-notice list are at <criteria URL>, and its members are listed at <member list URL>. Members may deploy the fix on the systems they operate before the release. They may share the pre-notice with their staff, and with the contractors or shared-service bodies they name that operate their systems, which accept the same rules in writing. They may say that a fix is coming and give the date of the release. They must not share or republish it with anyone else, and they must report any leak at once. A member is removed only after a short review shows that a leak came through it. It may appeal, and may apply again after 12 months.

### Supported versions

| Version | Security fixes until |
|---|---|
| <N.x> | <supported, or a date> |
| <N-1.x> | <date> |

We announce the end of support for a major version at least 6 months ahead.

### Verify a release

<!-- Software component repository: -->
Each release comes with signatures, a CycloneDX SBOM and SLSA provenance. To verify a release, see <verification instructions URL>.

<!-- Specification repository: -->
Each release is a signed Git tag. To verify the tag, see <verification instructions URL>.

## Français

### Signaler une vulnérabilité

Signalez une vulnérabilité en privé. **N'ouvrez pas de billet, de demande de fusion ni de discussion publics. N'en parlez pas à un groupe de travail, à ses réunions ni à ses listes de diffusion.** Selon la section 5 de la gouvernance de la Community Specification 1.0, l'information transmise dans le cadre des activités d'un groupe de travail n'est pas confidentielle.

Employez l'un de ces canaux privés :

1. Le signalement privé de vulnérabilités de ce dépôt : onglet **Security**, puis **Report a vulnerability**.
2. Le courriel <adresse de sécurité>, chiffré avec la clé à <URL de la clé> si possible.

Donnez la version touchée, les étapes pour reproduire la faille et son impact selon vous. Vous pouvez écrire en français ou en anglais.

Si vous trouvez une vulnérabilité dans une spécification, signalez-la de la même façon.

### La suite

- Nous accusons réception de votre signalement dans un délai de **3 jours ouvrables**.
- Dans un délai de **10 jours ouvrables**, nous vous disons si nous l'acceptons et quelle gravité nous lui donnons. Nous cotons une vulnérabilité d'un logiciel avec le **CVSS v4.0**. Pour une faille dans une spécification, nous donnons une gravité de faible à critique, ou nous cotons une mise en œuvre conforme.
- Nous vous informons de nos progrès au moins tous les **14 jours**.
- Pour une vulnérabilité d'un logiciel, nous obtenons un identifiant CVE. Pour une faille dans une spécification, nous en demandons un quand une mise en œuvre conforme est vulnérable.
- Nous publions un avis au format OSV au moment de la publication.
- Nous vous remercions dans l'avis, sous le nom de votre choix, sauf si vous nous demandez de ne pas le faire.

### Divulgation

FPSOT suit la divulgation coordonnée :

1. Nous corrigeons la vulnérabilité en privé.
2. Nous envoyons un **préavis**, avec les détails et la correction, à tous les membres de la liste de préavis en même temps. La liste est gratuite. Elle est ouverte aux organismes publics qui emploient un composant de FPSOT, et aux hébergeurs et intégrateurs qui l'exploitent en production pour eux, selon les critères publiés. Personne ne peut acheter un accès anticipé.
3. Environ **7 jours** avant la publication, nous publions un **avis public de date** à <URL du canal des avis>. Il donne la date, le composant et la gravité, sans aucun détail. Quand l'avance est plus courte, l'avis part avec le préavis.
4. La **publication** a lieu 7 jours après le préavis par défaut. Cette avance n'est jamais inférieure à 72 heures, ni supérieure à 14 jours, sauf si la limite de 90 jours ci-dessous laisse moins de temps.
5. Chaque vulnérabilité devient publique au plus tard **90 jours** après la réception du signalement. Avec votre accord, nous pouvons reporter cette limite une fois, d'au plus 30 jours. Sans correction à cette date, nous publions l'avis avec les solutions de contournement connues.
6. Si la vulnérabilité est exploitée, ou si ses détails fuient, l'équipe de sécurité de FPSOT publie immédiatement, sans avis de date. Sans correction, cette publication est l'avis avec les solutions de contournement connues.

Si la faille se trouve dans un composant externe, nous suivons l'embargo de ses responsables.

Les critères de la liste de préavis sont à <URL des critères>, et la liste de ses membres est à <URL de la liste des membres>. Les membres peuvent déployer la correction sur les systèmes qu'ils exploitent avant la publication. Ils peuvent transmettre le préavis à leur personnel, et aux entreprises ou organismes de services partagés qu'ils désignent et qui exploitent leurs systèmes, qui acceptent les mêmes règles par écrit. Ils peuvent dire qu'une correction est à venir et donner la date de la publication. Ils ne doivent pas la transmettre ni la republier à quiconque d'autre, et doivent signaler toute fuite sans délai. Un membre est retiré seulement si une courte revue montre qu'une fuite est passée par lui. Il peut faire appel, et présenter une nouvelle demande après 12 mois.

### Versions prises en charge

| Version | Corrections de sécurité jusqu'au |
|---|---|
| <N.x> | <prise en charge, ou une date> |
| <N-1.x> | <date> |

Nous annonçons la fin de la prise en charge d'une version majeure au moins 6 mois à l'avance.

### Vérifier une version

<!-- Dépôt d'un composant logiciel : -->
Chaque version est accompagnée de signatures, d'une nomenclature logicielle CycloneDX et d'une provenance SLSA. Pour vérifier une version, consultez <URL des instructions de vérification>.

<!-- Dépôt de spécification : -->
Chaque version est une étiquette Git signée. Pour vérifier l'étiquette, consultez <URL des instructions de vérification>.
