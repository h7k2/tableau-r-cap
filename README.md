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

# Récapitulatif des concepts - Projet Shell I/O Redirections & Filters

| 0  | `0-hello_world`              | `echo "Hello, World"`                                              | Affichage sur la sortie standard                                                    |
| 1  | `1-confused_smiley`          | `echo "\"(Ôo)'"`                                                   | Affichage de caractères spéciaux                                                    |
| 2  | `2-hellofile`                | `cat /etc/passwd`                                                  | Lecture et affichage d’un fichier                                                   |
| 3  | `3-twofiles`                 | `cat /etc/passwd /etc/hosts`                                       | Lecture de plusieurs fichiers                                                       |
| 4  | `4-lastlines`                | `tail /etc/passwd`                                                 | Affichage des 10 dernières lignes d’un fichier                                      |
| 5  | `5-firstlines`               | `head /etc/passwd`                                                 | Affichage des 10 premières lignes                                                   |
| 6  | `6-third_line`               | `head -n 3 iacta \| tail -n 1`                                     | Affichage d’une ligne spécifique (3e ligne)                                         |
| 7  | `7-file`                     | `echo "Best School" > '\*\\'"Best School"\'\\*\$?\*\*\*\*\*:)'`   | Création d’un fichier au nom complexe + redirection                                 |
| 8  | `8-cwd_state`                | `ls -la > ls_cwd_content`                                          | Redirection de la sortie standard vers un fichier                                  |
| 9  | `9-duplicate_last_line`      | `tail -n 1 iacta >> iacta`                                         | Redirection avec ajout (append) de contenu                                          |
| 10 | `10-no_more_js`             | `find . -type f -name "*.js" -delete`                              | Suppression de fichiers avec `find`                                                 |
| 11 | `11-directories`            | `find . -type d \| wc -l`                                          | Compte tous les répertoires (y compris `.`)                                         |
| 12 | `12-newest_files`           | `ls -t \| head -n 10`                                              | Tri par date de modification + sélection des 10 plus récents                       |
| 13 | `13-unique`                 | `sort \| uniq -u`                                                  | Filtrer les lignes uniques (non dupliquées)                                        |
| 14 | `14-findthatword`           | `grep -w "root" /etc/passwd`                                       | Recherche d’un mot entier dans un fichier                                          |
| 15 | `15-countthatword`          | `grep -cw "bin" /etc/passwd`                                       | Compter le nombre exact d’occurrences d’un mot                                     |
| 16 | `16-whatsnext`              | `cut -d: -f1 /etc/passwd \| sort`                                  | Extraction de champs (cut) + tri                                                    |
| 17 | `17-hidethisword`           | `grep -v "root" /etc/passwd`                                       | Exclure les lignes contenant un mot donné                                          |
| 18 | `18-letteronly`             | `grep "^[a-zA-Z]*$"`                                               | Filtrer les lignes ne contenant que des lettres                                    |
| 19 | `19-AZ`                     | `tr "A-Z" "a-z"`                                                   | Conversion des majuscules en minuscules                                            |
| 20 | `20-hiago`                  | `tr -d "c"`                                                        | Suppression d’un caractère donné                                                    |
| 21 | `21-reverse`                | `rev`                                                              | Inversion des lignes                                                               |
| 22 | `22-users_and_homes`        | `cut -d: -f1,6 /etc/passwd \| sort` 

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
