# Socle [Technologie]

## 1. Présentation

Le socle constitue la base technique commune du laboratoire [nom-du-laboratoire].

Il fournit une structure fonctionnelle permettant de développer de nouvelles expérimentations sans repartir de zéro.

## 2. Technologies

- [Technologie principale]
- [Framework]
- [Bibliothèques principales]
- [Outil de test]
- [Outil de qualité]

## 3. Fonctionnalités

- [Fonctionnalité commune 1]
- [Fonctionnalité commune 2]
- [Fonctionnalité commune 3]
- Tests automatisés
- Contrôles qualité
- Intégration continue (CI)
- Déploiement continu (CD)

## 4. Fonctionnalités principales

### [Fonctionnalité ou point d'entrée]

[Description concise de son rôle.]

[Exemple de configuration, d'API ou de structure si nécessaire.]

## 5. Qualité du code

Contrôles automatisés :

- **[Outil 1]** : [rôle].
- **[Outil 2]** : [rôle].
- **[Outil 3]** : [rôle].

**Pre-commit** : exécution des contrôles avant chaque commit.

**CI** : exécution des contrôles après un push ou une Pull Request.

Documentation : [dev-toolbox — Documentation qualité](LIEN_VERS_DOCUMENTATION)

## 6. CI/CD

Le laboratoire utilise une pipeline automatisée basée sur **GitHub Actions**.

- **CI** : exécution des contrôles automatisés sur un runner self-hosted.
- **CD** : transfert et déploiement de l'application sur un serveur dédié.

Documentation : [tech-lab-index — Infrastructure CI/CD](LIEN_VERS_TECH_LAB_INDEX)

## 7. Branches

- `socle` : base technique commune et neutre.
- `experience/*` : branches dédiées aux expérimentations.