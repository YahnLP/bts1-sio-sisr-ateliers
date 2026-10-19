# C04 – Automatiser une sauvegarde avec un script Bash

## 1. Principes

| Principe | Application |
|---|---|
| **Automatiser** | Ne pas dépendre d'un oubli |
| **Contrôler les erreurs** | Un script qui échoue silencieusement est dangereux |
| **Dater** | Pouvoir retrouver une version précise |
| **Limiter la rétention** | Ne pas saturer le disque |
| **Séparer** | La sauvegarde ne doit pas rester sur la même machine (règle du 3-2-1) |
| **Tester la restauration** | Une sauvegarde non testée n'est pas une sauvegarde |

## 2. Le script

À enregistrer sous `sav.sh` puis rendre exécutable (`chmod +x sav.sh`). À tester **dans le laboratoire**.

```bash
#!/bin/bash
# Sauvegarde datée avec conservation des 7 dernières archives
set -u
SRC="${1:-}"
DEST="${2:-}"
KEEP=7
if [ -z "$SRC" ] || [ -z "$DEST" ]; then
  echo "Usage : $0 <dossier_source> <dossier_destination>" >&2
  exit 1
fi
if [ ! -d "$SRC" ]; then
  echo "Erreur : source introuvable : $SRC" >&2
  exit 2
fi
mkdir -p "$DEST" || exit 3
ARCHIVE="$DEST/sauvegarde-$(date +%Y-%m-%d_%H%M%S).tar.gz"
if tar -czf "$ARCHIVE" -C "$SRC" . ; then
  echo "OK : $ARCHIVE"
else
  echo "Erreur : échec de l'archive" >&2
  exit 4
fi
ls -1t "$DEST"/sauvegarde-*.tar.gz 2>/dev/null | tail -n +$((KEEP+1)) | while read -r f; do
  rm -- "$f" && echo "Supprimé (ancien) : $f"
done
```

### Je comprends

| Ligne | Rôle |
|---|---|
| `set -u` | Erreur si une variable n'est pas définie |
| `SRC`, `DEST` | Arguments : dossier à sauvegarder et dossier de destination |
| Tests `-z` et `-d` | Vérifier les arguments et l'existence de la source |
| `exit 1` à `4` | Codes de sortie distincts pour savoir **ce qui a échoué** |
| `date +%Y-%m-%d_%H%M%S` | Nom daté, triable |
| `tar -czf` | Archive compressée du contenu de la source |
| `ls -1t` puis `tail -n +8` | `ls -1t` liste les archives de la plus récente à la plus ancienne ; `tail -n +8` ne retient que celles au-delà des 7 plus récentes, qui sont supprimées par la boucle |

### Tests à réaliser

| Test | Attendu |
|---|---|
| `./sav.sh` sans argument | Message d'usage, code de sortie 1 |
| `./sav.sh /dossier/inexistant /tmp/sauv` | Erreur « source introuvable », code 2 |
| Lancer 9 fois avec un dossier valide | Il reste **7** archives |

Pour lire le code de sortie : `echo $?` juste après la commande.

## 3. Planification

La planification se fait avec `cron`. La commande `crontab -e` ouvre la table de l'utilisateur ; la ligne suivante lance la sauvegarde **chaque jour à 2 h** :

```text
0 2 * * * /usr/local/bin/sav.sh /srv/donnees /srv/sauvegardes >> /var/log/sav.log 2>&1
```

Les cinq champs sont : minute, heure, jour du mois, mois, jour de la semaine. Le journal `/var/log/sav.log` permet de vérifier l'exécution.

## 4. Test de restauration

| Étape | Commande |
|---|---|
| Lister le contenu d'une archive | `tar -tzf <archive>` |
| Restaurer dans un dossier de test | `mkdir /tmp/restau && tar -xzf <archive> -C /tmp/restau` |
| Comparer avec la source | `diff -r <source> /tmp/restau` |

Aucune différence affichée signifie que la restauration est conforme.

> [!WARNING]
> Ne restaure **jamais** par-dessus les données de production sans l'avoir testé ailleurs. Une sauvegarde qui reste sur le **même disque** que la source ne protège pas d'une panne du disque : prévoir une copie sur un autre support ou un autre site.

## 5. Documenter

Pour le portfolio : besoin, choix (rétention de 7, heure, destination), **journal des tests**, **preuve de restauration** (capture du `diff` vide), procédure de reprise.

## Grille d'évaluation (20 points)

| Critère | Points | Auto-évaluation |
|---|---:|---|
| Script exécuté, erreurs gérées | 5 |  |
| Rétention vérifiée (7 archives) | 4 |  |
| Planification correcte | 3 |  |
| Restauration prouvée | 5 |  |
| Documentation et limites (même disque) | 3 |  |
| **Total** | **20** |  |
