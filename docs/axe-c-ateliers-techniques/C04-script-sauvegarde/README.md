# C04 – Automatiser une sauvegarde avec un script Bash

| Élément | Détail |
|---|---|
| **Niveau** | BTS SIO option SISR – atelier de professionnalisation |
| **Axe** | Axe C – Ateliers techniques |
| **Durée indicative** | 2 h |
| **Compétence(s) visée(s)** | Mettre à disposition un service ; gérer le patrimoine informatique |
| **Prérequis** | Bases de la ligne de commande Linux |
| **Livrable** | Un **script**, une **tâche planifiée** et une **preuve de restauration**. |

## Objectifs

À la fin de l'atelier, l'étudiant est capable de :

1. Écrire un **script** avec contrôles d'erreur
2. Produire une **sauvegarde datée** et gérer la **rétention**
3. **Planifier** l'exécution
4. **Tester la restauration**

## Contenu

| Document | Rôle |
|---|---|
| [Guide de l'atelier](01-atelier.md) | Méthode, exercices, modèles et grille d'évaluation |

## Déroulé conseillé

| Durée | Activité |
|---|---|
| 15 min | Principes d'une bonne sauvegarde |
| 40 min | Lire et tester le script |
| 20 min | Planification |
| 30 min | Test de restauration |
| 15 min | Documenter |

## Je sais faire

- [ ] Écrire un script avec contrôle d'erreur
- [ ] Gérer la rétention
- [ ] Planifier avec cron
- [ ] Tester une restauration

<details markdown="1">
<summary>Notes pour l'enseignant</summary>

- Script testé : 9 exécutions conservent 7 archives ; source inexistante renvoie le code 2 ; sans argument, code 1.
- Chemins d'exemple à adapter au laboratoire.
- Ne pas lancer de suppression ailleurs que dans le dossier de test.
- Atelier écrit lors de la refonte ; à relire avant diffusion.

</details>
