

# Conventions du laboratoire

Ce dossier regroupe les conventions communes aux laboratoires frontend et backend.

## Documents

| Document                                                               | Rôle                                            |
|------------------------------------------------------------------------|-------------------------------------------------|
| [repository-convention.md](conventions/repository-convention.md)       | Nommage et organisation des dépôts Git          |
| [branch-convention.md](conventions/branch-convention.md)               | Organisation des branches et des expériences    |
| [lab-base-convention.md](conventions/lab-base-convention.md)           | Règles communes aux socles frontend et backend  |
| [configuration-convention.md](conventions/configuration-convention.md) | Configuration, API et uniformisation            |
| [versioning-convention.md](conventions/versioning-convention.md)       | Cycle de développement et de validation V0 à V7 |

## Principes généraux

- Chaque dépôt correspond à une technologie ou un environnement technique.
- Chaque dépôt possède une branche `socle`.
- Les expérimentations sont développées dans des branches `experience/*`.
- Une expérience peut partir du socle ou d'une autre expérience.
- Les socles frontend et backend respectent un contrat commun.
- Les expériences doivent rester reproductibles et traçables.
- Le versioning permet d'identifier les étapes de maturation d'une expérience et de ses modules.

