https://www.youtube.com/watch?v=Qc9ADZ4JfOc


### Mettez en place votre environnement

![[16529685405762_P1C2-2.png]]

### Apportez votre première contribution

Pour permettre à tous de contribuer, Open Transport utilise la fonctionnalité GitHub **Issues**.

Les issues permettent d’identifier une tâche à réaliser sur le projet. Elles peuvent représenter de nouvelles fonctionnalités, des corrections, des problèmes à résoudre, etc. Elles sont généralement hiérarchisées, par exemple par type, par importance, par thématique, etc.

Ainsi, une façon de commencer à contribuer est de lire les issues du projet et d’en choisir une à notre portée technique. Je vous laisse parcourir [la liste des issues](https://github.com/OpenClassrooms-Student-Center/7688581-Expert-Git-GitHub/issues) du projet Open Transport.

Je vous propose de traiter [la première issue](https://github.com/OpenClassrooms-Student-Center/7688581-Expert-Git-GitHub/issues/1), qui correspond à une erreur de texte dans le fichier README.md :

Notre plan d’attaque est le suivant :

1. Modifier en local le fichier README.md.
    
2. Faire un git add, un git commit (avec le numéro de l’issue dans le message, cf. [les règles de contribution](https://github.com/OpenClassrooms-Student-Center/7688581-Expert-Git-GitHub/blob/main/CODE_OF_CONDUCT.md)) et un git push pour envoyer la modification sur notre repository distant (le fork).
    
3. Créer une pull request via l’interface graphique de GitHub.
    

Pour les étapes 1 et 2, je vous fais entièrement confiance, vous n’avez pas besoin de mon aide ! Sinon, je vous invite à consulter [ce chapitre](https://openclassrooms.com/fr/courses/7162856-gerez-du-code-avec-git-et-github/7165726-travaillez-depuis-votre-depot-local-git#/id/r-7481074) du cours _Gérez du code avec Git et GitHub_.



CONTRIBUTING.md

# CONTRIBUTING

```
Avant toutes choses, merci de vouloir contribuer au projet Open Transport !   
C'est grâce à ce genre d'investissement que nous pourrons favoriser un covoiturage solidaire.
```

Open Transport recherche des contributeurs pour tous types de tâches : améliorations, correction de bugs, nouvelles fonctionnalités.

## Comment contriburer ?


Pour commencer, nous recommendons de consulter la liste des [issues](https://github.com/OpenClassrooms-Student-Center/7688581-Expert-Git-GitHub/issues)   

- Chaque issue est catégorisée et nous demandons à ce qu'une première contribution soit obligatoire une issue de type "good first issue".  
- Un contributeur doit forker le projet source puis pourra soumettre ces contributions via des pull requests.  
- Les pulls requests seront ensuite revues et traitées. L'issue associée sera mise à jour en conséquence.  
- Les commentaires doivent contenir le numéro de l'issue.


## Résolvez les conflits avec Git

Décryptons :

- Les chaînes de caractères _**<<<<<<<**_ et _**>>>>>>>**_ balisent la zone de conflit ;
    
- La première partie du texte qui suit le mot _**HEAD**_ correspond à la modification locale ;
    
- La chaîne _**=======**_ indique la fin de cette modification, et il s’ensuit la modification distante en conflit ;
    
- Le texte _**a6c82f75db73fc5aaec7fc2ef175253133876565**_ correspond au numéro d’identification unique du commit d’où provient le texte en conflit.


### 1. Mettre à jour votre branche locale

Avant de commencer à résoudre des conflits, assurez-vous que votre branche locale est à jour avec la branche distante en utilisant la commande suivante :

bash

Copier le code

`git pull`

### 2. Effectuer le merge ou rebase

Lorsque vous essayez de fusionner ou de rebaser une branche et que des conflits surviennent, vous verrez un message vous indiquant qu'il y a des conflits. Voici comment vous pouvez déclencher un merge ou un rebase :

bash

Copier le code

`# Pour un merge git merge nom-de-la-branche  # Pour un rebase git rebase nom-de-la-branche`

### 3. Identifier les fichiers en conflit

Git marquera les fichiers en conflit et vous devrez les résoudre manuellement. Vous pouvez lister les fichiers en conflit avec :

bash

Copier le code

`git status`

Cela affichera une liste de fichiers sous la section "Unmerged paths".

### 4. Résoudre les conflits

Ouvrez chaque fichier en conflit dans un éditeur de texte. Vous verrez quelque chose comme ceci :

diff

Copier le code

`<<<<<<< HEAD Votre modification locale ======= La modification sur la branche distante >>>>>>> nom-de-la-branche`

Les lignes entre `<<<<<<<` et `=======` représentent votre version, et celles entre `=======` et `>>>>>>>` représentent la version de l'autre branche. Modifiez le fichier en fonction de la solution que vous souhaitez conserver.

### 5. Marquer les conflits comme résolus

Une fois les conflits résolus, vous devez ajouter les fichiers résolus à l'index Git pour indiquer que les conflits ont été résolus :

bash

Copier le code

`git add nom-du-fichier`

### 6. Finaliser le merge ou le rebase

- Si vous avez effectué un **merge** :

bash

Copier le code

`git commit`

Git vous proposera un message de commit par défaut que vous pouvez modifier.

- Si vous avez effectué un **rebase** :

bash

Copier le code

`git rebase --continue`

### 7. Pousser les modifications

Enfin, poussez vos changements vers la branche distante :

bash

Copier le code

`git push`

Ces étapes devraient vous permettre de résoudre les conflits avec Git de manière fluide.


## Corrigez l’historique du projet au fil de vos développements

- **git commit --amend** permet de modifier le dernier commit.
    
- **git rebase** permet de réécrire l’historique d’une branche.
    
- **git stash** permet de mettre de côté le développement en cours.
    
- **git stash pop** permet de récupérer le développement mis de côté.
    
- **git bisect** permet d’identifier un commit problématique en parcourant l’historique. 
    
- **git revert** permet d’annuler un commit.



#### **1. git commit --amend**
La commande `git commit --amend` permet de modifier le dernier commit. Elle est utile lorsque vous avez oublié d'ajouter un fichier ou que vous souhaitez changer le message du commit.

**Cas d'utilisation :**  
Imaginons que vous venez de faire un commit, mais vous réalisez que vous avez oublié d'ajouter un fichier important. Au lieu de faire un nouveau commit, vous pouvez utiliser `git commit --amend` pour l'ajouter au précédent commit.

**Exemple :**
```bash
git add fichier-oublie.txt
git commit --amend
```
Cela ouvrira un éditeur de texte pour modifier le message du commit si nécessaire.

#### **2. git rebase**
La commande `git rebase` permet de réécrire l’historique d’une branche en la "rejouant" sur une autre base. Elle est souvent utilisée pour garder un historique linéaire et propre.

**Cas d'utilisation :**  
Vous avez travaillé sur une branche et vous voulez intégrer vos modifications dans la branche `main`, mais au lieu d'utiliser un `git merge`, vous voulez un historique linéaire sans commits de fusion (merge commits). Vous utilisez alors `git rebase`.

**Exemple :**
```bash
git checkout feature-branch
git rebase main
```
Cela repositionne les commits de `feature-branch` sur la dernière version de `main`.

#### **3. git stash**
`git stash` permet de mettre de côté des modifications non terminées sans les compromettre dans un commit. C’est idéal lorsque vous devez interrompre votre travail pour passer à une autre tâche urgente.

**Cas d'utilisation :**  
Vous travaillez sur une fonctionnalité, mais une autre tâche plus prioritaire survient. Vous ne voulez pas commettre un travail inachevé, donc vous "stash" (mettez de côté) vos modifications.

**Exemple :**
```bash
git stash
```

#### **4. git stash pop**
Une fois que vous avez terminé votre tâche urgente, vous pouvez récupérer votre développement mis de côté avec `git stash pop`. Cela remet vos modifications dans l'état précédent.

**Cas d'utilisation :**  
Après avoir résolu une tâche urgente, vous souhaitez reprendre le travail là où vous l'avez laissé.

**Exemple :**
```bash
git stash pop
```

#### **5. git bisect**
`git bisect` est utilisé pour identifier le commit exact qui a introduit un bug en parcourant l’historique de manière binaire. C'est un outil puissant pour déboguer un projet.

**Cas d'utilisation :**  
Vous avez un bug dans votre projet, mais vous ne savez pas exactement à quel moment il est apparu. Vous pouvez utiliser `git bisect` pour trouver le commit fautif.

**Exemple :**
```bash
git bisect start
git bisect bad # Pour indiquer la version actuelle comme étant défectueuse
git bisect good v1.0 # Pour indiquer un commit ou une version connue comme étant fonctionnelle
```
Git va alors vous guider pour tester les différents commits jusqu'à trouver le mauvais.

#### **6. git revert**
La commande `git revert` permet d’annuler un commit en créant un nouveau commit qui inverse les modifications du commit problématique, tout en préservant l’historique.

**Cas d'utilisation :**  
Un commit a introduit une régression dans le projet, mais vous ne voulez pas supprimer ce commit. Vous pouvez créer un nouveau commit qui annule les changements tout en gardant la trace de l'historique.

**Exemple :**
```bash
git revert <id-du-commit>
```
Cela crée un nouveau commit qui inverse les modifications introduites par `<id-du-commit>`.

---

### Cas pratique : Exemple d'utilisation de ces commandes

Imaginons que vous travaillez sur un projet et vous suivez ces étapes :

1. Vous réalisez un commit, mais vous oubliez d’ajouter un fichier important :
    ```bash
    git add fichier-oublie.txt
    git commit --amend
    ```

2. Ensuite, vous devez intégrer votre travail dans la branche `main`, mais vous voulez un historique propre :
    ```bash
    git checkout feature-branch
    git rebase main
    ```

3. En cours de développement, une tâche urgente arrive. Vous mettez votre travail de côté :
    ```bash
    git stash
    ```

4. Après avoir fini la tâche urgente, vous récupérez votre travail mis de côté :
    ```bash
    git stash pop
    ```

5. Vous remarquez qu'un bug s'est introduit à un moment donné dans l’historique. Vous commencez une recherche binaire pour trouver le commit fautif :
    ```bash
    git bisect start
    git bisect bad
    git bisect good v1.0
    ```

6. Vous trouvez le commit problématique et décidez de l’annuler tout en gardant l'historique intact :
    ```bash
    git revert <id-du-commit>
    ```

## Structurez la collaboration grâce à GitFlow

Nous avons donc exécuté les commandes ci-dessous :

- git flow init ;
    
- git flow feature start issue5 ;
    
- git add * ;
    
- git commit -m “#5 implémentation de la fonctionnalité” ;
    
- git flow feature finish issue5 ;
    
- git flow release start 0.0.2 ;
    
- git flow release finish ‘0.0.2’.



### **Étapes de base avec GitFlow**

#### 1. **git flow init**
La commande `git flow init` initialise GitFlow dans un projet Git. Elle crée les branches de base comme `master` (ou `main`) et `develop`, et définit les conventions de nommage pour les branches de fonctionnalités, de release, etc.

**Cas d'utilisation :**  
Vous démarrez un projet et souhaitez structurer le développement de manière formelle avec GitFlow.

**Exemple :**
```bash
git flow init
```
Cela vous permet de configurer les branches principales (`develop` et `master`) et les conventions pour les branches de fonctionnalités, de release, et de hotfix.

---

#### 2. **git flow feature start issue5**
La commande `git flow feature start <nom>` démarre une nouvelle branche pour une fonctionnalité. Cela crée une branche à partir de `develop` avec un nom spécifique (généralement associé à un numéro d'issue ou de tâche).

**Cas d'utilisation :**  
Vous commencez à développer une nouvelle fonctionnalité liée à l'issue #5. Vous voulez isoler ce développement pour éviter d'affecter d'autres parties du projet.

**Exemple :**
```bash
git flow feature start issue5
```
Une branche nommée `feature/issue5` est créée, et vous pouvez commencer à développer cette fonctionnalité.

---

#### 3. **git add** et **git commit -m "message"**
Une fois que vous avez implémenté votre fonctionnalité, vous devez ajouter vos fichiers modifiés et les commettre. Cela fait partie du processus standard de Git pour enregistrer les changements.

**Cas d'utilisation :**  
Après avoir implémenté la fonctionnalité #5, vous ajoutez et commitez les fichiers.

**Exemple :**
```bash
git add *
git commit -m "#5 implémentation de la fonctionnalité"
```
Vous enregistrez vos modifications avec un message de commit décrivant le travail effectué.

---

#### 4. **git flow feature finish issue5**
Lorsque vous avez terminé le développement de la fonctionnalité, vous pouvez utiliser la commande `git flow feature finish <nom>` pour fusionner la branche de fonctionnalité dans `develop` et supprimer la branche de fonctionnalité.

**Cas d'utilisation :**  
Après avoir testé et terminé la fonctionnalité #5, vous voulez l'intégrer dans la branche `develop` pour préparer sa future intégration dans une version stable.

**Exemple :**
```bash
git flow feature finish issue5
```
Cela fusionne la branche `feature/issue5` dans `develop` et supprime la branche de fonctionnalité.

---

#### 5. **git flow release start 0.0.2**
Une fois que plusieurs fonctionnalités sont prêtes dans `develop`, vous pouvez démarrer une nouvelle version en utilisant la commande `git flow release start`. Cela crée une branche de release à partir de `develop`, où vous pouvez finaliser la préparation de la version, comme la correction des bugs ou la mise à jour de la documentation.

**Cas d'utilisation :**  
Vous avez terminé plusieurs fonctionnalités et êtes prêt à préparer la version 0.0.2 de votre projet.

**Exemple :**
```bash
git flow release start 0.0.2
```
Cela crée une branche `release/0.0.2` à partir de `develop` pour préparer la prochaine version.

---

#### 6. **git flow release finish '0.0.2'**
Une fois que tout est prêt pour la nouvelle version, la commande `git flow release finish` permet de finaliser la version. Elle fusionne la branche de release dans `master` (ou `main`), marque la version avec un tag et fusionne également les modifications dans `develop`.

**Cas d'utilisation :**  
Votre version 0.0.2 est prête à être déployée, vous la finalisez pour l'intégrer dans `master` et la taguer.

**Exemple :**
```bash
git flow release finish '0.0.2'
```
Cela fusionne la branche `release/0.0.2` dans `master`, crée un tag `0.0.2`, et fusionne les changements dans `develop` pour que tout soit à jour.

---

### Cas pratique : Utilisation de GitFlow pour gérer le développement

Imaginons que vous travaillez dans une équipe et suivez GitFlow pour structurer le développement. Voici comment le processus se déroulerait :

1. **Initialisation du projet avec GitFlow :**
   Vous commencez par initialiser GitFlow dans votre projet pour créer les branches `master` et `develop`.

    ```bash
    git flow init
    ```

2. **Création et développement d'une nouvelle fonctionnalité (issue #5) :**
   Une fois une nouvelle issue (#5) assignée à vous, vous créez une branche de fonctionnalité pour commencer à travailler dessus.

    ```bash
    git flow feature start issue5
    ```

   Vous implémentez la fonctionnalité, ajoutez vos modifications et les commitez :

    ```bash
    git add *
    git commit -m "#5 implémentation de la fonctionnalité"
    ```

3. **Finalisation de la fonctionnalité et intégration dans `develop` :**
   Une fois la fonctionnalité terminée et testée, vous la fusionnez dans `develop` pour qu'elle soit prête à être incluse dans la prochaine version.

    ```bash
    git flow feature finish issue5
    ```

4. **Préparation d'une nouvelle version (0.0.2) :**
   Après avoir terminé plusieurs fonctionnalités, vous démarrez une nouvelle release pour préparer la version 0.0.2 de votre projet.

    ```bash
    git flow release start 0.0.2
    ```

   Vous finalisez la version avec les derniers ajustements, puis vous la terminez et la déployez.

    ```bash
    git flow release finish '0.0.2'
    ```

Ce flux de travail organise clairement le développement en phases distinctes : développement de nouvelles fonctionnalités, préparation des releases, et gestion des corrections de bugs. GitFlow facilite également la collaboration en permettant aux développeurs de travailler simultanément sur différentes parties du projet sans se gêner.

### En résumé
- Les workflows Git permettent de normaliser l’utilisation de Git au sein d’une équipe ou d’un groupe de collaborateurs.
    
- Les principaux workflows sont :
    
    - le workflow centralisé ;
        
    - le workflow basé sur la création de branches de fonctionnalités ;
        
    - le workflow basé sur le tronc ;
        
    - le workflow de duplication ;
        
    - le GitFlow.
        
- GitFlow est un workflow répandu qui étend le workflow basé sur la création de branches de fonctionnalités, en normalisant les branches et les interactions entre elles.
    
- Un plugin GitFlow donne accès à des commandes facilitant la mise en œuvre de GitFlow. 
    

_Vous savez désormais mettre en place des workflows avec GitFlow, bravo ! Retrouvez-moi dans le chapitre suivant pour automatiser les traitements sur vos projets grâce aux hooks !_