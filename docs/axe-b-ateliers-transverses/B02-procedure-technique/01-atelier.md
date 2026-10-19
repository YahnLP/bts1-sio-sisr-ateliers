# B02 – Rédiger une procédure technique claire

## 1. Structure

| Rubrique | Contenu |
|---|---|
| **Titre et version** | Un titre d'action (« Créer un compte utilisateur »), date, auteur |
| **Objectif** | À quoi sert la procédure, quand l'utiliser |
| **Public et droits requis** | Qui peut l'exécuter, avec quels droits |
| **Prérequis** | Ce qu'il faut avoir avant de commencer |
| **Étapes numérotées** | Une action par étape, dans l'ordre |
| **Vérification** | Comment savoir que c'est réussi |
| **Retour arrière** | Comment annuler si cela se passe mal |
| **Contacts** | Qui prévenir en cas de blocage |

## 2. Écrire une étape

| Règle | Mauvais exemple | Bon exemple |
|---|---|---|
| **Un verbe d'action** | « Le compte est créé » | « Crée le compte » |
| **Une action par étape** | « Ouvre la console, crée le compte et envoie le mot de passe » | Trois étapes |
| **Valeurs exactes** | « Choisis un bon groupe » | « Ajoute le compte au groupe `Production` » |
| **Résultat attendu** | (absent) | « Le compte apparaît dans la liste » |
| **Captures** | Nombreuses et illisibles | Une capture annotée aux étapes délicates |

## 3. Exercice 1 : corriger une procédure faible

> **Créer un compte.** Aller dans l'outil, ajouter l'utilisateur, lui mettre les droits nécessaires et lui dire son mot de passe. Vérifier que ça marche.

**Questions** : relève six défauts et réécris la procédure.

<details markdown="1">
<summary>Voir des éléments de réponse</summary>

**Défauts** : pas d'objectif ; pas de prérequis (qui, quels droits) ; étapes floues (« l'outil », « droits nécessaires ») ; plusieurs actions par ligne ; **mot de passe transmis oralement** (risque de sécurité) ; vérification non décrite ; aucun retour arrière.

**Réécriture (extrait)** : *Objectif* : créer le compte d'un nouvel arrivant. *Prérequis* : demande validée par le responsable ; droits d'administrateur des comptes. *Étapes* : 1. Ouvre la console d'administration. 2. Clique sur « Nouvel utilisateur ». 3. Saisis le nom et l'identifiant au format `prenom.nom`. 4. Ajoute le compte au groupe indiqué dans la demande. 5. Génère un mot de passe temporaire et impose son changement à la première connexion. 6. Transmets-le par un canal séparé de l'identifiant. *Vérification* : connecte-toi avec le compte de test et contrôle l'accès attendu. *Retour arrière* : désactive le compte et note-le dans le ticket.
</details>

## 4. Exercice 2 : ma procédure

Choisis une tâche que tu réalises ou sais réaliser (installer un poste, créer un partage, redémarrer un service, sauvegarder, déclarer un incident). Rédige la procédure d'**une page** avec **toutes** les rubriques.

## 5. Test croisé

Un camarade **exécute** ta procédure sans te poser de question et note chaque blocage.

| Étape | Compris ? | Blocage ou ambiguïté | Correction |
|---|---|---|---|
|  |  |  |  |

> [!WARNING]
> Ne publie jamais une procédure qui contient un **mot de passe réel**, une **adresse IP réelle** ou un **nom de personne** : remplace-les par des valeurs d'exemple.

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Structure complète | 5 |  |
| Étapes claires (verbe, valeurs, résultat) | 5 |  |
| Vérification et retour arrière | 4 |  |
| Test croisé réalisé et corrigé | 4 |  |
| Aucune donnée confidentielle | 2 |  |
| **Total** | **20** |  |
