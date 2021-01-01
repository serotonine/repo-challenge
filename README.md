# THE Ultimate Hello World program

This program does exactly what it says

## 1- Corriger les typos du message du commit 03.
Le message doit être redressé comme suit: 03- Started Hello World Feature

```git
git rebase -i d9f582c
reword b219bcb 03- StArrtid Helo Volrd feature
^X y
03- Started Hello World Feature
^X y
```


## 2- Permuter l'ordre des commits 02 et 03

de manière à ce que le commit Started Hello ... apparaisse avant Finished Hello... dans l'historique.
On doit faire ici une permutation des transactions de commit et non pas juste la permutation des messages.
En effet, l'effet de l'actuelle transaction 2762d2bd doit apparaitre avant l'effet de la transaction 87da3d43
et portera le message 02- Started Hello World Feature.
La transaction 87da3d43 portera alors le message 03- Finished Hello World Feature.

```git
git rebase -i HEAD~10
copy pick ab92f64 03- Started Hello World Feature
delete pick ab92f64 03- Started Hello World Feature
paste pick ab92f64 03- Started Hello World Feature above pick d9f582c 02- Finished Hello World feature
reword 02- Finished Hello World feature
reword 03- Started Hello World Feature
^X y
02- Started Hello World Feature
^X y
03- Finished Hello World feature
^X y
git log --oneline
```

## 3- Changer l'auteur du commit 05 pour qu'il soit Me, the Challenger.

On veut cacher que Pompier était à notre secours !

```git
git rebase -i aff03fe489097b4b7ae877faf0c7f61824500e22
edit 05- debugging
^X y
git commit --amend --author="Me, the Challenger <challenger@challengeland.com>"
^X y
git rebase --continue
git log
```

## 4- Ecraser l'actuel commit numéro 06.
On ne veut pas divulguer cette opération critique dans l'historique par peur que certains curieux viendront y chercher des données sensibles.

```git
git rebase -i HEAD~10
fixup f7450ca 06- important secret
^X y
git log
```


## 5- Fusionner les 3 commits 07, 08, et 09 en un seul commit portant le message Add doc.
```git
git rebase -i HEAD~9
pick 06d3b88 07- Add doc - step 1
squash ae75c99 08- Add doc - step 2 but edit the commit message
squash afe3c44 09- Add doc - step 3ut stop for amending
^X y

# This is a combination of 3 commits.
# This is the 1st commit message:

07- Add doc

# This is the commit message #1:

# 08- Add doc - step 2

# This is the commit message #2:

# 09- Add doc - step 3

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
^X y
```

## 6- Faire en sorte que le commit 11 soit une continuité du commit 10 et qu'il en conserve le message.

```git
git rebase -i HEAD~3
fixup 5ec2c1b 11- I forgot a semicolon
^X y
git log
```

## 7- Renuméroter les commits dans l'ordre
```git
git rebase -i HEAD~5
r 2b84e76 07- Add doc
r 2bd8f17 10- Test for feature hello world
^X y
06- Add doc
^X y
07- Test for feature hello world
^X y
git log --oneline
0842d27 (HEAD -> master) 07- Test for feature hello world
791103e 06- Add doc
ba66116 05- debugging
aff03fe 04- Really made the thingy done
d9f582c 03- Finished Hello World feature
ab92f64 02- Started Hello World Feature
4727b96 01- Initial commit
```
## 7- Créer repo git hub + push repo-challenge + update README.md

```git
 git remote add origin https://github.com/serotonine/repo-challenge.git

```
