# C03 – Superviser un service : indicateurs, seuils, alertes

## 1. Pourquoi superviser ?

Superviser, c'est **détecter avant l'utilisateur** : disque plein, service arrêté, mémoire saturée. Une alerte utile est **rare**, **claire** et **actionnable**.

## 2. Indicateurs et seuils

| Indicateur | Pourquoi | Avertissement | Critique |
|---|---|---|---|
| **Espace disque** | Un disque plein arrête les services et les sauvegardes | 80 % | 90 % |
| **Mémoire utilisée** | Saturation, ralentissements | 80 % | 90 % |
| **Charge processeur** (durée) | Surcharge durable | 80 % pendant 10 min | 95 % pendant 10 min |
| **Service actif** | Disponibilité du service | — | Arrêté |
| **Disponibilité** | Respect du SLA | < objectif | — |
| **Sauvegarde** | Données protégées | Retard de 1 jour | Retard de 3 jours |

> [!NOTE]
> Les seuils sont des **valeurs de départ** à ajuster selon le contexte. Un seuil trop bas crée du bruit, un seuil trop haut prévient trop tard.

## 3. Manipulation sur une machine virtuelle de laboratoire

À faire **uniquement sur la machine de laboratoire**.

| Relevé | Commande |
|---|---|
| Charge et durée de fonctionnement | `uptime` |
| Mémoire | `free -h` |
| Disque | `df -h` |
| Ports en écoute | `ss -tlnp` |
| État d'un service | `systemctl status <service>` |
| Derniers journaux d'un service | `journalctl -u <service> -n 20` |

Note les résultats dans un tableau : date, indicateur, valeur, seuil, conclusion.

## 4. Exercice : lire des relevés (fictifs)

| Relevé | Valeurs |
|---|---|
| **Disque** | 500 Go au total, 410 Go utilisés |
| **Mémoire** | 8 Go au total, 1,2 Go disponibles |
| **Service de partage** | Actif |
| **Sauvegarde** | Dernière réussie il y a 2 jours |

**Questions**

1. Calcule le taux d'utilisation du disque et de la mémoire.
2. Compare aux seuils et classe : normal, avertissement ou critique.
3. Quelle action proposes-tu pour chaque cas ?
4. La sauvegarde date de 2 jours : classement ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

**1.** Disque : 410 / 500 = **82 %**. Mémoire : (8 − 1,2) / 8 = 6,8 / 8 = **85 %**.

**2.** Disque : **avertissement** (≥ 80 %, < 90 %). Mémoire : **avertissement**. Service : normal. Sauvegarde : retard de 2 jours, **avertissement** (retard d'au moins un jour, moins de 3).

**3.** Disque : identifier les plus gros dossiers, archiver ou supprimer ce qui est inutile, ou prévoir plus d'espace avant 90 %. Mémoire : repérer le processus consommateur, redémarrer le service concerné si nécessaire, ou prévoir plus de mémoire. Sauvegarde : examiner le journal du dernier échec et relancer.

**4.** Avertissement : au-delà d'un jour de retard on traite, avant le seuil critique de 3 jours.
</details>

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Indicateurs et seuils pertinents | 5 |  |
| Relevés effectués et notés | 5 |  |
| Calculs et classement corrects | 5 |  |
| Actions adaptées | 5 |  |
| **Total** | **20** |  |
