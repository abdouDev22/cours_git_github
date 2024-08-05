![[16964126324398_Downloadable Summary [Git et Github] .png]]

## Introduction à Git et aux plateformes de gestion de code

Git est un système de contrôle de version distribué qui permet de suivre les modifications dans le code source durant le développement logiciel. Il est utilisé par les développeurs pour collaborer sur des projets et gérer les versions du code. Ce cours couvre les bases de Git ainsi que des fonctionnalités avancées, en mettant l'accent sur les plateformes d'hébergement de code populaires.

### 1. Les plateformes d'hébergement de code

Les plateformes d'hébergement de code permettent aux développeurs de collaborer et de partager leur code. Voici les principales plateformes :

#### 1.1 GitHub
[GitHub](https://github.com/) est la plateforme de gestion de code la plus populaire. Elle offre une interface conviviale pour collaborer, suivre les problèmes et contribuer à des projets open source. GitHub propose des fonctionnalités gratuites et payantes, adaptées aux besoins des développeurs.

**Avantages :**
- Vaste communauté de développeurs
- Outils intégrés pour la gestion des projets
- Hébergement gratuit pour les projets publics

**Inconvénients :**
- Certaines fonctionnalités avancées sont payantes

#### 1.2 GitLab
[GitLab](https://about.gitlab.com/) est une alternative à GitHub, offrant des fonctionnalités similaires, y compris l'intégration continue (CI/CD). GitLab peut être hébergé sur leurs serveurs ou sur vos propres serveurs, offrant ainsi plus de contrôle.

**Avantages :**
- Hébergement sur vos propres serveurs
- Fonctionnalités de CI/CD intégrées

**Inconvénients :**
- Moins populaire pour les projets open source

#### 1.3 Bitbucket
[Bitbucket](https://bitbucket.org/) est une plateforme d'Atlassian, intégrée avec d'autres outils comme Jira. Elle est idéale pour les équipes utilisant la suite Atlassian.

**Avantages :**
- Intégration avec les outils Atlassian
- Version gratuite pour les petites équipes

**Inconvénients :**
- Moins de visibilité pour les projets open source

### 2. Configuration initiale de Git

Avant de commencer à utiliser Git, vous devez configurer vos informations utilisateur. Cela permet de suivre l'auteur des modifications.

#### 2.1 Configuration des informations utilisateur
```bash
git config --global user.name "Votre Nom"
git config --global user.email votre.email@example.com
```

Ces commandes définissent votre nom et votre email globalement sur votre système. Vous pouvez aussi les définir pour un projet spécifique en omettant l'option `--global`.

### 3. Les commandes de base de Git

#### 3.1 Initialisation d'un dépôt Git
Pour commencer à utiliser Git dans un projet, vous devez initialiser un dépôt.

```bash
git init
```

Cette commande crée un nouveau dépôt Git dans le répertoire courant.

#### 3.2 Ajouter des fichiers au suivi
Pour suivre les modifications d'un fichier, vous devez l'ajouter à l'index de Git.

```bash
git add chemin/vers/fichier
```

Pour ajouter tous les fichiers modifiés :

```bash
git add .
```

#### 3.3 Effectuer un commit
Un commit enregistre les modifications dans l'historique du projet.

```bash
git commit -m "Message décrivant les modifications"
```

#### 3.4 Visualiser l'état du dépôt
Pour voir l'état actuel des fichiers suivis et non suivis :

```bash
git status
```

#### 3.5 Afficher les différences entre les versions
Pour voir les modifications non commitées :

```bash
git diff
```

Pour voir les différences entre les commits :

```bash
git diff commit1 commit2
```

### 4. Gestion des branches

Les branches permettent de travailler sur des fonctionnalités ou des corrections de bugs indépendamment du reste du code.

#### 4.1 Créer une nouvelle branche
```bash
git branch nom_de_branche
```

#### 4.2 Basculer vers une branche
```bash
git checkout nom_de_branche
```

#### 4.3 Créer et basculer vers une nouvelle branche
```bash
git checkout -b nom_de_branche
```

#### 4.4 Fusionner une branche
Pour fusionner une branche dans la branche courante :

```bash
git merge nom_de_branche
```

#### 4.5 Supprimer une branche
Pour supprimer une branche locale :

```bash
git branch -d nom_de_branche
```

Pour forcer la suppression :

```bash
git branch -D nom_de_branche
```

#### 4.6 Lister les branches distantes
```bash
git branch -r
```

### 5. Collaboration et gestion des dépôts distants

#### 5.1 Ajouter un dépôt distant
```bash
git remote add origin git@github.com:VotreNomUtilisateur/nom_du_projet.git
```

#### 5.2 Pousser les modifications vers le dépôt distant
```bash
git push -u origin main
```

#### 5.3 Récupérer les modifications depuis le dépôt distant
```bash
git pull origin main
```

#### 5.4 Cloner un dépôt
```bash
git clone git@github.com:NomUtilisateur/NomDepot.git
```

### 6. Historique et gestion des commits

#### 6.1 Afficher l'historique des commits
```bash
git log
```

#### 6.2 Afficher les détails des modifications d'un fichier
```bash
git blame chemin/vers/fichier
```

#### 6.3 Afficher l'historique des références
```bash
git reflog
```

#### 6.4 Annuler un commit précédent
```bash
git revert HEAD^
```

#### 6.5 Appliquer des commits spécifiques à une autre branche
```bash
git cherry-pick d356940 de966d4
```

#### 6.6 Revenir à un commit précédent
Pour revenir au commit précédent tout en conservant les modifications locales :

```bash
git reset HEAD~
```

Pour revenir à un commit spécifique tout en supprimant toutes les modifications effectuées après :

```bash
git reset notreCommitCible --hard
```

**Attention :** Cette commande supprime toutes les modifications après le commit ciblé, y compris les commits non poussés. Vérifiez attentivement avant de l'utiliser pour éviter toute perte de données.

#### 6.7 Réinitialiser sans supprimer les modifications
Pour revenir juste après le dernier commit ou un commit spécifié, sans supprimer les modifications en cours :

```bash
git reset --mixed
```

Cette commande désindexe les fichiers, mais conserve les modifications locales, ce qui permet de recommencer une fonctionnalité tout en conservant les modifications non commitées.

### 7. Utilisation avancée de Git

#### 7.1 Stash des modifications non commités
Pour sauvegarder les modifications en cours sans les commiter :

```bash
git stash
```

Pour appliquer le dernier stash :

```bash
git stash apply
```

Pour afficher la liste des stashes :

```bash
git stash list
```

Pour appliquer un stash spécifique :

```bash
git stash apply stash@{numéro}
```

#### 7.2 Modifier le message d'un commit précédent
Pour modifier le message du dernier commit :

```bash
git commit --amend -m "Nouveau message de commit"
```

Pour modifier sans changer le message :

```bash
git commit --amend --no-edit
```

