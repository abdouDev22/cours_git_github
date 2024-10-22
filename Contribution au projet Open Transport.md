## Introduction

Contribuer à des projets open source est une excellente façon d'améliorer vos compétences en développement, de collaborer avec d'autres développeurs, et d'apporter une réelle valeur à la communauté. Dans ce guide, nous allons voir comment configurer votre environnement, faire votre première contribution, et adopter de bonnes pratiques Git, notamment en utilisant GitFlow.

---

## Mettez en place votre environnement

### 1. Installer Git

Pour commencer, assurez-vous que **Git** est installé sur votre machine. Vous pouvez vérifier cela en exécutant la commande suivante dans votre terminal :

```bash
git --version
```

Si Git n'est pas installé, vous pouvez le télécharger et l'installer en suivant [ce guide d'installation](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

### 2. Créer un compte GitHub

Vous devez avoir un compte GitHub pour pouvoir contribuer à des projets open source. Si vous n'avez pas encore de compte, créez-en un sur [github.com](https://github.com/).

### 3. Configurer votre environnement Git

Après avoir installé Git et créé un compte GitHub, configurez Git en liant votre compte GitHub avec les informations suivantes :

```bash
git config --global user.name "VotreNomGitHub"
git config --global user.email "VotreEmailGitHub"
```

Cette configuration permet à Git de vous identifier lorsque vous contribuez à des projets.

---

## Apportez votre première contribution

### 1. Comprendre les Issues sur GitHub

Les **issues** sont des tickets ou des tâches ouvertes sur un projet GitHub. Elles sont utilisées pour :

- Identifier des bugs,
- Proposer des nouvelles fonctionnalités,
- Discuter des améliorations du code.

Les contributeurs et les mainteneurs de projet utilisent les issues pour organiser le travail. Les issues peuvent être catégorisées par priorité, par type de tâche, ou par difficulté. Cela vous permet de choisir une issue adaptée à votre niveau technique.

### 2. Parcourir les Issues du projet Open Transport

Pour commencer à contribuer, vous pouvez parcourir la [liste des issues](https://github.com/OpenClassrooms-Student-Center/7688581-Expert-Git-GitHub/issues) du projet Open Transport. Choisissez une issue étiquetée "good first issue" si vous êtes débutant, car ce type d'issue est spécifiquement destiné aux nouveaux contributeurs.

Par exemple, une issue courante pourrait être une correction dans le fichier `README.md`. Voici les étapes pour résoudre ce type d'issue :

### 3. Plan d’action pour résoudre une issue

#### Étape 1 : Forker le projet

Forker un projet signifie copier son repository GitHub dans votre propre compte. Pour forker Open Transport :

- Rendez-vous sur la page du projet.
- Cliquez sur le bouton **Fork** dans le coin supérieur droit.

Cela crée une copie du projet dans votre compte GitHub, sur laquelle vous pouvez travailler.

#### Étape 2 : Cloner le projet en local

Après avoir forké le projet, clonez-le sur votre machine locale avec la commande suivante :

```bash
git clone https://github.com/VotreNomUtilisateur/Open-Transport.git
```

Cela télécharge une copie du projet sur votre ordinateur.

#### Étape 3 : Créer une branche pour la modification

Avant de commencer à travailler, créez une nouvelle branche dédiée à votre contribution. Cela permet de travailler de manière isolée sans affecter la branche principale du projet :

```bash
git checkout -b correction-readme
```

#### Étape 4 : Modifier le fichier concerné

Ouvrez le fichier `README.md` ou tout autre fichier que vous souhaitez modifier. Apportez vos corrections, puis enregistrez vos modifications.

#### Étape 5 : Ajouter et committer vos modifications

Ajoutez les modifications à l'index Git pour les préparer à être commises :

```bash
git add README.md
```

Ensuite, commettez vos changements avec un message clair expliquant votre contribution et en mentionnant le numéro de l’issue :

```bash
git commit -m "Correction du texte du README.md (#issue1)"
```

#### Étape 6 : Pousser les changements vers votre fork

Envoyez les modifications vers votre repository GitHub en utilisant la commande `git push` :

```bash
git push origin correction-readme
```

#### Étape 7 : Créer une Pull Request (PR)

Une fois vos modifications poussées, allez sur GitHub et créez une Pull Request depuis votre fork. Dans cette PR, mentionnez le numéro de l’issue que vous avez résolue, décrivez brièvement vos modifications, puis soumettez la PR pour qu'elle soit examinée par les mainteneurs du projet.