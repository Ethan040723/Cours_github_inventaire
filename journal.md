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