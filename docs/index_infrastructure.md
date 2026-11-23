# Infrastructure CI/CD

## 1. Présentation

L'infrastructure CI/CD du laboratoire permet d'automatiser la validation, le transfert et le déploiement des applications.

Elle repose sur GitHub Actions et deux machines virtuelles Ubuntu :

- **Runner** : exécution des tâches d'intégration continue (CI).
- **Deploy** : réception des livrables et hébergement des applications.

Le runner est centralisé au niveau du dépôt **`tech-lab-index`**, qui référence l'infrastructure commune aux laboratoires.

Les secrets et variables GitHub sont gérés individuellement par chaque dépôt de laboratoire.

## 2. Architecture

Infrastructure : `LAB-RUNNER-DEPLOY-NET`

```text
Développement local (Windows)
          |
          | git push
          v
        GitHub
          |
          | GitHub Actions
          | 
          v
      VM Runner
          |
          | CI : contrôles et tests
          |
          | Transfert SSH
          v
      VM Deploy
          |
          | CD : déploiement
          v
      Application
          |
          v
       Navigateur
```

## 3. Composants

| Composant        | Rôle                            | Documentation                            |
|------------------|---------------------------------|------------------------------------------|
| Réseau           | Communication entre les VM      | [Réseau](infrastructure/reseau.md)       |
| VM Runner        | Exécution de la CI              | [VM Runner](infrastructure/vm-runner.md) |
| VM Deploy        | Hébergement et déploiement      | [VM Deploy](infrastructure/vm-deploy.md) |
| `tech-lab-index` | Référencement central du Runner | Documentation infrastructure             |

## 4. Fonctionnement CI/CD

- **CI** : GitHub Actions déclenche les contrôles et les tests sur la VM Runner.
- **CD** : les livrables sont transférés par SSH vers la VM Deploy, où l'application est déployée.

## 5. Environnement

| Élément              | Technologie                       |
| -------------------- | --------------------------------- |
| Hyperviseur          | VMware                            |
| Systèmes             | Ubuntu                            |
| Automatisation       | GitHub Actions                    |
| Runner               | GitHub Actions Self-hosted Runner |
| Communication privée | SSH                               |
| Réseau dédié         | `CI-CD`           |