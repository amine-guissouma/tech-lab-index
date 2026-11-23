# Git Registry

## 1. Présentation

**Git Registry** est un projet en phase de conception visant à développer un système générique de gestion de registres versionnés avec Git.

Il est né des besoins rencontrés lors de la mise en place de l'infrastructure de déploiement des laboratoires.

L'objectif est de centraliser les informations relatives aux applications et aux infrastructures, de contrôler leur cohérence et d'accompagner leur cycle de déploiement.

## 2. Objectifs

Le système vise à :

- Centraliser les informations de référence dans des registres Git.
- Valider les configurations et les données.
- Détecter les incohérences et les conflits de ressources.
- Suivre l'état des applications et des infrastructures.
- Synchroniser les modifications avec Git.
- Générer de la documentation à partir des registres.
- Permettre la réutilisation du moteur dans différents projets.

## 3. Architecture envisagée

Le projet repose sur trois dépôts indépendants.

| Dépôt | Responsabilité |
|---|---|
| `git-registry-tools` | Moteur générique de manipulation et de validation des registres. |
| `lab-deploy-registry` | Données, configuration et registres propres au laboratoire. |
| `git-registry-docs` | Documentation générale, architecture et guides d'utilisation. |

### `git-registry-tools`

Le moteur générique doit assurer les opérations suivantes :

- Lecture et validation des registres.
- Détection des conflits.
- Comparaison des données.
- Mise à jour des registres.
- Synchronisation avec Git.
- Génération de documentation.

Il ne doit pas contenir de règles spécifiques à un environnement. Celles-ci sont fournies par le dépôt de registres.

### `lab-deploy-registry`

Ce dépôt constitue la source centrale des données du laboratoire.

Il doit notamment contenir :

- Les registres des applications.
- Les registres des machines virtuelles.
- Les schémas de validation.
- Les règles métier.
- Les informations relatives aux ressources utilisées, notamment les ports.

### `git-registry-docs`

Ce dépôt rassemble la documentation générale du système : architecture, principes de conception, fonctionnement et utilisation.

## 4. Fonctionnement envisagé

Git Registry doit intervenir à différentes étapes du cycle de vie d'une application.

1. **Pre-commit** : contrôle préventif de la configuration avant son envoi.
2. **CI** : validation de la configuration avec les registres centralisés.
3. **CD** : nouvelle vérification des ressources disponibles juste avant le déploiement.
4. **VM** : exécution du déploiement et vérification de son résultat.
5. **Synchronisation** : mise à jour des registres après confirmation du résultat réel du déploiement.

Le Pre-commit et la CI permettent de détecter les problèmes en amont, mais ne garantissent pas à eux seuls la disponibilité d'une ressource au moment du déploiement.

Le CD doit donc effectuer une nouvelle validation, avec un mécanisme de coordination permettant d'éviter les conflits entre déploiements concurrents.

Les VM autorisées sont chargées de publier les modifications correspondant à leur périmètre.

## 5. Principes de conception

Le projet repose sur plusieurs principes :

- **Séparation des responsabilités** : moteur, données et documentation sont indépendants.
- **Généricité** : le moteur ne dépend pas d'un projet particulier.
- **Configuration externe** : les règles métier sont définies dans le dépôt de registres.
- **Centralisation** : les informations partagées sont conservées dans un dépôt Git.
- **Traçabilité** : les modifications sont historisées avec Git.
- **Sécurité** : les droits de lecture et d'écriture sont limités selon les responsabilités.
- **Cohérence** : les registres doivent refléter l'état réel des ressources.
- **Synchronisation maîtrisée** : aucune publication inutile en l'absence de modification des données.

## 6. Points à approfondir

Plusieurs aspects restent à définir :

- Structure et format des registres.
- Schémas de validation et règles métier.
- Contrat entre le moteur et le dépôt de données.
- Gestion des accès et des identités techniques.
- Gestion des déploiements concurrents et des verrouillages.
- Gestion des échecs et des mises à jour partielles.
- Synchronisation Git et résolution des conflits.
- Génération de documentation.

## 7. État du projet

<escape>**Statut : conception théorique — projet non implémenté.**</escape>

L'architecture générale et les principaux flux de fonctionnement ont été identifiés. Les choix techniques détaillés, les contrats entre dépôts et les mécanismes de synchronisation restent à préciser.

Le laboratoire constitue le premier environnement envisagé pour expérimenter et valider ce système.