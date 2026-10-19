# A04 – Documenter une réalisation : preuves, schémas, confidentialité

## 1. Ce qu'est une bonne preuve

Une preuve répond à : **qu'est-ce qui a été fait, par qui, quand, avec quel résultat ?**

| Type | Exemple | Qualité attendue |
|---|---|---|
| **Capture d'écran** | Fenêtre de configuration, résultat d'une commande | Lisible, **annotée** (flèche, numéro), **datée** |
| **Journal des tests** | Tableau test / résultat attendu / résultat obtenu | Complet, honnête (les échecs aussi) |
| **Schéma** | Réseau, flux, architecture | Légende, noms cohérents |
| **Procédure** | Marche à suivre pour l'utilisateur ou l'équipe | Testée par une autre personne |
| **Rapport** | Compte rendu d'incident, de recette | Faits, causes, actions |
| **Ticket / courriel** | Demande et réponse | Anonymisé |

## 2. Captures annotées

1. **Cadrer** : montrer l'élément utile, pas tout l'écran ;
2. **Annoter** : numéroter les éléments (1, 2, 3) et les expliquer en dessous ;
3. **Dater** et nommer le fichier (voir plus bas) ;
4. **Masquer** ce qui est confidentiel (mot de passe, adresse réelle, nom d'une personne).

## 3. Un schéma lisible

| Règle | Pourquoi |
|---|---|
| Un titre et une **légende** | On comprend sans explication orale |
| Des **noms** identiques au texte | Pas de confusion |
| Les **flux** fléchés dans un sens | On suit le trajet |
| Peu de couleurs, **significatives** | Lisible en noir et blanc |
| **Pas** d'adresses réelles de l'entreprise | Confidentialité |

**Exercice.** Dessine le schéma d'une réalisation (par exemple : trois postes, un serveur, un routeur, une sauvegarde externe) avec légende et plan d'adressage **fictif**.

## 4. Nommer et ranger

```text
portfolio/
  R01-serveur-fichiers/
    fiche-R01.pdf
    preuves/
      R01-01-creation-groupes-2026-03-12.png
      R01-02-test-acces-refuse-2026-03-12.png
    schema-R01.png
    journal-tests-R01.md
```

Règles : un dossier par réalisation, un **préfixe** de réalisation, un **numéro d'ordre**, une **date** en ordre année-mois-jour, pas d'espaces ni d'accents.

## 5. Confidentialité

| À retirer ou masquer | Pourquoi |
|---|---|
| **Mots de passe**, clés, jetons | Sécurité |
| **Adresses IP** et noms de machines réels | Cartographie du réseau de l'entreprise |
| **Noms et courriels** de personnes | Données personnelles (RGPD) |
| **Données clients** | Confidentialité et secret des affaires |
| **Références contractuelles** | Confidentialité |

> [!WARNING]
> Demande **l'accord de ton tuteur** avant de présenter une réalisation d'entreprise. Remplace les valeurs sensibles par des valeurs **fictives cohérentes** (par exemple `192.168.10.0/24` pour un réseau d'exemple).

**Exercice.** Relis ta fiche de l'atelier A02 et sa preuve principale. Fais une liste de tout ce que tu masques et par quoi tu le remplaces.

## 6. Journal des tests

| N° | Test | Résultat attendu | Résultat obtenu | Conforme ? | Preuve |
|---|---|---|---|---|---|
| 1 | Connexion avec le compte du groupe « production » | Accès au dossier « Production » | Accès obtenu | Oui | R01-02 |
| 2 | Connexion avec le même compte au dossier « Direction » | Accès refusé | Accès refusé | Oui | R01-03 |

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Captures annotées et lisibles | 5 |  |
| Schéma avec légende | 4 |  |
| Nommage et classement | 3 |  |
| Journal des tests complet | 4 |  |
| Confidentialité respectée | 4 |  |
| **Total** | **20** |  |
