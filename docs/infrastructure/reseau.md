# Architecture réseau CI/CD

## 1. Présentation

L'infrastructure utilise deux réseaux VMware :

- **VMnet8** : accès Internet via NAT.
- **VMnet2** : communication privée entre les machines Runner et Deploy.

Nom de l'infrastructure : `LAB-RUNNER-DEPLOY-NET`

## 2. Réseaux

| Réseau | Type | Sous-réseau | Rôle |
|---|---|---|---|
| VMnet8 | NAT | DHCP | Accès Internet |
| VMnet2 | Host-only | `192.168.200.0/24` | Communication privée CI/CD |

## 3. Interfaces réseau

Chaque machine virtuelle dispose de deux interfaces réseau.

| Interface | Réseau | Configuration |
|---|---|---|
| `ens33` | VMnet8 | DHCP |
| `ens37` | VMnet2 | Adresse IP fixe |

## 4. Adressage IP

| Machine | Interface privée | Adresse IP |
|---|---|---|
| `LAB-UBUNTU-RUNNER-01` | `ens37` | `192.168.200.10/24` |
| `LAB-UBUNTU-DEPLOY-01` | `ens37` | `192.168.200.20/24` |

## 5. Architecture réseau

```text
                  Internet
                     |
                  VMnet8
                    NAT
                     |
          +----------+----------+
          |                     |
      VM Runner             VM Deploy
          |                     |
        ens33                 ens33
          |                     |
        ens37                 ens37
          |                     |
          +------ VMnet2 -------+
             Host-only
          192.168.200.0/24
```

## 6. Communication

Le réseau privé VMnet2 assure les échanges entre les deux machines virtuelles, notamment le transfert des livrables par SSH.

Le réseau VMnet8 assure leur accès à Internet.