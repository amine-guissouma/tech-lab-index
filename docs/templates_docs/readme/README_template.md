# [nom-du-laboratoire]

Laboratoire [backend / frontend / autre] [technologie].

Ce dépôt fournit le socle [technologie] utilisé par les expérimentations du laboratoire.

Les expérimentations sont développées dans des branches `experience/*`.

---

## Socle

Le socle constitue le point de départ du laboratoire. Il fournit les éléments communs nécessaires aux expérimentations :

- `[Technologie principale]`
- `[Framework et bibliothèques]`
- Configuration centralisée
- Organisation du projet
- Fonctionnalités communes
- Tests automatisés
- Contrôles qualité
- Intégration continue (CI)
- Déploiement Déploiement automatique selon la branche

Documentation du socle

---

## Branches

- `socle` : base technique commune et neutre.
- `experience/*` : branches dédiées aux expérimentations.

---

## Expérimentations

Chaque expérimentation explore une fonctionnalité ou une approche technique à partir d'une base existante.

Une expérience peut partir :

- Directement du socle.
- D'une autre expérience pour approfondir ou étendre une fonctionnalité.

| Branche            | Base de départ              | Sujet                    | Documentation |
| ------------------ |-----------------------------|--------------------------| ------------- |
| `experience/[nom]` | `socle ou experience/[nom]` | [Sujet de l'expérience]  | Voir          |

---

## Annexes

| Élément              | Description                                                          | Documentation                                                                                              |
|----------------------|----------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Qualité du code      | [Outils de formatage, analyse et tests]                              | dev-toolbox — Qualité du code                                                                              |
| Infrastructure CI/CD | GitHub Actions, Runner et Deploy                                     | [tech-lab-index — Infrastructure](https://github.com/amine-guissouma/tech-lab-index/docs/infrastructure)   |
| Outils communs       | Vérification et gestion des configurations communes aux laboratoires | [Lab Toolkit](https://github.com/amine-guissouma/lab-toolkit)                                              |

---

## Index des laboratoires

Les laboratoires et leurs expérimentations sont référencés dans [tech-lab-index](https://github.com/amine-guissouma/tech-lab-index).