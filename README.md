# THE Ultimate Hello World program

This program does exactly what it says

## 1- Corriger les typos du message du commit 03.
Le message doit être redressé comme suit: 03- Started Hello World Feature

```git
git rebase
```


## 2- Permuter l'ordre des commits 02 et 03

de manière à ce que le commit Started Hello ... apparaisse avant Finished Hello... dans l'historique.
On doit faire ici une permutation des transactions de commit et non pas juste la permutation des messages.
En effet, l'effet de l'actuelle transaction 2762d2bd doit apparaitre avant l'effet de la transaction 87da3d43
et portera le message 02- Started Hello World Feature.
La transaction 87da3d43 portera alors le message 03- Finished Hello World Feature.

## 3- Changer l'auteur du commit 05 pour qui'il soit Me, the Challenger.

On veut cacher que Pompier était à notre secours !

```git
git rebase -i 22d2e29c6c3cdec435a686a4f84a29a7bdd8e432
edit 823cb9e 05- debugging
28585  2020-12-31 13:22:59 git commit --amend --author="Me, the Challenger <challenger@challengeland.com>"
```

## 4- Ecraser l'actuel commit numéro 06.
```git
git rebase -i 22d2e29c6c3cdec435a686a4f84a29a7bdd8e432
edit 823cb9e 05- debugging
```


## 5- Fusionner les 3 commits 07, 08, et 09 en un seul commit portant le message Add doc.

## 6- Faire en sorte que le commit 11 soit une continuité du commit 10 et qu'il en conserve le message.