## Utilisation de GitFlow

GitFlow est un workflow Git structurant le développement en branches spécifiques : `develop`, `feature`, `release`, et `hotfix`.

### Étape 1 : Initialiser GitFlow

Pour utiliser GitFlow dans un projet, vous devez l'initialiser avec :

```bash
git flow init
```

### Étape 2 : Démarrer une nouvelle fonctionnalité

Chaque fonctionnalité doit être développée sur une branche dédiée :

```bash
git flow feature start issue5
```

### Étape 3 : Finaliser la fonctionnalité

Une fois la fonctionnalité terminée, vous la fusionnez dans `develop` :

```bash
git flow feature finish issue5
```

### Étape 4 : Gérer les releases

Les releases sont préparées sur une branche spécifique. Commencez une nouvelle release avec :

```bash
git flow release start 0.0.2
```

Finalisez la release avec :

```bash
git flow release finish '0.0.2'
```
