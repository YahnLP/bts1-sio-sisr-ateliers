# B03 – Conduire un mini-projet : cadrage, planning, suivi

## 1. Les étapes

| Étape | Résultat |
|---|---|
| **Cadrage** | Objectif, périmètre, contraintes, livrables, parties prenantes |
| **Planification** | Tâches, durées, dépendances, ressources |
| **Réalisation** | Suivi de l'avancement |
| **Recette** | Validation par le demandeur |
| **Clôture** | Bilan, documentation, retour d'expérience |

## 2. La fiche de cadrage

| Rubrique | Contenu |
|---|---|
| **Contexte et besoin** | Pourquoi ce projet ? |
| **Objectifs mesurables** | Ce qui doit être vrai à la fin |
| **Périmètre** | Ce qui est inclus / exclu |
| **Contraintes** | Délai, budget, techniques, réglementaires |
| **Livrables** | Ce qui sera remis |
| **Parties prenantes** | Demandeur, utilisateurs, équipe, décideurs |
| **Critères de réussite** | Comment valider |

## 3. Exercice : migration de la messagerie (cas fictif)

L'*Atelier Roussel* (15 utilisateurs) migre sa messagerie vers un nouveau service. Tâches, durées en jours ouvrés et dépendances :

| Code | Tâche | Durée | Après |
|---|---|---:|---|
| T1 | Inventorier les boîtes et les usages | 2 | — |
| T2 | Choisir et valider la solution | 3 | T1 |
| T3 | Préparer les comptes et la messagerie cible | 2 | T2 |
| T4 | Migrer un groupe pilote | 2 | T3 |
| T5 | Former les utilisateurs | 1 | T2 |
| T6 | Basculer l'ensemble des utilisateurs | 1 | T4, T5 |

**Questions**

1. Dessine le planning (diagramme en barres ou réseau).
2. Quelle est la **durée totale** du projet ?
3. Quel est le **chemin critique** ? Quelle tâche a de la **marge**, et de combien ?
4. Un retard de deux jours sur T3 : quelle conséquence ? Et un retard de deux jours sur T5 ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

**2.** T1 démarre à 0 et finit à 2 ; T2 de 2 à 5 ; T3 de 5 à 7 ; T4 de 7 à 9 ; T5 de 5 à 6 ; T6 démarre après T4 (fin à 9) et T5 (fin à 6) donc de 9 à 10. **Durée totale : 10 jours ouvrés.**

**3.** Chemin critique : **T1 → T2 → T3 → T4 → T6** (2 + 3 + 2 + 2 + 1 = 10). T5 a de la marge : elle peut finir au plus tard à 9, elle finit au plus tôt à 6, soit **3 jours de marge**.

**4.** Retard de 2 jours sur T3 : T3 sur le chemin critique, donc **le projet finit à 12 jours**. Retard de 2 jours sur T5 : T5 finit à 8, avant la fin de T4 (9) ; **aucune conséquence** sur la date finale.
</details>

## 4. Risques

| Risque | Probabilité (1-3) | Gravité (1-3) | Criticité (P×G) | Parade |
|---|:---:|:---:|:---:|---|
| Perte de courriels pendant la migration | 1 | 3 | 3 | Sauvegarde préalable, groupe pilote |
| Utilisateurs non formés à la bascule | 2 | 2 | 4 | Formation avant la bascule |
| Indisponibilité du service cible | 1 | 3 | 3 | Date de bascule hors période critique |

On traite d'abord les risques de **criticité la plus élevée**.

## 5. Compte rendu de suivi

| Rubrique | Contenu |
|---|---|
| **Date, participants** | Qui, quand |
| **Avancement** | Tâches terminées, en cours, en retard |
| **Décisions** | Ce qui a été décidé |
| **Actions** | Qui fait quoi, avant quand |
| **Risques** | Nouveaux risques, évolutions |
| **Prochaine réunion** | Date |

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Fiche de cadrage complète | 4 |  |
| Durée et chemin critique corrects | 6 |  |
| Analyse d'un retard | 3 |  |
| Tableau de risques pertinent | 4 |  |
| Compte rendu exploitable | 3 |  |
| **Total** | **20** |  |
