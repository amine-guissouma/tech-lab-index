

# Repository Convention

Ce document définit les règles de nommage et d'organisation des dépôts Git du laboratoire.

## 1. Convention de nommage

Chaque dépôt représente un laboratoire dédié à un domaine et à une technologie.

Format :

```text
lab-<domaine>-<technologie>
```

Exemples :

```text
lab-front-react
lab-front-angular

lab-back-django
lab-back-fastapi
lab-back-flask
```

## 2. Règles de nommage

- Utiliser uniquement des minuscules.
- Utiliser `-` comme séparateur.
- Commencer par `lab-`.
- Identifier le domaine : `front`, `back`, etc.
- Terminer par la technologie ou le framework principal.
- Ne pas inclure le nom d'une expérience dans le dépôt.

## 3. Organisation

Chaque dépôt contient une branche `socle` et des branches dédiées aux expérimentations.

Exemple :

```text
lab-back-django
│
├── socle
│
├── experience/auth-token
├── experience/auth-session
└── experience/error-handling
```

## 4. Responsabilités

| Élément | Responsabilité |
|---|---|
| Repository | Identifie le contexte technique |
| `socle` | Fournit la base commune |
| `experience/*` | Identifie une expérimentation |

## 5. Évolution

De nouveaux dépôts peuvent être ajoutés sans modifier la convention.

```text
lab-front-react
lab-front-angular
lab-back-django
lab-back-fastapi
lab-back-flask
```

