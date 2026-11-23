

# Branch Convention

Ce document définit les règles de création, de nommage et d'organisation des branches.

## 1. Branche `socle`

La branche `socle` représente le point de départ commun du laboratoire.

Elle contient uniquement les éléments nécessaires au fonctionnement général du lab.

Elle doit rester :

- neutre ;
- minimale ;
- stable ;
- reproductible ;
- indépendante des expérimentations.

Les fonctionnalités propres à une expérience ne doivent pas être intégrées au socle.

## 2. Branches expérimentales

Chaque expérience utilise une branche dédiée :

```text
experience/<sujet>
```

Une expérience peut partir :

- directement de `socle` ;


Une expérience dérivée doit conserver la trace de sa branche parente.

Exemple :

```text
socle
  │
  ├── experience/auth-token
  │       │
  │       └── experience/auth-jwt
  │
  └── experience/auth-session
```

Dans cet exemple, `experience/auth-jwt` part de `experience/auth-token`.

## 3. Règles

1. Une branche `experience/*` correspond à une expérimentation identifiable.
2. Une expérience doit indiquer sa branche de départ.
3. Une expérience dérivée doit conserver la traçabilité de ses dépendances.
4. Les expériences ne sont pas fusionnées dans `socle` par défaut.
5. Les expériences comparées doivent utiliser une base commune lorsque la comparaison le nécessite.
6. Une modification commune et nécessaire au fonctionnement du laboratoire doit être réalisée dans `socle`.

## 4. Nommage

Format :

```text
experience/<sujet>
```

Pour une variante :

```text
experience/<sujet>-<technologie>
```

Exemples :

```text
experience/auth-token
experience/auth-token-apikit

experience/auth-session
experience/auth-session-apikit

experience/error-handling
experience/error-handling-graphql
```

## 5. Règles de nommage

- Utiliser uniquement des minuscules.
- Utiliser `-` comme séparateur.
- Ne pas utiliser d'espaces.
- Utiliser un nom court et descriptif.
- Identifier le sujet étudié.
- Ajouter la technologie ou l'approche lorsque nécessaire.

## 6. Traçabilité

Chaque documentation d'expérience doit préciser :

- le nom de la branche ;
- la branche parente ;
- l'objectif de l'expérience ;
- les modifications apportées par rapport à sa base.

