# Récapitulatif du projet "Permissions"

| N°  | Fichier                        | Objectif                                                                 | Commande(s)/Concept(s) principal(aux)                  |
|-----|--------------------------------|--------------------------------------------------------------------------|--------------------------------------------------------|
| 0   | 0-iam_betty                    | Se connecter/switcher sur l'utilisateur `betty`                          | `su betty`                                             |
| 1   | 1-who_am_i                     | Afficher l’utilisateur effectif actuel                                   | `whoami`                                               |
| 2   | 2-groups                       | Afficher les groupes de l’utilisateur actuel                             | `groups`                                               |
| 3   | 3-new_owner                    | Changer le propriétaire du fichier `hello` à `betty`                     | `chown betty hello`                                   |
| 4   | 4-empty                        | Créer un fichier vide nommé `hello`                                      | `touch hello`                                         |
| 5   | 5-execute                      | Ajouter la permission d'exécution au propriétaire du fichier `hello`     | `chmod u+x hello`                                     |
| 6   | 6-multiple_permissions         | Ajouter `x` à owner/group et `r` à others pour `hello`                   | `chmod ug+x,o+r hello`                                |
| 7   | 7-everybody                    | Ajouter la permission d’exécution à tous les utilisateurs                | `chmod a+x hello`                                     |
| 8   | 8-James_Bond                   | Aucun droit à owner/group, tous les droits à others                      | `chmod 007 hello`                                     |
| 9   | 9-John_Doe                     | Donner les droits `rwxr-x-wx` à `hello`                                   | `chmod 715 hello`                                     |
| 10  | 10-mirror_permissions          | Copier les permissions de `olleh` vers `hello`                           | `chmod --reference=olleh hello`                       |
| 11  | 11-directories_permissions     | Ajouter `x` à tous les sous-dossiers du dossier courant                  | `chmod a+X *` avec test `-type d`                     |
| 12  | 12-directory_permissions       | Créer un dossier `my_dir` avec permissions `751`                         | `mkdir -m 751 my_dir`                                 |
| 13  | 13-change_group                | Changer le groupe du fichier `hello` à `school`                          | `chgrp school hello`                                  |
| 14  | 14-change_owner_and_group      | Changer propriétaire à `vincent` et groupe à `staff` pour tous           | `chown vincent:staff *`                               |
| 15  | 15-symbolic_link_permissions   | Changer owner/group d’un **lien symbolique** `_hello`                    | `chown -h vincent:staff _hello`                       |
| 16  | 16-if_only                     | Changer le owner à `vincent` **seulement si** c’est `guillaume`         | `chown vincent hello` avec `if` et `stat`/`find`      |

---

# Récapitulatif du projet `io_redirections_and_filters`

| #  | Nom du fichier                | Description                                                                                          | 
|----|-------------------------------|------------------------------------------------------------------------------------------------------|
| 0  | 0-hello_world                 | Affiche “Hello, World” suivi d’un saut de ligne.                                                    |
| 1  | 1-confused_smiley             | Affiche le smiley confus `"(Ôo)'`.                                                                   |
| 2  | 2-hellofile                   | Affiche le contenu du fichier `/etc/passwd`.                                                         | 
| 3  | 3-twofiles                    | Affiche le contenu de `/etc/passwd` et `/etc/hosts`.                                                 |
| 4  | 4-lastlines                   | Affiche les 10 dernières lignes de `/etc/passwd`.                                                    |
| 5  | 5-firstlines                  | Affiche les 10 premières lignes de `/etc/passwd`.                                                    |
| 6  | 6-third_line                  | Affiche la 3ᵉ ligne du fichier `iacta` (sans utiliser `sed`).                                       |
| 7  | 7-file                        | Crée un fichier avec un nom spécial contenant le texte `Best School` suivi d’un saut de ligne.      |
| 8  | 8-cwd_state                   | Écrit dans `ls_cwd_content` le résultat de la commande `ls -la`.                                     |
| 9  | 9-duplicate_last_line         | Duplique la dernière ligne du fichier `iacta`.                                                       |
| 10 | 10-no_more_js                 | Supprime tous les fichiers `.js` (pas les dossiers) dans le répertoire courant et ses sous-dossiers.|
| 11 | 11-directories                | Compte les dossiers et sous-dossiers (hors `.` et `..`, inclut les dossiers cachés).                  |
| 12 | 12-newest_files              | Affiche les 10 fichiers les plus récents du répertoire courant, triés du plus récent au plus ancien. |
| 13 | 13-unique                    | Affiche les mots qui apparaissent une seule fois dans une liste, triés par ordre alphabétique.       |
| 14 | 14-findthatword              | Affiche les lignes contenant le mot “root” dans le fichier `/etc/passwd`.                            |
| 15 | 15-countthatword             | Affiche le nombre de lignes contenant le mot “bin” dans `/etc/passwd`.                               |
| 16 | 16-whatsnext                 | Affiche les lignes contenant “root” suivies des 3 lignes suivantes dans `/etc/passwd`.               |
| 17 | 17-hidethisword              | Affiche les lignes de `/etc/passwd` ne contenant pas le mot “bin”.                                   |
| 18 | 18-letteronly                | Affiche les lignes de `/etc/ssh/sshd_config` qui commencent par une lettre (majuscule ou minuscule). |
| 19 | 19-AZ                        | Remplace les lettres `A` par `Z` et `c` par `e` dans l’entrée standard.                              |
| 20 | 20-hiago                     | Supprime toutes les lettres `c` et `C` de l’entrée standard.                                         |
| 21 | 21-reverse                   | Inverse l’entrée standard (chaîne de caractères).                                                    |
| 22 | 22-users_and_homes           | Affiche les utilisateurs et leurs répertoires personnels à partir de `/etc/passwd`, triés.           |

---


# 🐚 Projet : Shell - Init Files, Variables and Expansions

## ✅ Résumé des scripts et fonctionnalités

| #   | Script                          | Description                                                                                   | Commandes / Concepts principaux         |
|-----|----------------------------------|-----------------------------------------------------------------------------------------------|------------------------------------------|
| 0   | `0-alias`                        | Crée un alias `ls` pour `rm -f *`                                                              | `alias`                                  |
| 1   | `1-hello_you`                    | Affiche `hello <user>` où `<user>` est l'utilisateur actuel                                   | `whoami`, `echo`, substitution           |
| 2   | `2-path`                         | Ajoute `/action` à la fin du `PATH`                                                           | `export`, manipulation du `PATH`         |
| 3   | `3-paths`                        | Affiche le nombre de répertoires dans le `PATH`                                               | `echo $PATH`, `tr`, `wc -w`              |
| 4   | `4-global_variables`            | Liste toutes les variables d'environnement                                                    | `printenv`, `env`                        |
| 5   | `5-local_variables`             | Liste variables locales, d'environnement, fonctions                                            | `set`                                    |
| 6   | `6-create_local_variable`       | Crée une variable **locale** `BEST="School"`                                                  | `BEST="School"`                          |
| 7   | `7-create_global_variable`      | Crée une variable **globale** `BEST="School"`                                                 | `export BEST="School"`                   |
| 8   | `8-true_knowledge`              | Affiche la somme de 128 et `$TRUEKNOWLEDGE`                                                   | `echo $((128 + $TRUEKNOWLEDGE))`         |
| 9   | `9-divide_and_rule`             | Affiche le résultat de `$POWER` divisé par `$DIVIDE`                                          | `echo $((POWER / DIVIDE))`               |
| 10  | `10-love_exponent_breath`       | Affiche `$BREATH` puissance `$LOVE`                                                           | `echo $((BREATH ** LOVE))`               |
| 11  | `11-binary_to_decimal`          | Convertit un nombre binaire (`$BINARY`) en décimal                                            | `echo $((2#$BINARY))`                    |
| 12  | `12-combinations`               | Affiche toutes les combinaisons de 2 lettres sauf `oo`                                        | boucles `for`, conditions                |
| 13  | `13-print_float`                | Affiche la variable `$NUM` avec 2 décimales                                                   | `printf "%.2f\n" "$NUM"`                 |
| 14  | `14-decimal_to_hexadecimal`     | Convertit un nombre décimal (`$DECIMAL`) en hexadécimal                                       | `printf "%x\n" "$DECIMAL"`               |

---
