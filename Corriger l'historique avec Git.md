## Corriger l'historique avec Git

### Modifier un commit avec `git commit --amend`

Si vous avez oublié d'ajouter un fichier à votre dernier commit ou souhaitez changer son message, utilisez `git commit --amend` :

```bash
git add fichier-oublie.txt
git commit --amend
```

Cela modifie le dernier commit sans créer un nouveau commit.

### Réécrire l'historique avec `git rebase`

Le rebase permet de rejouer une série de commits sur une autre base, souvent utilisé pour garder un historique propre et linéaire :

```bash
git checkout feature-branch
git rebase main
```

### Utiliser `git stash`

Si vous travaillez sur une tâche, mais devez soudainement en commencer une autre, utilisez `git stash` pour mettre de côté vos modifications :

```bash
git stash
```

Vous pouvez ensuite récupérer votre travail avec :

```bash
git stash pop
```
