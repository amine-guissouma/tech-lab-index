# VM Deploy

## 1. Présentation

La VM Deploy héberge les applications déployées par le laboratoire.

Elle constitue l'environnement de destination des livrables produits par la VM Runner.

## 2. Caractéristiques

| Élément | Configuration |
|---|---|
| Nom | `LAB-UBUNTU-DEPLOY-01` |
| Système | Ubuntu |
| Mémoire RAM | 4 Go |
| Processeurs | 2 |
| Disque | 50 Go |
| Hyperviseur | VMware |

## 3. Réseau

| Interface | Réseau | Configuration |
|---|---|---|
| `ens33` | VMnet8 (NAT) | DHCP |
| `ens37` | VMnet2 (Host-only) | `192.168.200.20/24` |

## 4. Rôle

La VM Deploy assure :

- La réception des livrables transmis par la VM Runner.
- L'hébergement des applications.
- L'exécution des applications déployées.
- La gestion des services applicatifs.
- L'exposition des applications sur leurs ports respectifs.

## 5. Communication

| Source | Adresse IP | Protocole |
|---|---|---|
| VM Runner | `192.168.200.10` | SSH |

## 6. Position dans l'infrastructure

La VM Deploy constitue l'environnement de déploiement et d'exécution des applications (CD).