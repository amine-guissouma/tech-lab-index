

# Configuration Convention

Ce document définit les règles communes de configuration et d'uniformisation des laboratoires frontend et backend.

## 1. Configuration centralisée

La configuration commune du socle est regroupée dans :

```text
config/
└── config-socle.*
```

Le fichier `config-socle` constitue la référence pour les paramètres communs du laboratoire.

Il regroupe notamment :

- les adresses frontend et backend ;
- les ports ;
- les paramètres de communication ;
- la configuration de l'API ;
- les paramètres du mode développement.

Les valeurs sensibles ou propres à un environnement peuvent être fournies séparément par des variables d'environnement.

**Règle :** éviter de disperser les paramètres communs directement dans le code.

## 2. Adressage standard

Valeurs par défaut :

```text
Frontend : localhost:3000
Backend  : localhost:8000
```

Ces valeurs sont centralisées dans la configuration du socle.

## 3. API du socle

Tous les laboratoires backend exposent une route d'identification commune :

```text
GET /api/lab
```

Réponse :

```json
{
  "name": "lab-back-django"
}
```

Cette route permet au frontend de récupérer l'identité du backend.

Il n'existe pas de route `/api/health` dans le contrat du socle.

## 4. Préfixe API

Les routes API utilisent le préfixe :

```text
/api/
```

Exemples :

```text
/api/lab
/api/session
/api/token
```

Les routes expérimentales sont ajoutées dans les branches correspondantes.

## 5. Format des réponses

Les endpoints API retournent du JSON.

Exemple :

```json
{
  "name": "lab-back-django"
}
```

Le format des réponses doit rester cohérent entre les différentes technologies.

## 6. Format des erreurs

Les API utilisent un format d'erreur commun.

Exemple :

```json
{
  "error": {
    "code": "NOT_FOUND",
    "message": "Resource not found"
  }
}
```

L'implémentation interne reste libre selon le framework utilisé.

## 7. Premier écran frontend

Le premier écran standard affiche :

```text
LAB FRONT : lab-front-react
LAB BACK  : lab-back-django
```

Le nom du backend est récupéré avec :

```text
GET /api/lab
```

Cet écran constitue le test minimal de communication entre les deux laboratoires.

## 8. Tests du socle

Chaque backend vérifie au minimum :

- le démarrage ;
- la route `/api/lab` ;
- le format de la réponse ;
- le comportement des erreurs principales.

Chaque frontend vérifie au minimum :

- le démarrage ;
- l'affichage du premier écran ;
- l'appel à `/api/lab` ;
- l'affichage du nom du backend.

## 9. Documentation

Chaque dépôt doit documenter les rubriques suivantes :

```text
# Nom du lab

## Objectif

## Technologie

## Configuration

## Démarrage

## Communication Front / Back

## API du socle

## Tests

## Structure

## Expérimentations
```

Les commandes restent propres à chaque technologie.

## 10. CI/CD

La CI/CD fait partie du socle des laboratoires.

Elle permet notamment :

- d'exécuter les contrôles qualité ;
- de lancer les tests ;
- de vérifier les modifications ;
- d'automatiser le déploiement lorsque celui-ci est configuré.

Les détails de l'infrastructure CI/CD sont documentés séparément afin d'éviter leur duplication dans les conventions.

## 11. Principe directeur

> Le socle uniformise les éléments nécessaires à la comparaison des expériences, sans uniformiser les éléments qui constituent leur objet d'étude.

