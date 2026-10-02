# Tp2

## Git status

### 1.

Message de git status quand rien n'est afficher
```bash
PS D:\GitHub\tp-02-zones-git\inventaire> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        starter/

nothing added to commit but untracked files present (use "git add" to track)
PS D:\GitHub\tp-02-zones-git\inventaire> 
```

Message de ls -a .git 
````bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ ls -a .git
./  ../  config  description  HEAD  hooks/  info/  objects/  refs/
````

### 2.
Avec add README.md je pense que le git status vas renvoyer :   

New :Readme.md  
Untracked files : les autre fichier

Résultat:
````bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status`

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/

````
Prévision réussi!

Prévision :
Modifier le readme.md je pense qu'il vas ajouter une sectin modified avce README.ld à l'intérieur:

New : Readme.md  
Untracked files : les autre fichier
modified : README.md

Résultat:
````bash
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/
````

Prévision réussi!

Prévision:
Si on créer un commit il vas enlever la section new: README et laisser le reste 

Résultat:
````bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/

no changes added to commit (use "git add" and/or "git commit -a")
````
Prévision reussi!

Prévision:
Si on ajoute a nouveau le README.md et que l'on commit je pense qu'il vas rester que le untracked

Résultat:
````bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/

nothing added to commit but untracked files present (use "git add" to track)
````

Prévision reussi!

### 3.

Résultat du git status -s :
`````bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status -s
MM README.md
A  pom.xml
?? journal.md
?? src/
`````

le MM du fichier README veut dire pour le premier M qu'on a modifier un fichier déja commit et le deuxième M signifie qu'on as modifier le fichier déjà indexé

Pour le A de pom.xml cela signifie qu'on ajoute un nouveau fichier jamais ajouté.

### 4.
la commande est git restore --staged <Nom du fichier>

le fichier retourne dans Untracked ou modfied si le fichier à déjà été commit.

# Tp3

## Historique Git

### 3.

Voici ce qu'il se passe quand on fait git add -f <nom du fichier qui est dans git ignore>

 ````bash
 Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   build/sortie.bin

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        enonce.md
 ````

On voit que le gitignore empeche d'ajouter les programme non voulue mais si on force le add on peut quand meme les indexés

### 4.

Résultat du git statut après avoir ajouter un fichier .gitkeep pour indexé le dossier non vide "logs" car git ne prend pas en compte les dossier vides

```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   logs/.gitkeep

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   journal.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        enonce.md


```

### 5.

Résultat du git ls-files --eol script.sh :
```
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git ls-files --eol script.sh
i/lf    w/lf    attr/text eol=lf        script.sh
```

### 7.

Avant la modification du commit 
```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git log --oneline
34b39b4 (HEAD -> master) Suppresion d'un article
2b26059 Ajout de plusieur  article
9317e8e Ajout d'un article
b1442be ajout d'un script
f0b6d7e tp1 & tp2
82db163 Complète le README
8f66946 Ajoute le README.
``` 
Apres la modification du commit

```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git log --oneline
89e7a7d (HEAD -> master) Suppressino d'un article vendu
2b26059 Ajout de plusieur  article
9317e8e Ajout d'un article
b1442be ajout d'un script
f0b6d7e tp1 & tp2
82db163 Complète le README
8f66946 Ajoute le README.
```

### 9.

Le git status de départ 
```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    doc/brouillon.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   journal.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        enonce.md
```

pour bien suppimer doc/brouillon.md il faut faire un add du fichier supprimé et un commit.

voila apres un commit

```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   journal.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        enonce.md

no changes added to commit (use "git add" and/or "git commit -a")

```

### 10.


la différence entres le git rm et juste supprimer la fichier depuis l'explorateur c'est qu'il index le fichier supprimer et qu'il reste plus que un commit pour bien suppimer.

### 11.

Pour supprimer le suivie d'un fichier il faut faire git rm --cached build/sortie.bin voici ce qu'ilse passe dans le git status il faut donc commit juste après

```bash 
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    build/sortie.bin

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    doc/notes.md
        modified:   journal.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        enonce.md
```


### 12.

Quand on fait git mv src/App.java src/Inventaire.java git prend en compte cette commande comme un renommage

```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git status -s
 D doc/notes.md
 M journal.md
R  src/App.java -> src/Inventaire.java
?? .gitignore
?? enonce.md
```

### 13.

Résultat du premier git diff avec un fichier non indexé
```bash
$ git diff src/Inventaire.java
warning: in the working copy of 'src/Inventaire.java', LF will be replaced by CRLF the next time Git touches it
diff --git a/src/Inventaire.java b/src/Inventaire.java
index abd9881..5098701 100644
--- a/src/Inventaire.java
+++ b/src/Inventaire.java
@@ -2,6 +2,6 @@ public class App {
 
   public static void main(String[] args) {
     System.out.println("Inventaire : 0 article");
-     System.out.println("Inventaire : 5 article");
+     System.out.println("Inventaire : 7 article");
   }
 }
```

Résultat du git diff avec indexions 
```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git diff src/Inventaire.java

```
On voit bien que rien en se passe alors que avec it diff --staged

```bash
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git diff --staged
diff --git a/src/App.java b/src/Inventaire.java
similarity index 70%
rename from src/App.java
rename to src/Inventaire.java
index abd9881..5098701 100644
--- a/src/App.java
+++ b/src/Inventaire.java
@@ -2,6 +2,6 @@ public class App {
 
   public static void main(String[] args) {
     System.out.println("Inventaire : 0 article");
-     System.out.println("Inventaire : 5 article");
+     System.out.println("Inventaire : 7 article");
   }
}
```
### 16.

| Je veux annuler... | Commande | Ce que je perds |
| :--- | :--- | :--- |
| **une modification non indexée** | `git restore <fichier>` | La modification locale |
| **une indexation** | `git restore --staged <fichier>` | Rien (la modification est conservée en local) |
| **le message du dernier commit** | `git commit --amend` | L'ancien message de commit |


### 19.
Résultat de la commande git lg

```bash 
Ethan@DESKTOP-N7IV693 MINGW64 /d/GitHub/tp-02-zones-git/inventaire (master)
$ git lg
* 40317bc (HEAD -> master) supprission de suivie
* e4cc07f ajout du teste
* 309642a test
* 7e736f7 Supprimer doc/brouillon.md
* 4621325 Bonjour
* 89e7a7d Suppressino d'un article vendu
* 2b26059 Ajout de plusieur  article
* 9317e8e Ajout d'un article
* b1442be ajout d'un script
* f0b6d7e tp1 & tp2
* 82db163 Complète le README
* 8f66946 Ajoute le README.
```