---
title: 🧭 Trajectoire interopérabilité
nav_order: 1
description: 
---


## Qu'est-ce que l'interopérabilité ?

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum

## Stratégie des versions FHIR

La stratégie sur le choix des versions FHIR a été définie au sein d'un groupe de travail organisé entre InteropSanté et l'ANS en 2023/2024, complétée par une [concertation](https://participez.esante.gouv.fr/project/fhir-r5-ou-r4/presentation/presentation) de l'ANS. Les conclusions de ce GT sont indiquées ci-dessous.

### Nouveaux cas d’usages FHIR adressés par Interop’Santé et l’ANS : privilégier FHIR R4

Pour garantir un écosystème cohérent, il est nécessaire de privilégier l’usage de FHIR R4.

Dans certains cas, une autre version de FHIR peut être justifiée, par exemple pour des besoins d’échanges internationaux ou pour des ressources qui ont beaucoup évolué en termes de modélisation ou de maturité entre deux versions (ex : ressources médicament). Le cas échéant, l’usage d’une nouvelle version devra être validé par une étude des normes et standards et par l’écosystème.

Dans certains cas non identifiés encore à ce jour, il pourrait être nécessaire de maintenir des guides d’implémentation sous plusieurs versions. Après validation par l’écosystème de ce besoin, cela donnerait l’opportunité d’essayer des travaux de maintenance d’Implementation Guide (IG) sous plusieurs versions ainsi qu’un mapping associé pour gagner en expérience et estimer la charge.

### Ne pas créer d’IG FrCore R5 sans cas d’usage identifié

Cela engendrerait une fragmentation de l’écosystème et un ralentissement de la mise en qualité de l’existant qui finirait par freiner l’adoption de FHIR.

La priorité actuelle est de faire monter l’écosystème en compétences et de gagner en maturité sur les spécifications existantes.

S’il y a un cas d’usage dont l’usage de FHIR R5 a été justifié, et que celui-ci nécessite des profils nationaux (FrCore) :

* Créer un profil FrCore dans l’IG du cas d’usage en mimant ce qui a été fait en R4 (comme dans cet IG autrichien)
* Si le besoin de profils est répété au niveau de plusieurs cas d’usages, créer un IG FrCore R5 à alimenter progressivement avec de nouveaux profils.

### Anticiper dès à présent la transition vers R6

La release 6 se veut être la “final stable version” de FHIR, une transition vers R6 se veut donc nécessaire. Pour anticiper cette transition, il est jugé important d’être proactif sur les travaux
internationaux sur R6 et d’anticiper les impacts pour l’écosystème FR.

### Priorité FHIR France en 2024 et 2025 - Améliorer la qualité de l’existant

Beaucoup de travaux ont été menés en 2023 tels que le passage au format IG et la mise à jour des tests et validateurs gazelle, …

En 2024 et 2025, les priorités sont :

* La montée en compétences et l’acculturation des développeurs aux bonnes pratiques d’usages de FHIR
* S’assurer de la faisabilité d’implémentation des IGs existants (amélioration du contenu narratif pour expliquer comment utiliser les ressources, s’assurer de la facilité d’accès au contenu, …).
* La prise en main des outils de mapping tel que le FHIR Mapping Language afin d'assurer une transition maîtrisée vers une autre version de FHIR.

Il est également nécessaire de rester à l’écoute des tendances internationales en interopérabilitéet de se garder la possibilité de réitérer l’analyse si le besoin a évolué.

## Cartographie de l'interopérabilité

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum

## Listing des acteurs influençant la trajectoire

Il est important de noter que de nombreux acteurs influencent la trajectoire et que le rôle des experts interopérabilité est d'avoir cette vision globale pour répondre aux besoins en réutilisant au maximum les travaux existants au niveau internationale.

Les acteurs peuvent se classifier sur plusieurs statuts : au niveau politique, au niveau technique et au niveau implémentation.

## Focus FHIR Document

Aujourd'hui en France, l'ensemble des documents médicaux sont stockés en CDA, notamment avec la plus grande plateforme technique médicale nationale : le DMP, brique de Mon Espace Santé. Le nouveau standard d'interopérabilité FHIR, connu pour son API Rest standard, est utilisé dans de nombreux cas d'usages en France : l'annuaire santé, le ROR, le SAS, Mon Espace Santé, .... L'usage de FHIR peut être étendu aux documents

### Etude internationale

Selon l'étude [2024 State of FHIR survey](../../assets/docs/2024 StateofFHIRSurveyResults_final.pdf), la majorité des pays voit une forte augmentation de l'usage de FHIR.

![](../../assets/images/fhir-adoption-rate-change.png)

Cette étude dévoile également un nombre important de pays utilisant le FHIR document.

![](../../assets/images/fhir-document.png)

De plus, les projets européens European Health Data Space (EHDS) ayant fait une étude de normes et standards pour les échanges transfrontaliers au sein de l'Europe a conclu sur l'usage du FHIR Document. Ce choix est justifié par le fait que certains pays n'ont pas d'historiques et choisissent très logiquement d'utiliser le standard FHIR étant plus récent et plus à la mode.

### Intérêt d'usage du FHIR document

En plus de la trajectoire internationale semblant mener vers l'usage du FHIR document, des avantages non négligeables sont à noter sur l'usage de ce nouveau standard

* Les FHIR Document sont composés d'une multitude de brique, appelée ressource (ex : Observation, Patient, Encounter, ...) qui peuvent être extraites du document facilement pour être consommées et réutilisées au sein d'une API Rest par exemple.
* Les spécifications peuvent être publiées en open source sur GitHub car leur édition est totalement en mode texte (FSH / markdown), permettant ainsi de faciliter la collaboration, la remontée d'erreurs, la participation de l'écosystème, l'automatisation des différences entre les versions et du changelog, l'historisation automatique des anciennes versions, ...

### Avis de l'Agence du Numerique en Santé

Il existe deux possibilités quant à l'usage du standard FHIR dans la gestion des documents en France :

#### Mettre en place une transformation entre les standards CDA et FHIR

Ces travaux ont un défaut : la nécessité de maintenir le mapping entre les standards avec les nouvelles versions des spécifications CDA et FHIR qui vont sortir, avec un grand niveau de difficulté. Par exemple, des [travaux italiens sur ce sujet](https://build.fhir.org/ig/hl7-it/cda2fhir/index.html) contiennent plusieurs dizaines de miliers de lignes. Il y a également des questionnements quant à la nature de la donnée.

#### Permettre une utilisation concommitante de FHIR et de CDA le temps d'une transition vers FHIR

## Actions menées pour encourager l'interopérabilité

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum

## Le paradigme "Document" du DMP à compléter par un service orienté donnée
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum
