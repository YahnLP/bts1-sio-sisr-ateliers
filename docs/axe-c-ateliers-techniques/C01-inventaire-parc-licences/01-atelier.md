# C01 – Inventaire du parc et suivi des licences

## 1. Pourquoi inventorier ?

On ne protège, ne maintient et ne renouvelle bien que ce que l'on **connaît**. L'inventaire permet : le suivi des **garanties** et de l'**âge**, le respect des **licences**, la préparation du **budget**, la **sécurité** (systèmes obsolètes) et le traitement des **incidents** (savoir ce qui est installé).

## 2. Les champs d'un inventaire

| Champ | Exemple |
|---|---|
| **Identifiant** | PC-07 |
| **Type** | Fixe, portable, serveur, imprimante |
| **Année d'achat** | 2018 |
| **Système et version** | Windows 10 |
| **Logiciels et licences** | Suite bureautique : oui |
| **Utilisateur / service** | Administratif |
| **Garantie / fin de support** | Date |
| **État** | En service, à remplacer, en stock |

> [!NOTE]
> Un outil d'inventaire peut remplir ces champs automatiquement ; sinon, un **tableur** bien tenu suffit. Le but est une **information à jour**, pas un outil précis.

## 3. Exercice : l'inventaire de l'Atelier Roussel (fictif)

Nous sommes en **2026**. La suite bureautique est **achetée en 10 licences**.

| ID | Type | Achat | Système | Suite installée |
|---|---|---:|---|---|
| PC-01 | Fixe | 2019 | Windows 10 | oui |
| PC-02 | Fixe | 2019 | Windows 10 | oui |
| PC-03 | Portable | 2021 | Windows 11 | oui |
| PC-04 | Portable | 2021 | Windows 11 | oui |
| PC-05 | Portable | 2022 | Windows 11 | oui |
| PC-06 | Fixe | 2018 | Windows 10 | oui |
| PC-07 | Fixe | 2018 | Windows 10 | non |
| PC-08 | Portable | 2023 | Windows 11 | oui |
| PC-09 | Portable | 2023 | Windows 11 | oui |
| PC-10 | Fixe | 2020 | Windows 10 | oui |
| PC-11 | Portable | 2024 | Windows 11 | oui |
| PC-12 | Portable | 2024 | Windows 11 | oui |

**Questions**

1. Combien de postes ont la suite installée ? Quel est l'**écart** avec les licences achetées ?
2. Combien de machines ont **plus de cinq ans** ? Lesquelles ?
3. Combien fonctionnent sous Windows 10 ? Quel risque cela représente-t-il ?
4. Quel est l'**âge moyen** du parc ? Quelle part de **portables** ?
5. Propose un **plan de renouvellement sur trois ans** en priorisant, avec les critères retenus.

<details markdown="1">
<summary>Voir la réponse attendue</summary>

**1.** 11 postes ont la suite installée (tous sauf PC-07) ; 10 licences achetées ; **écart de 1 licence** : une installation est sans licence, à régulariser (acheter une licence ou désinstaller).

**2.** Plus de cinq ans (achat en 2020 ou avant) : **5 machines** : PC-01, PC-02, PC-06, PC-07, PC-10.

**3.** **5 machines** sous Windows 10, les mêmes cinq. Le support de Windows 10 par l'éditeur a pris fin en octobre 2025 (à vérifier sur le site de l'éditeur) : plus de correctifs de sécurité réguliers, donc exposition aux vulnérabilités ; migration ou remplacement à prévoir.

**4.** Âge moyen : (7 + 7 + 5 + 5 + 4 + 8 + 8 + 3 + 3 + 6 + 2 + 2) / 12 = 60 / 12 = **5,0 ans**. Portables : 7 sur 12, soit **58,3 %**.

**5.** Exemple : **année 1** : remplacer PC-06 et PC-07 (les plus anciennes, 2018) ; **année 2** : PC-01 et PC-02 (2019) ; **année 3** : PC-10 (2020). Critères : âge, système obsolète, criticité de l'usage, budget annuel. Autre option : migrer les machines compatibles vers un système supporté si le matériel le permet, pour étaler le coût.
</details>

## 4. Mise en forme pour le portfolio

Pour présenter cette réalisation (compétence « gérer le patrimoine informatique ») : le **besoin** (absence d'inventaire), la **méthode** (champs, source des données), l'**analyse** (indicateurs ci-dessus), les **décisions** (régularisation, renouvellement) et des **preuves** anonymisées (extrait du tableau, graphique).

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Écart de licences et âge corrects | 6 |  |
| Obsolescence et risque expliqués | 4 |  |
| Indicateurs (âge moyen, part de portables) | 4 |  |
| Plan de renouvellement argumenté | 4 |  |
| Lien avec le portfolio | 2 |  |
| **Total** | **20** |  |
