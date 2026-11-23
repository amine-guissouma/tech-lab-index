# VM Runner

## 1. Présentation

La VM Runner héberge le **GitHub Actions Self-hosted Runner**.

Elle exécute les tâches d'intégration continue (CI) du laboratoire.

## 2. Caractéristiques

| Élément | Configuration |
|---|---|
| Nom | `LAB-UBUNTU-RUNNER-01` |
| Système | Ubuntu |
| Mémoire RAM | 4 Go |
| Processeurs | 2 |
| Disque | 30 Go |
| Hyperviseur | VMware |

## 3. Réseau

| Interface | Réseau | Configuration |
|---|---|---|
| `ens33` | VMnet8 (NAT) | DHCP |
| `ens37` | VMnet2 (Host-only) | `192.168.200.10/24` |

## 4. Rôle

La VM Runner assure :

- L'exécution des workflows GitHub Actions.
- Les contrôles qualité du code.
- L'exécution des tests automatisés.
- La préparation des livrables.
- Le transfert des livrables vers la VM Deploy par SSH.

## 5. Communication

| Destination | Adresse IP | Protocole |
|---|---|---|
| VM Deploy | `192.168.200.20` | SSH |

## 6. Position dans l'infrastructure

La VM Runner constitue l'environnement d'exécution de l'intégration continue (CI).