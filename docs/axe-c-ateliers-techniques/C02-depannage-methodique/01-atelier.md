# C02 – Dépannage méthodique et traitement d'un ticket

## 1. La démarche

| Étape | Question |
|---|---|
| **1. Écouter** | Quel est le problème exact, pour qui, depuis quand ? |
| **2. Reproduire** | Est-ce que je le vois moi-même ? |
| **3. Délimiter** | Un poste ou plusieurs ? Un service ou tous ? Qu'est-ce qui a changé ? |
| **4. Formuler des hypothèses** | Quelles causes sont possibles, de la plus simple à la plus complexe ? |
| **5. Tester une hypothèse à la fois** | Un test, un résultat |
| **6. Corriger et vérifier** | Le problème a-t-il disparu ? L'utilisateur confirme-t-il ? |
| **7. Documenter** | Ticket, cause, solution, procédure si le cas se répète |

> [!WARNING]
> Avant toute action qui peut **supprimer des données** ou **couper un service**, prévenir l'utilisateur et vérifier la **sauvegarde**.

## 2. Cas 1 : « Je n'ai plus Internet » (fictif)

Léa (PC-07) n'accède plus aux sites web depuis ce matin. Ses collègues, eux, y accèdent.

Tests sur le poste (commandes courantes) :

| Test | Commande | Ce qu'il apprend |
|---|---|---|
| Adresse IP reçue | `ipconfig` (Windows) / `ip a` (Linux) | Le poste a-t-il une adresse valide ? |
| Passerelle joignable | `ping <passerelle>` | Le réseau local fonctionne-t-il ? |
| Internet par adresse | `ping 1.1.1.1` | La sortie vers Internet fonctionne-t-elle ? |
| Résolution de noms | `nslookup exemple.org` | Le DNS répond-il ? |

**Questions**

1. Pourquoi tester d'abord les collègues et le poste de Léa ?
2. Les résultats : passerelle **oui**, `ping 1.1.1.1` **oui**, `nslookup` **échec**. Quelle hypothèse ?
3. Quelle action proposes-tu ? Quelle vérification ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

**1.** Pour **délimiter** : un seul poste (cause locale) ou plusieurs (cause réseau/serveur) ?

**2.** Le réseau et la sortie vers Internet fonctionnent ; seule la **résolution de noms** échoue : le **serveur DNS** configuré sur le poste est mauvais ou injoignable.

**3.** Vérifier le serveur DNS configuré (par exemple avec `ipconfig /all`), le comparer à un poste qui fonctionne, corriger (configuration automatique ou serveur DNS correct), puis vérifier avec `nslookup` et l'ouverture d'un site ; faire confirmer par Léa.
</details>

## 3. Cas 2 : « Je ne peux plus imprimer »

Un service n'imprime plus sur l'imprimante réseau depuis ce matin ; d'autres services y arrivent.

**Questions**

1. Liste cinq hypothèses de la plus simple à la plus complexe.
2. Quels tests simples distinguent « imprimante » de « poste » ?

<details markdown="1">
<summary>Voir la réponse attendue</summary>

**1.** Imprimante éteinte ou en erreur (papier, bourrage) ; câble ou Wi-Fi ; file d'attente bloquée sur le poste ; imprimante par défaut changée ; pilote ou adresse de l'imprimante modifiés ; problème réseau du service.

**2.** Imprimer une page de test depuis l'imprimante ; imprimer depuis un autre poste du même service ; `ping` de l'adresse de l'imprimante depuis le poste ; vider la file d'attente.
</details>

## 4. Le ticket

| Champ | Exemple |
|---|---|
| **Titre** | Pas de résolution DNS sur PC-07 |
| **Demandeur / date** | Léa Martin, service administratif, 14/10 |
| **Description** | Les sites web ne s'ouvrent plus, symptômes depuis 8 h 30 |
| **Impact et urgence** | 1 utilisatrice, bloquée pour la facturation : urgence moyenne |
| **Diagnostic** | Réseau et sortie fonctionnels ; DNS en échec |
| **Cause** | Serveur DNS configuré manuellement avec une adresse incorrecte |
| **Action** | Retour en configuration automatique |
| **Vérification** | `nslookup` OK, ouverture d'un site confirmée par l'utilisatrice |
| **Clôture / durée** | 14/10, 25 minutes |
| **Prévention** | Aucune configuration DNS manuelle sur les postes |

**Exercice.** Rédige les tickets complets des deux cas.

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Démarche et hypothèses ordonnées | 5 |  |
| Tests choisis et interprétés | 5 |  |
| Corrections et vérifications | 4 |  |
| Ticket complet | 4 |  |
| Prévention et documentation | 2 |  |
| **Total** | **20** |  |
