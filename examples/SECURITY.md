<!--
Template of the FPSOT security specification (SEC-063). Copy this file to the root of a repository,
or to its .github/ folder, and replace each <placeholder>. Keep both languages, and keep them in step.
Gabarit de la spécification FPSOT sur la sécurité (SEC-063). Copiez ce fichier à la racine d'un dépôt,
ou dans son dossier .github/, et remplacez chaque <espace réservé>. Gardez les deux langues à jour ensemble.
-->

# Security policy / Politique de sécurité

[English](#english) · [Français](#français)

## English

### Report a vulnerability

Report a vulnerability in private. **Do not open a public issue, pull request or discussion. Do not tell a Working Group, its meetings or its mailing lists.** Information shared in Working Group activity is not confidential under section 5 of the Community Specification 1.0 governance.

Use one of these private channels:

1. The private vulnerability reporting of this repository: **Security** tab, then **Report a vulnerability**.
2. Email <security contact address>, encrypted with the key at <key URL> if you can.

Please give the affected version, the steps to reproduce the flaw and its impact as you see it. You may write in English or in French.

If you find a vulnerability in a specification, report it the same way.

### What happens next

- We acknowledge your report within **3 business days**.
- Within **10 business days**, we tell you whether we accept it and how severe we think it is. We score each vulnerability with **CVSS v4.0**.
- We tell you of our progress at least every **14 days**.
- We obtain a CVE identifier and publish an advisory in the OSV format when we release the fix.
- We credit you in the advisory, under the name you choose, unless you ask us not to.

### Disclosure

FPSOT follows coordinated disclosure:

1. We fix the vulnerability in private.
2. We send a **pre-notice**, with the details and the fix, to the members of the pre-notice list, all at the same time. The list is open, free of charge, to every public-sector adopter that meets the published criteria. Nobody can buy early access.
3. About **7 days** before the release, we publish a **public date notice** at <notice channel URL>. It gives the date, the component and the severity, and no details.
4. The **public release** comes 7 days after the pre-notice by default. That head start is never shorter than 72 hours, nor longer than 14 days.
5. Every vulnerability becomes public no later than **90 days** after we receive the report.
6. If the vulnerability is exploited, or its details leak, the FPSOT security team releases at once.

The criteria of the pre-notice list are at <criteria URL>, and its members are listed at <member list URL>. Members may deploy the fix on the systems they operate before the release. They must not share or republish it, and they must report any leak at once. A leak ends membership.

### Supported versions

| Version | Security fixes until |
|---|---|
| <N.x> | <supported, or a date> |
| <N-1.x> | <date> |

We announce the end of support for a major version at least 6 months ahead.

### Verify a release

Each release comes with signatures, a CycloneDX SBOM and SLSA provenance. To verify a release, see <verification instructions URL>.

## Français

### Signaler une vulnérabilité

Signalez une vulnérabilité en privé. **N'ouvrez pas de billet, de demande de fusion ni de discussion publics. N'en parlez pas à un groupe de travail, à ses réunions ni à ses listes de diffusion.** L'information transmise dans le cadre des activités d'un groupe de travail n'est pas confidentielle selon la section 5 de la gouvernance de la Community Specification 1.0.

Employez l'un de ces canaux privés :

1. Le signalement privé de vulnérabilités de ce dépôt : onglet **Security**, puis **Report a vulnerability**.
2. Le courriel <adresse de sécurité>, chiffré avec la clé à <URL de la clé> si possible.

Donnez la version touchée, les étapes pour reproduire la faille et son impact selon vous. Vous pouvez écrire en français ou en anglais.

Si vous trouvez une vulnérabilité dans une spécification, signalez-la de la même façon.

### La suite

- Nous accusons réception de votre signalement dans un délai de **3 jours ouvrables**.
- Dans un délai de **10 jours ouvrables**, nous vous disons si nous l'acceptons et quelle gravité nous lui donnons. Nous cotons chaque vulnérabilité avec le **CVSS v4.0**.
- Nous vous informons de nos progrès au moins tous les **14 jours**.
- Nous obtenons un identifiant CVE et publions un avis au format OSV quand nous publions la correction.
- Nous vous remercions dans l'avis, sous le nom de votre choix, sauf si vous nous demandez de ne pas le faire.

### Divulgation

FPSOT suit la divulgation coordonnée :

1. Nous corrigeons la vulnérabilité en privé.
2. Nous envoyons un **préavis**, avec les détails et la correction, aux membres de la liste de préavis, tous en même temps. La liste est ouverte, sans frais, à toute organisation du secteur public qui adopte nos composants et qui respecte les critères publiés. Personne ne peut acheter un accès anticipé.
3. Environ **7 jours** avant la publication, nous publions un **avis public de date** à <URL du canal des avis>. Il donne la date, le composant et la gravité, sans aucun détail.
4. La **publication** a lieu 7 jours après le préavis par défaut. Cette avance n'est jamais inférieure à 72 heures, ni supérieure à 14 jours.
5. Chaque vulnérabilité devient publique au plus tard **90 jours** après la réception du signalement.
6. Si la vulnérabilité est exploitée, ou si ses détails fuient, l'équipe de sécurité de FPSOT publie immédiatement.

Les critères de la liste de préavis sont à <URL des critères>, et la liste de ses membres est à <URL de la liste des membres>. Les membres peuvent déployer la correction sur les systèmes qu'ils exploitent avant la publication. Ils ne doivent pas la transmettre ni la republier, et doivent signaler toute fuite sans délai. Une fuite met fin à l'adhésion.

### Versions prises en charge

| Version | Corrections de sécurité jusqu'au |
|---|---|
| <N.x> | <prise en charge, ou une date> |
| <N-1.x> | <date> |

Nous annonçons la fin de la prise en charge d'une version majeure au moins 6 mois à l'avance.

### Vérifier une version

Chaque version est accompagnée de signatures, d'une nomenclature logicielle CycloneDX et d'une provenance SLSA. Pour vérifier une version, consultez <URL des instructions de vérification>.
