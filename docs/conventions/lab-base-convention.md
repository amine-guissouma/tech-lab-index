

# Lab Base Convention

Ce document définit les règles communes aux socles des laboratoires frontend et backend.

## 1. Organisation des laboratoires

Les laboratoires frontend et backend sont développés dans des dépôts distincts.

```text
Expérience
    │
    ├── lab-front-*
    │
    └── lab-back-*
```

Une même expérience peut être reproduite avec différentes technologies.

Exemple :

```text
Expérience Session
│
├── lab-front-react
├── lab-front-angular
├── lab-back-django
└── lab-back-fastapi
```

## 2. Rôle du socle

Le socle fournit l'environnement minimal nécessaire au développement des expériences.

Il doit rester :

- neutre ;
- minimal ;
- stable ;
- reproductible ;
- indépendant des fonctionnalités expérimentales.

Les fonctionnalités spécifiques, comme JWT, les sessions personnalisées ou les bibliothèques expérimentales, appartiennent aux branches `experience/*`.

## 3. Couple Frontend / Backend

Les socles frontend et backend doivent pouvoir communiquer avant toute expérimentation.

```text
Frontend
    │
    │ HTTP
    ▼
Backend
```

Le contrat minimal repose sur une API d'identification commune.

```text
GET /api/lab
```

Réponse :

```json
{
  "name": "lab-back-django"
}
```

Cette route permet au frontend d'identifier le backend utilisé.

## 4. Adressage standard

Les laboratoires utilisent par défaut les adresses suivantes :

```text
Frontend : http://localhost:3000
Backend  : http://localhost:8000
```

Les ports peuvent être adaptés si une contrainte technique l'impose, mais les changements doivent être documentés dans la configuration du socle.

## 5. Premier écran frontend

Tous les laboratoires frontend disposent d'un premier écran standard.

Il affiche :

```text
LAB FRONT : lab-front-react
LAB BACK  : lab-back-django
```

Le frontend connaît sa propre identité et récupère celle du backend avec :

```text
GET /api/lab
```

Cet écran sert à vérifier la communication entre les deux laboratoires.

Il ne doit contenir aucune fonctionnalité propre à une expérience.

## 6. Contrat de communication

La compatibilité frontend/backend repose sur :

- une adresse connue ;
- des routes définies ;
- des méthodes HTTP ;
- des formats de données ;
- des comportements attendus.

Les API du socle retournent du JSON.

## 7. Validation du socle

### Backend

- Le serveur démarre.
- Le serveur écoute sur le port défini.
- `GET /api/lab` fonctionne.
- La réponse respecte le contrat attendu.

### Frontend

- L'application démarre.
- Le premier écran s'affiche.
- Le frontend appelle `/api/lab`.
- Le nom du backend est affiché.

### Couple Frontend / Backend

La communication doit être validée avant de commencer les expérimentations.

## 8. Stabilité

Une expérience ne doit pas modifier le socle pour résoudre un problème qui lui est propre.

Les modifications communes et nécessaires doivent être intégrées dans `socle`.

Les modifications expérimentales restent dans leur branche dédiée.

## 9. Principe directeur

> Le socle fournit l'environnement minimal, stable et commun. L'expérience apporte la question technique à étudier.

