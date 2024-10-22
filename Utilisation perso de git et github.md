Voici une version plus structurée et détaillée du fichier que vous avez partagé, avec des explications pour chaque point comme s'il s'agissait d'un cours complet :

---

## Introduction à Git et aux plateformes de gestion de code

Git est un système de contrôle de version distribué qui permet de suivre les modifications du code source durant le développement logiciel. Il est utilisé pour faciliter la collaboration entre développeurs et pour gérer les différentes versions du code d'un projet. Dans ce cours, vous découvrirez les bases de Git ainsi que des fonctionnalités avancées. Nous nous concentrerons également sur les plateformes d'hébergement de code comme GitHub, GitLab et Bitbucket.

---

## 1. Les plateformes d'hébergement de code

Les plateformes d'hébergement de code jouent un rôle clé dans la gestion et la collaboration sur les projets de développement. Elles permettent aux développeurs de partager leur code, suivre les bugs et les nouvelles fonctionnalités via des **issues**, et gérer le développement via des branches et des pull requests.

### 1.1 GitHub

[GitHub](https://github.com/) est la plateforme la plus populaire pour héberger du code source. Elle propose une interface conviviale, idéale pour les projets open source et privés.

- **Avantages :**
  - Vaste communauté de développeurs
  - Outils intégrés pour la gestion des projets (issues, pull requests)
  - Hébergement gratuit pour les projets publics

- **Inconvénients :**
  - Certaines fonctionnalités avancées sont payantes (comme GitHub Actions ou l'accès à des statistiques avancées)

### 1.2 GitLab

[GitLab](https://about.gitlab.com/) est une autre plateforme populaire, offrant des fonctionnalités similaires à GitHub. Elle se distingue par ses options d’intégration continue (CI/CD), qui permettent d’automatiser les tests et les déploiements.

- **Avantages :**
  - Hébergement sur vos propres serveurs pour plus de contrôle
  - Fonctionnalités CI/CD puissantes et gratuites

- **Inconvénients :**
  - Moins utilisée pour les projets open source par rapport à GitHub

### 1.3 Bitbucket

[Bitbucket](https://bitbucket.org/) fait partie de la suite Atlassian et s'intègre parfaitement avec des outils tels que Jira pour une gestion de projet complète.

- **Avantages :**
  - Intégration fluide avec les outils Atlassian
  - Plan gratuit pour les petites équipes

- **Inconvénients :**
  - Moins de projets open source en comparaison avec GitHub ou GitLab

---

## 2. Configuration initiale de Git

Avant de commencer à utiliser Git, il est nécessaire de configurer votre environnement avec vos informations utilisateur. Cela permet à Git d'associer chaque modification que vous faites à votre identité.

### 2.1 Configuration des informations utilisateur

Utilisez les commandes suivantes pour définir votre nom et votre adresse email dans Git :

```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```

Ces informations seront utilisées à chaque commit pour identifier l’auteur. Si vous souhaitez configurer ces informations uniquement pour un projet spécifique, ne mettez pas l'option `--global`.

---

## 3. Commandes de base de Git

### 3.1 Initialisation d'un dépôt Git

Pour commencer à utiliser Git dans un projet, il faut initialiser un dépôt Git. Cela crée un répertoire `.git` dans lequel toutes les informations du contrôle de version seront stockées.

```bash
git init
```

### 3.2 Ajouter des fichiers au suivi

Pour commencer à suivre un fichier et le versionner avec Git, vous devez l'ajouter à l'index :

```bash
git add chemin/vers/fichier
```

Pour ajouter tous les fichiers modifiés dans le répertoire courant :

```bash
git add .
```

### 3.3 Effectuer un commit

Une fois les modifications prêtes, vous pouvez les enregistrer dans l'historique du projet avec un commit :

```bash
git commit -m "Message décrivant les modifications"
```

### 3.4 Visualiser l'état du dépôt

Pour voir l'état actuel des fichiers suivis et non suivis, utilisez la commande suivante :

```bash
git status
```

### 3.5 Afficher les différences entre les versions

Pour voir les différences entre les fichiers modifiés et la dernière version commitée :

```bash
git diff
```

Pour comparer deux commits spécifiques :

```bash
git diff commit1 commit2
```

---

## 4. Gestion des branches

Les branches permettent de travailler sur des fonctionnalités ou des corrections de bugs sans affecter le code principal.

### 4.1 Créer une nouvelle branche

Pour créer une nouvelle branche sans basculer immédiatement dessus :

```bash
git branch nom_de_branche
```

### 4.2 Basculer vers une branche

Pour passer d'une branche à une autre :

```bash
git checkout nom_de_branche
```

### 4.3 Créer et basculer vers une nouvelle branche

Si vous souhaitez créer une branche et y basculer directement :

```bash
git checkout -b nom_de_branche
```

### 4.4 Fusionner une branche

Pour fusionner une branche dans la branche courante (généralement `main` ou `develop`) :

```bash
git merge nom_de_branche
```

### 4.5 Supprimer une branche

Après avoir fusionné une branche, vous pouvez la supprimer en local avec :

```bash
git branch -d nom_de_branche
```

Si vous forcez la suppression d'une branche sans vérifier son statut :

```bash
git branch -D nom_de_branche
```

### 4.6 Lister les branches distantes

Pour voir les branches présentes sur le dépôt distant :

```bash
git branch -r
```

---

## 5. Collaboration et gestion des dépôts distants

### 5.1 Ajouter un dépôt distant

Pour ajouter un dépôt distant (par exemple, sur GitHub) :

```bash
git remote add origin git@github.com:VotreNomUtilisateur/nom_du_projet.git
```

### 5.2 Pousser les modifications vers le dépôt distant

Une fois les modifications locales prêtes à être partagées avec d'autres collaborateurs, poussez-les vers le dépôt distant :

```bash
git push -u origin main
```

### 5.3 Récupérer les modifications depuis le dépôt distant

Pour synchroniser votre dépôt local avec les dernières modifications du dépôt distant :

```bash
git pull origin main
```

### 5.4 Cloner un dépôt

Si vous souhaitez démarrer un projet en récupérant une copie d’un dépôt distant :

```bash
git clone git@github.com:NomUtilisateur/NomDepot.git
```

---

## 6. Historique et gestion des commits

### 6.1 Afficher l'historique des commits

Pour afficher un historique des commits effectués sur le projet :

```bash
git log
```

### 6.2 Afficher les détails des modifications d'un fichier

Pour voir qui a modifié chaque ligne d’un fichier, utilisez :

```bash
git blame chemin/vers/fichier
```

### 6.3 Afficher l'historique des références

Pour voir l’historique des commandes et références :

```bash
git reflog
```

### 6.4 Annuler un commit précédent

Pour annuler un commit précédent tout en gardant l’historique intact, utilisez :

```bash
git revert HEAD^
```

### 6.5 Appliquer des commits spécifiques à une autre branche

Pour appliquer un ou plusieurs commits spécifiques à une autre branche sans tout fusionner :

```bash
git cherry-pick d356940 de966d4
```

### 6.6 Revenir à un commit précédent

Pour revenir à un commit précédent tout en conservant les modifications locales :

```bash
git reset HEAD~
```

Pour revenir à un commit spécifique et supprimer toutes les modifications ultérieures :

```bash
git reset notreCommitCible --hard
```

**Attention :** Cette commande supprime toutes les modifications non poussées. Assurez-vous de bien comprendre les conséquences avant de l'utiliser.

### 6.7 Réinitialiser sans supprimer les modifications

Si vous souhaitez revenir à un commit spécifique sans perdre les modifications locales :

```bash
git reset --mixed
```

---

## 7. Utilisation avancée de Git

### 7.1 Stash des modifications non commités

Si vous avez besoin de sauvegarder des modifications non terminées sans les commiter, vous pouvez les stasher :

```bash
git stash
```

Pour appliquer le dernier stash :

```bash
git stash apply
```

Pour lister tous les stashes :

```bash
git stash list
```

Pour appliquer un stash spécifique :

```bash
git stash apply stash@{numéro}
```

### 7.2 Modifier le message d'un commit précédent

Si vous avez fait une erreur dans le message d’un commit, vous pouvez le modifier avec :

```bash
git commit --amend -m "Nouveau message de commit"
```

Si vous voulez modifier le commit sans changer le message :

```bash
git commit --amend --no-edit
```
