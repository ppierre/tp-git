# Suivre les consignes de ce document

Faire les modifications indiquées directement dans ce même document en suivant les indications.

## Faire un fork de ce dépôt

Depuis la page Github de ce dépôt, faire un fork de ce même dépôt.

Puis cloner votre fork sur votre PC (avec VSCode).
- `Shift+CMD+P` _Git clone_ Puis _Cloner à partir de Github_ Puis choisir son fork de `tp-git`

- [ ] Cochez cette checkbox en plaçant un "**X**" entre les deux `[ ]` en début de ligne.
- Faire un commit avec le message "test commit et push"
- Faire un push du commit sur Github.

## Principe du TP

- [X] Cochez les checkbox quand demandé et/ou répondez directement dans ce document.
- Suivre les indications sur les commits et autres manipulation.

L'historique git de vos commits sera la preuve que vous avez fait le TP.

# Gitignore

Le fichier `.gitignore` sert à indiquer à Git les fichiers qu'il doit ignorer (c-à-d qu'il ne gardera pas l'historique de leurs modifications).

## génération automatique du fichier `.gitignore`

- Installez l'extension _".gitignore Generator"_ .
- L'utiliser (`Shift+CMD+P` Generate .gitignore File).
  - Faire un fichier `.gitignore` en sélectionnant :
    - [X] windows
    - [X] macos
    - [X] visualstudiocode
- [ ] cocher et faire commit "ajout .gitignore"

## ajout manuel à `.gitignore`

- Faire un fichier `/public/video/a-ignorer.txt`
- Ajouter en fin de fichier `.gitignore` la ligne suivante :
  - `/public/video`
- [ ] cocher et commit "ajout dossier à .gitignore"
- Synchroniser les commit avec Github
  - constater que le fichier `/public/video/a-ignorer.txt` n'a pas été publié sur Github

# Conflits

- [ ] Depuis le site Github (le dépôt "distant"), utiliser le bouton éditer ✏ pour cocher cette case. Avec "édit depuis Github", comme message de commit.
- [ ] Cochez cette case depuis VSCode (le dépôt sur votre PC). Faire un commit "édit local"
- Demandez à VSCode de synchroniser.
  - Cela doit échouer.
  - Faire `Shift+CMD+P` Git: Pull (rebase)
    - Dans ce cas faire "accept both change" et éditer pour garder les deux cases cochées.
    - Valider le changement du commit
    - Finir "rebase".
- Faire un "push" vers Github.

# Branches

## Faire une branche

- Faire une branche en cliquant en bas-à-gauche sur VSCode ; la nommer (en adaptant) _"votre-pseudo/test-branche"_
  - VSCode vous place automatiquement dans la nouvelle branche.
- [ ] Cochez et commit : "1re commit dans branche"
- [ ] Puis cochez et commit "2nd commit dans branche"
- Regardez la liste des commits dans le volet Chronologie en bas de explorateur de VSCode

## Changer de branche

- Retourner à la branche _"master"_ avec le bouton en bas à droite
  - Regardez les deux checkboxs au dessus, elle ne son pas cochées (**important:** les laissez ainsi) .
  - [ ] Cochez et commit : "commit dans master à rebaser dans branche"
- Regardez la liste des commits
  - Vous ne voyez pas les commits fait dans la branche
- Retourner à la branche  _"????/test-branche"_

## "Rebaser" une branche

- Utiliser la commande `Shift+CMD+P` _Git: rebaser la branche_
  - Choisir la branche "Master"
    - Si Conflit :
      - Accepter la version courante dans l'éditeur
      - Valider la résolution de conflit dans le volet "Changements rebase" du panneau "Contrôle de code source"

## "Merger" une branche

- Retourner à la branche "Master"
- Faire la commande `Shift+CMD+P` _Git: Merge Branch_
  - Sélectionner la branche _"????/test-branche"_
- Regardez la liste des commits
  - Vous voyez les commits fait dans la branche !
    - Et plus haut dans ce document les checkbox correspondantes sont cochées
- Poussez les commits vers Github

# "Amend", Réordonner et "squash" les commits.

Pour ces étapes on va utiliser Github Destop.

- Lancer Github Desktop et ouvrir la copie locale de ce dépôt avec Github Desktop en le faisant glisser sur son panneau d'accueil.
 - Sélectionner la branche _"????/test-branche"_
  - On peut modifier l'historique des commits tant qu'ils n'ont pas été "poussés" vers le dépôt central (_origin_).
  - Modifier l'historique des commits déjà publiés peut causer de gros problèmes. Donc faire ses travaux dans une branche est plus sûr.

Documentation "[amend]" et autres manipulations...

[amend]: https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/managing-commits/amending-a-commit "GitHub Desktop/Amending a commit"

## Consignes

Décrire ce que vous faites en éditant ce document sur le modèle des indications que j'ai données avant.

Exemple :

## A vous de faire

- Plusieurs commits
- "amend" du derniers commit
- Réordonnez des commits
- "squash" des commits ensembles

**Editez ici**

# Remonter dans le temps pour trouver un "bug"

- [X] décochez cette case et commit : "le bug"
- _message à modifier plus tard_
-
-
-
-
- [ ] cochez et commit : "après bug 1"
- [ ] cochez et commit : "après bug 2"
- [ ] cochez et commit : "après bug 3"

- Dans le terminal répéter la commande :
  - `git checkout head~1`
  - Jusqu'à ce que la case du "bug" soit de nouveau cochée (c-à-d remonter jusqu'avant le commit du bug)
  - Ne jamais changer le code quand on utilise "checkout" ainsi.
- Faire une branche "correction-bug", pour pouvoir changer et tester le code sans risque.
  - Remplacer le _message à modifier_ plus haut par : **Bug corrigé**
  - Faire un commit : "Bug corrigé"
  - En vrais, on testerait maintenant si notre code est "sans bug".
- Faire un [cherry pick] de ce commit vers la branche "master".
  - Résoudre le conflit en prenant "incoming change" (le bug corrigé) dans VSCode.

[cherry pick]: https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/managing-commits/cherry-picking-a-commit


# Mettre des changements de coté (_stash_)

Certaines actions ne peuvent être faite s'il existe des changements "non commités".

- [ ] cochez cette case **sans faire de commit !**
- Essayez de changez de branche :
  - Vous ne pouvez pas
  - Choisir _"Faire un stash et extraire"_
  - **Ou bien** dans le terminal : `git stash`
    - Suivit du changement de branche
  - [ ] cochez et commit "Dans branche"
- Retourner à la branche "master"
- Faire `Shift+CMD+P` _Git: Pop latest stash_
  - *Ou bien* dans le terminal : `git stash pop`

Vous devez retrouvez votre changement non commité : faire le commit "test stash"

# Preuve que vous avez bien fait le travail demandé :

- Dans le terminal :
  - `git reflog show > reflog.txt`
- Faire un commit 'ajout copie du reflog"

Noter ici l'URL de votre fork : 
https://github.com/?????/tp-git
 
# Archive d'un dépôt

Archive d'un dépôt local : [git archive](https://git-scm.com/docs/git-archive).

- Faire l'archive de ce dépôt et la rendre sur Mooodle.
  - `git archive -o tp-git.zip HEAD`
  - Supprimez l'archive après l'avoir rendue (inutile de la garder sur votre ordinateur).
