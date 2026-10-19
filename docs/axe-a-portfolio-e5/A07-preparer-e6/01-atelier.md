# A07 – Préparer l'épreuve E6 (pratique et orale) : méthode

## 1. Le déroulement (arrêté du 8 juillet 2024)

L'épreuve **E6 – Administration des systèmes et des réseaux** (option SISR) est **pratique et orale**, de **coefficient 4**. Elle prend appui sur **deux réalisations professionnelles** du dossier numérique.

| Temps | Contenu |
|---|---|
| **Préparation 1** : 30 min | Étude d'une **expression de besoins** rédigée par la commission à partir d'une de tes situations |
| **Entretien 1** : 20 min maximum | Tu présentes ton **analyse**, tes **spécifications techniques**, le **choix des outils** et ta **démarche** |
| **Préparation 2** : 1 h | Tu **réalises la solution** en autonomie sur l'environnement du centre d'interrogation |
| **Entretien 2** : 20 min maximum | **Recette** de la solution, puis entretien d'explicitation : conformité, opérationnalité, pertinence des outils et de la démarche |

> [!NOTE]
> Tu es **responsable** de l'usage de l'environnement : respecter les consignes de sécurité et de sauvegarde, et te munir des outils et ressources nécessaires.

## 2. Analyser une expression de besoins

Méthode en cinq temps :

1. **Souligner** les exigences (verbes « doit », « permet », valeurs chiffrées) ;
2. **Lister** ce qui est donné (existant) et ce qui manque ;
3. **Traduire** en spécifications techniques ;
4. **Choisir** les outils et justifier ;
5. **Prévoir** les tests de recette.

### Exercice (cas fictif)

> *Atelier Roussel (12 salariés) souhaite un service de **partage de fichiers**. Trois groupes d'utilisateurs : production, administratif, direction. Seule la direction peut lire le dossier « Direction ». L'accès se fait depuis le réseau interne uniquement. Une sauvegarde quotidienne est exigée. Une procédure d'une page doit être remise à l'administrateur.*

**Questions**

1. Dresse la liste des **exigences** (au moins six).
2. Écris les **spécifications techniques** correspondantes.
3. Propose un **plan de réalisation** en 60 minutes.
4. Liste cinq **tests de recette**.

<details markdown="1">
<summary>Voir des éléments de réponse</summary>

**1.** Partage de fichiers ; trois groupes ; dossier « Direction » réservé à la direction ; accès depuis le réseau interne uniquement ; sauvegarde quotidienne ; procédure d'une page.

**2.** Un serveur de fichiers ; trois groupes d'utilisateurs ; permissions par dossier ; pare-feu limité au réseau interne ; tâche planifiée de sauvegarde ; document de procédure.

**3.** 5 min vérification de l'environnement ; 10 min création des utilisateurs et groupes ; 15 min création des partages et permissions ; 10 min règle de pare-feu ; 10 min sauvegarde ; 5 min tests ; 5 min procédure.

**4.** Un utilisateur « production » lit et écrit dans « Production » ; le même utilisateur est refusé dans « Direction » ; un membre de la direction lit « Direction » ; accès refusé depuis un autre réseau ; une sauvegarde de test est restaurée.
</details>

## 3. Organiser l'heure de réalisation

| Principe | Application |
|---|---|
| **Lire d'abord** | Relire l'expression de besoins avant de toucher à la machine |
| **Faire simple, puis améliorer** | Une version qui marche vaut mieux qu'une version parfaite inachevée |
| **Tester au fur et à mesure** | Un test par étape |
| **Documenter en passant** | Noter les commandes et captures utiles |
| **Garder 10 minutes** | Pour les tests de recette et la préparation de la présentation |

## 4. Recette et explicitation

Prépare une feuille de recette **avant** d'être en situation.

| N° | Exigence | Test | Résultat attendu | Résultat |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Exigences repérées et traduites | 6 |  |
| Spécifications et choix d'outils justifiés | 5 |  |
| Plan de réalisation réaliste | 5 |  |
| Tests de recette pertinents | 4 |  |
| **Total** | **20** |  |
