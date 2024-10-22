### Étape 1 : Mettre à jour votre branche locale

Avant de résoudre un conflit, vous devez vous assurer que votre branche locale est à jour. Utilisez la commande suivante pour récupérer les dernières modifications depuis la branche distante :

```bash
git pull origin main
```

### Étape 2 : Identifier et résoudre les conflits

Lorsque vous faites un merge ou un rebase, Git vous indique les fichiers en conflit. Vous pouvez les lister avec `git status`. Ensuite, ouvrez chaque fichier marqué comme en conflit et résolvez le problème.

Les conflits apparaissent dans ce format :

```
<<<<<<< HEAD
Votre modification locale
=======
La modification sur la branche distante
>>>>>>>
```

Vous devez décider quelle version conserver et supprimer les balises `<<<<<<<`, `=======`, et `>>>>>>>`.

### Étape 3 : Marquer les conflits comme résolus

Une fois les conflits résolus, marquez-les comme résolus avec la commande `git add` :

```bash
git add nom-du-fichier
```

Finalisez ensuite le merge ou le rebase avec :

```bash
git commit
# ou
git rebase --continue
```
