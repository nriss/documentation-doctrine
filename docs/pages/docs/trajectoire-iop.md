---
title: 🧭 Trajectoire interopérabilité
nav_order: 1
description: 
---


<!-- TOC generated with Auto Markdown TOC 
Nom : Auto Markdown TOC
ID : xavierguarch.auto-markdown-toc
Description : Markdown TOC (Table Of Contents) Plugin for Visual Studio Code.
Version : 2.1.4
Serveur de publication : Xavier Guarch
Lien de la Place de marché pour VS : https://marketplace.visualstudio.com/items?itemName=xavierguarch.auto-markdown-toc -->

<!-- TOC -->

- [Qu'est-ce que l'interopérabilité ?](#quest-ce-que-linterop%C3%A9rabilit%C3%A9-)
- [Stratégie des versions FHIR](#strat%C3%A9gie-des-versions-fhir)
    - [Nouveaux cas d’usages FHIR adressés par Interop’Santé et l’ANS : privilégier FHIR R4 et anticiper la transition vers R6](#nouveaux-cas-dusages-fhir-adress%C3%A9s-par-interopsant%C3%A9-et-lans--privil%C3%A9gier-fhir-r4-et-anticiper-la-transition-vers-r6)
    - [Ne pas créer d’IG se basant sur R5 sans cas d’usage identifié](#ne-pas-cr%C3%A9er-dig-se-basant-sur-r5-sans-cas-dusage-identifi%C3%A9)
    - [Priorité FHIR France en 2024 et 2025 - Améliorer la qualité de l’existant](#priorit%C3%A9-fhir-france-en-2024-et-2025---am%C3%A9liorer-la-qualit%C3%A9-de-lexistant)
- [Listing des acteurs influençant la trajectoire](#listing-des-acteurs-influen%C3%A7ant-la-trajectoire)
    - [Les acteurs dits "politiques"](#les-acteurs-dits-politiques)
    - [Les acteurs dits "techniques"](#les-acteurs-dits-techniques)
    - [Les acteurs dits "implémenteurs"](#les-acteurs-dits-impl%C3%A9menteurs)
- [Focus FHIR Document](#focus-fhir-document)
    - [Etude internationale](#etude-internationale)
    - [Intérêt d'usage du FHIR document](#int%C3%A9r%C3%AAt-dusage-du-fhir-document)
    - [Position de l'Agence du Numerique en Santé](#position-de-lagence-du-numerique-en-sant%C3%A9)
        - [Mettre en place une transformation entre les standards CDA et FHIR](#mettre-en-place-une-transformation-entre-les-standards-cda-et-fhir)
        - [Permettre une utilisation concommitante de FHIR et de CDA le temps d'une transition vers FHIR](#permettre-une-utilisation-concommitante-de-fhir-et-de-cda-le-temps-dune-transition-vers-fhir)
- [Actions menées pour encourager l'interopérabilité](#actions-men%C3%A9es-pour-encourager-linterop%C3%A9rabilit%C3%A9)
- [Le paradigme "Document" du DMP à compléter par un service orienté donnée](#le-paradigme-document-du-dmp-%C3%A0-compl%C3%A9ter-par-un-service-orient%C3%A9-donn%C3%A9e)

<!-- /TOC -->
<!-- /TOC -->


## Qu'est-ce que l'interopérabilité ?

L'interopérabilité en e-santé consiste à trouver un langage informatique uniforme entre les différents systèmes d'information pour que celles-ci soient intégrables directement dans les logiciels, réutilisables, et exploitables. Pour cela, il faut construire ce langage de manière collaborative, avec l'ensemble des acteurs du système. Cela permet d'avoir une vision la plus large possible, et en s'appuyant sur les travaux et standards internationaux existants pour assurer une compatibilité à la plus grande échelle possible.

L'interopérabilité doit être pensé au plus tôt au moment de la conception du logiciel, "interoperability by design", car une fois des interfaces graphiques développées totalement corrélées aux flux propriétaires, il est bien plus coûteux de faire l'évolution dans l'autre sens.

Un langage de données commun permet un partage et un accès facilité à la donnée, ce qui a une plus-value immense pour le patient, mais aussi pour la recherche clinique.

L'interopérabilité est souvent confondue avec référencement, or ils ne sont pas synonymes. Les référencements peuvent avoir des exigences d'interopérabilité, c'est à dire la nécessité de respecter certains modèles de données, mais les exigences peuvent être beaucoup plus larges : sécurité, hébergement HDS, ...

Le rôle de l'expert interopérabilité est d'assurer une veille et de comprendre le besoin fonctionnel du projet pour appliquer les standards au cas d'usage en question.

## Stratégie des versions FHIR

La stratégie sur le choix des versions FHIR a été définie au sein d'un groupe de travail organisé entre InteropSanté et l'ANS en 2023/2024, complétée par une [concertation](https://participez.esante.gouv.fr/project/fhir-r5-ou-r4/presentation/presentation) de l'ANS. Les conclusions de ce GT sont indiquées ci-dessous.

Aux Etats-Unis, les spécifications CDA sont publiées sont forme de guide d'implémentation en modèle logique, permettant ainsi de valider les CDA avec le FHIR Validator avec pour objectif de laissaer tomber les schematrons [https://build.fhir.org/ig/HL7/CDA-ccda/validation.html#:~:text=Validation%20Note-,What%20happened%20to%20the%20Schematron%3F,of%20the%20C%2DCDA%20document.](source)

### Nouveaux cas d’usages FHIR adressés par Interop’Santé et l’ANS : privilégier FHIR R4 et anticiper la transition vers R6

Pour garantir un écosystème cohérent, il est nécessaire de privilégier l’usage de FHIR R4.

Dans certains cas, une autre version de FHIR peut être justifiée, par exemple pour des besoins d’échanges internationaux ou pour des ressources qui ont beaucoup évolué en termes de modélisation ou de maturité entre deux versions (ex : ressources médicament). Le cas échéant, l’usage d’une nouvelle version devra être validé par une étude des normes et standards et par l’écosystème.
Dans certains cas non identifiés encore à ce jour, il pourrait également être nécessaire de maintenir des guides d’implémentation sous plusieurs versions. Après validation par l’écosystème de ce besoin, cela donnerait l’opportunité d’essayer des travaux de maintenance d’Implementation Guide (IG) sous plusieurs versions ainsi qu’un mapping associé pour gagner en expérience et estimer la charge.

D'autre part, la release 6 se veut être la “final stable version” de FHIR, une transition vers R6 se veut donc nécessaire. Pour anticiper cette transition, il est jugé important d’être proactif sur les travaux
internationaux sur R6 et d’anticiper les impacts pour l’écosystème FR.

### Ne pas créer d’IG se basant sur R5 sans cas d’usage identifié

La priorité actuelle est de faire monter l’écosystème en compétences et de gagner en maturité sur les spécifications existantes. Créer des IGs R5 engendreraient une fragmentation de l’écosystème et un ralentissement de la mise en qualité de l’existant qui finirait par freiner l’adoption de FHIR.

S’il y a un cas d’usage dont l’usage de FHIR R5 a été justifié, et que celui-ci nécessite des profils nationaux (FrCore) :
<ul>
<li> Créer un profil FrCore dans l’IG du cas d’usage en mimant ce qui a été fait en R4 (comme dans cet IG autrichien) </li>
<li> Si le besoin de profils est répété au niveau de plusieurs cas d’usages, créer un IG FrCore R5 à alimenter progressivement avec de nouveaux profils. </li>
</ul>

### Priorité FHIR France en 2024 et 2025 - Améliorer la qualité de l’existant

Beaucoup de travaux ont été menés en 2023 tels que le passage au format IG et la mise à jour des tests et validateurs gazelle.

En 2024 et 2025, les priorités sont :

- La montée en compétences et l’acculturation des développeurs aux bonnes pratiques d’usages de FHIR
- S’assurer de la faisabilité d’implémentation des IGs existants (amélioration du contenu narratif pour expliquer comment utiliser les ressources, s’assurer de la facilité d’accès au contenu, …).
- La prise en main des outils de mapping tel que le FHIR Mapping Language afin d'assurer une transition maîtrisée vers une autre version de FHIR.

Il est également nécessaire de rester à l’écoute des tendances internationales en interopérabilitéet de se garder la possibilité de réitérer l’analyse si le besoin a évolué.

<!-- ## Cartographie de l'interopérabilité -->

## Listing des acteurs influençant la trajectoire

Il est important de noter que de nombreux acteurs influencent la trajectoire et que le rôle des experts interopérabilité est d'avoir cette vision globale pour répondre aux besoins en réutilisant au maximum les travaux existants au niveau internationale.

Les acteurs peuvent se classifier sur plusieurs statuts : au niveau politique, au niveau technique et au niveau implémentation.

### Les acteurs dits "politiques"

Ministère de la santé, commission européenne, EHDS

### Les acteurs dits "techniques"

IHE, HL7 International, HL7 Europe

### Les acteurs dits "implémenteurs"

La CNAM (DMP, Mon Espace Santé), l'écosystème français des éditeurs de logiciels de soin

## Focus FHIR Document

Aujourd'hui en France, l'ensemble des documents médicaux sont stockés en CDA, notamment avec la plus grande plateforme technique médicale nationale : le DMP, brique de Mon Espace Santé. Le nouveau standard d'interopérabilité FHIR, connu pour son API Rest standard, est utilisé dans de nombreux cas d'usages en France : l'annuaire santé, le ROR, le SAS, Mon Espace Santé, .... L'usage de FHIR peut être étendu aux documents.

### Etude internationale

Selon l'étude [2024 State of FHIR survey](../../assets/docs/2024 StateofFHIRSurveyResults_final.pdf), la majorité des pays voit une forte augmentation de l'usage de FHIR.

![](../../assets/images/fhir-adoption-rate-change.png)

Cette étude dévoile également un nombre important de pays utilisant le FHIR document.

![](../../assets/images/fhir-document.png)

De plus, les projets européens European Health Data Space (EHDS) ayant fait une étude de normes et standards pour les échanges transfrontaliers au sein de l'Europe a conclu sur l'usage du FHIR Document. Ce choix est justifié par le fait que certains pays n'ont pas d'historiques et choisissent très logiquement d'utiliser le standard FHIR étant plus récent et plus à la mode.
FHIR a été choisi comme standard largement préféré pour les trois cas d'usages identifiés par l'europe comme partage transfrontalier : le lab report, l'hospital discharge report et enfin le medical imaging report (resp. 18, 17 et 16 membres préféraient FHIR contre 3, 5 et 5 pour CDA).

### Intérêt d'usage du FHIR document

En plus de la trajectoire internationale semblant mener vers l'usage du FHIR document, des avantages non négligeables sont à noter sur l'usage de ce nouveau standard

<div class="wysiwyg">
    <ul>
        <li>Les FHIR Document sont composés d'une multitude de brique, appelée ressource (ex : Observation, Patient, Encounter, ...) qui peuvent être extraites du document facilement pour être consommées et réutilisées au sein d'une API Rest par exemple.</li>
        <li>Les spécifications peuvent être publiées en open source sur GitHub car leur édition est totalement en mode texte (FSH / markdown), permettant ainsi de faciliter la collaboration, la remontée d'erreurs, la participation de l'écosystème, l'automatisation des différences entre les versions et du changelog, l'historisation automatique des anciennes versions, ...</li>
        <li>Les développements faits seront facilement réutilisables à l'international (ex : Lab Report d'HL7 Europe dévié pour la France) --> Facilite l'internationalisation des entreprises</li>
    </ul>
</div>

### Position de l'Agence du Numerique en Santé

Il est à ce point indéniable qu'il est nécessaire de prioriser la prise en charge du FHIR document, les nombreux indices sur les études internationales et certains projets open sources lancés mettent en lumière le consensus international sur l'utilisation du FHIR Document.

Il existe deux possibilités quant à l'usage du standard FHIR dans la gestion des documents en France

#### Mettre en place une transformation entre les standards CDA et FHIR

Ces travaux ont un défaut : la nécessité de maintenir le mapping entre les standards avec les nouvelles versions des spécifications CDA et FHIR qui vont sortir, avec un grand niveau de difficulté. Par exemple, des [travaux italiens sur ce sujet](https://build.fhir.org/ig/hl7-it/cda2fhir/index.html) contiennent plusieurs dizaines de miliers de lignes. Il y a également des questionnements quant à la responsabilité : qui serait responsable d'une erreur de transformation ?
La solution choisie pour l'ANS pour l'heure est de faire une preuve de concept d'un mapping CDA - FHIR, générique, sans aller jusqu'à une spécification validée et utilisable en production

Pour une transformation des CDA vers FHIR complète, il faudrait que l'ensemble des spécifications CDA françaises soient définies au format StructureDefinition pour utiliser le FHIR Mapping Language.

#### Permettre une utilisation concommitante de FHIR et de CDA le temps d'une transition vers FHIR

La solution qui semble la plus logique est de permettre une utilisation concommitante de FHIR et de CDA, où les spécifications seront publiées selon les deux modes. Cela permettrait une transition douce avec un timing au choix de chacun vers le passage au paradigme FHIR Document.

Ainsi, au même titre que les documents CDA ne sont pas automatiquement transformés vers les nouvelles versions des spécifications, les documents historiques resteront au format CDA et les nouveaux au format FHIR Document.

## Actions menées pour encourager l'interopérabilité

Gazelle, SMT, GitHub, PAT

## Le paradigme "Document" du DMP à compléter par un service orienté donnée

L'historique français avec le DMP montre le cas d'usage "document" : un document est un compte rendu médical signé et daté d'un patient. Il est possible de voir un nouveau cas d'usage qui n'est pas orienté document mais plutôt "donnée unitaire" où une API Rest peut être davantage adatée.

Il y a par exemple déjà actuellement les API Mesures de santé et Agenda de mon espace santé où il y a des données accessibles via des requêtes REST sans document médical.

Ainsi, il ne faudra pas négliger ce paradigme API REST de données unitaires pour certains cas d'usages s'y pretant bien, comme par exemple une API de vaccination, une API Cercle de Soins, une API pour la diffusion des essais cliniques ouverts au recrutement, etc ...