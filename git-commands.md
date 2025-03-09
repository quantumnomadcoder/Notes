# Git - Commandes Essentielles

## Configuration

```bash
git config --global user.name "Nom Prénom"  # Définit le nom associé à vos commits
git config --global user.email "email@example.com"  # Définit l'email associé à vos commits
git config --global core.editor "code --wait"  # Configure l'éditeur par défaut (exemple avec VS Code)
git config --list  # Affiche toutes les configurations Git actuelles
```

## Création et Clonage de Dépôts

```bash
git init  # Initialise un nouveau dépôt Git dans le répertoire courant
git clone <url>  # Clone un dépôt existant depuis l'URL spécifiée
git clone <url> <directory>  # Clone un dépôt dans le répertoire spécifié
```

## Gestion des Modifications

```bash
git status  # Affiche l'état des fichiers (modifiés, indexés, non suivis)
git add <fichier>  # Ajoute un fichier spécifique à l'index
git add .  # Ajoute tous les fichiers modifiés à l'index
git reset <fichier>  # Retire un fichier de l'index sans perdre les modifications
git diff  # Affiche les modifications non indexées
git diff --staged  # Affiche les modifications indexées
```

## Commit et Historique

```bash
git commit -m "Message de commit"  # Crée un commit avec le message spécifié
git commit -am "Message de commit"  # Ajoute tous les fichiers modifiés et crée un commit
git log  # Affiche l'historique des commits
git log --oneline  # Affiche l'historique des commits en format condensé
git log --graph  # Affiche l'historique sous forme de graphe
git blame <fichier>  # Montre qui a modifié chaque ligne d'un fichier et quand
git show <commit-id>  # Affiche les détails d'un commit spécifique
```

## Branches

```bash
git branch  # Liste toutes les branches locales
git branch -a  # Liste toutes les branches (locales et distantes)
git branch <nom-branche>  # Crée une nouvelle branche
git checkout <nom-branche>  # Bascule vers la branche spécifiée
git checkout -b <nom-branche>  # Crée une nouvelle branche et bascule dessus
git switch <nom-branche>  # Bascule vers la branche spécifiée (Git moderne)
git switch -c <nom-branche>  # Crée une nouvelle branche et bascule dessus (Git moderne)
git branch -d <nom-branche>  # Supprime une branche (si fusionnée)
git branch -D <nom-branche>  # Force la suppression d'une branche (même non fusionnée)
```

## Fusion et Rebase

```bash
git merge <nom-branche>  # Fusionne la branche spécifiée dans la branche courante
git merge --abort  # Annule une fusion en cours en cas de conflits
git rebase <nom-branche>  # Réapplique les commits de la branche courante sur une autre branche
git rebase -i HEAD~n  # Lance un rebase interactif des n derniers commits
```

## Gestion des Conflits

```bash
git diff --check  # Vérifie s'il y a des conflits potentiels
git mergetool  # Lance l'outil de résolution de conflits configuré
git add <fichier>  # Marque un fichier comme résolu après avoir réglé les conflits
```

## Travail à Distance

```bash
git remote -v  # Affiche les dépôts distants configurés
git remote add <nom> <url>  # Ajoute un nouveau dépôt distant
git remote remove <nom>  # Supprime un dépôt distant
git fetch <remote>  # Récupère les modifications depuis le dépôt distant
git pull  # Récupère et fusionne les modifications distantes dans la branche courante
git push <remote> <branche>  # Envoie les commits locaux vers le dépôt distant
git push -u <remote> <branche>  # Envoie et configure la branche pour suivre la branche distante
```

## Annulation et Modifications

```bash
git restore <fichier>  # Restaure un fichier à son état dans HEAD (Git moderne)
git checkout -- <fichier>  # Restaure un fichier à son état dans HEAD (ancienne syntaxe)
git reset --soft HEAD~1  # Annule le dernier commit mais conserve les modifications
git reset --hard HEAD~1  # Annule le dernier commit et supprime les modifications
git revert <commit-id>  # Crée un nouveau commit qui annule les modifications d'un commit spécifique
git clean -fd  # Supprime tous les fichiers non suivis et répertoires
```

## Stash

```bash
git stash  # Met de côté les modifications en cours
git stash save "message"  # Met de côté les modifications avec un message descriptif
git stash list  # Affiche la liste des stashs
git stash apply  # Applique le dernier stash sans le supprimer
git stash pop  # Applique le dernier stash et le supprime
git stash drop stash@{n}  # Supprime un stash spécifique
```

## Tags

```bash
git tag  # Liste tous les tags
git tag <nom-tag>  # Crée un tag léger
git tag -a <nom-tag> -m "Message"  # Crée un tag annoté avec un message
git push <remote> <nom-tag>  # Envoie un tag spécifique vers le dépôt distant
git push <remote> --tags  # Envoie tous les tags vers le dépôt distant
```

## Sous-modules

```bash
git submodule add <url> <path>  # Ajoute un sous-module au chemin spécifié
git submodule init  # Initialise les sous-modules après un clone
git submodule update  # Met à jour les sous-modules à leur commit configuré
git submodule update --remote  # Met à jour les sous-modules à leur dernière version
```

## Recherche et Filtrage

```bash
git grep "terme"  # Cherche un terme dans les fichiers du dépôt
git log -S "terme"  # Cherche les commits qui ont ajouté ou supprimé le terme
git log --author="nom"  # Filtre les commits par auteur
git log --since="date" --until="date"  # Filtre les commits par plage de dates
```

## Maintenance

```bash
git gc  # Lance le ramasse-miettes pour optimiser le dépôt
git prune  # Supprime les objets orphelins
git fsck  # Vérifie l'intégrité du dépôt
git reflog  # Affiche l'historique des références (utile pour récupérer des commits perdus)
```

## Workflow Avancé

```bash
git cherry-pick <commit-id>  # Applique les modifications d'un commit spécifique à la branche courante
git rebase --onto <nouvelle-base> <ancienne-base>  # Change la base d'une série de commits
git worktree add <path> <branch>  # Crée un nouveau répertoire de travail lié au dépôt
git bisect start  # Démarre une recherche binaire pour trouver un commit problématique
```
