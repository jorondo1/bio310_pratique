# Débuter avec R

R est un language de programmation qui permet, entre autres, de manipuler des données, effectuer des calculs et des tests statistiques, et produire des figures. Travailler avec un language de programmation plutôt qu'un tableur comme Excel comporte beaucoup d'avantages, notamment la facilité à supporter de grands jeux de données, mais surtout une énorme **flexibilité** et une **reproductibilité parfaite**. R est un programme gratuit qui le restera toujours et qui fonctionne sur toutes les plateformes comme Windows et Mac.

Pour s'y initier, il faut en apprendre la syntaxe de base et se familiariser avec des concepts particuliers, comme les *objets*, les *fonctions*, les *commandes* et les *script*. Mais avant tout, il faut l'installer !

## 1. Installer R
R est le "moteur" qui exécute le code. C'est la première chose à installer. 
1. Rendez-vous sur le site officiel du CRAN (Comprehensive R Archive Network) : https://cran.r-project.org/
2. Cliquez sur le lien correspondant à votre système d'exploitation (Windows, Mac, ou Linux).  
   **Pour Windows** : Cliquez sur "base", puis sur le gros lien de téléchargement en haut de la page ("Download R-X.X.X for Windows").  
   **Pour Mac** : Choisissez le fichier .pkg correspondant à votre processeur (Apple Silicon M1/M2/M3 ou Intel).
3. Exécutez le fichier téléchargé et suivez les instructions.

## 2. Tester la console R
Une fois installé, ouvrez R dans vos applications. La fenêtre qui s'ouvre s'appelle une console. Chaque fois qu'on y entre une commande et qu'on tape la touche _retour_, on demande à R de l'exécuter et le résultat s'affiche. Une utilisation très banale est celle d'une calculatrice. Tapez, par exemple, 
```
sqrt(9)
```
et vous obtiendrez la racine carrée (**sq**uare **r**oo**t**) de 9, soit 3. 

R est un language dit « orienté objet ». Ainsi, on travaille typiquement en sauvant des valeurs dans un objet qui porte un nom, pour pouvoir le réutiliser plus tard sans devoir recalculer cette valeur à chaque fois. Par exemple, créons l'objet valeur_A et multiplions-la par deux :
```
valeur_A = sqrt(9)
valeur_A
valeur_A*2
```
La première ligne, une fois exécutée, n'affichera aucun résultat parce qu'on a demandé à R de plutôt sauver le résultat dans un objet qu'on baptise `valeur_A` (ça aurait pu être n'importe quel autre nom). Cependant, lorsqu'on exécute seulement `valeur_A` après l'avoir créé, la valeur `3` s'affiche. Ensuite, on peut opérer sur cet objet en le multipliant, par exemple, pour obtenir `6`.

Tout cela est très rudimentaire; l'objectif est simplement de montrer ce qu'on peut faire avec R. Un autre exemple est la génération d'une valeur aléatoire, ce qui peut être très pratique en statistiques et en modélisation. Tirons une valeur aléatoire entre 0 et 1 :

```
runif(n=1, min=0, max=1)
```
Ici, `runif()` est une fonction prédéfinie dans R. Elle requiert trois arguments, soit le nombre `n` de valeurs aléatoires qu'on veut avoir, et l'étendue dans laquelle cette valeur doit être pigée (ici, entre 0 et 1 inclusivement). Il existe des centaines de fonctions prédéfinies dans R qui servent à faire toutes sortes d'opérations; la génération de nombres aléatoires n'est qu'un exemple parmi d'autres. Pour une liste d'exemples, visitez ce site web: https://sparkbyexamples.com/r-programming/r-base-functions/ (en anglais).





