# Débuter avec R

R est un language de programmation qui permet, entre autres, de manipuler des données, effectuer des calculs et des tests statistiques, et produire des figures. Travailler avec un language de programmation plutôt qu'un tableur comme Excel comporte beaucoup d'avantages, notamment la facilité à supporter de grands jeux de données, mais surtout une énorme **flexibilité** et une **reproductibilité parfaite**. R est un programme gratuit qui le restera toujours et qui fonctionne sur toutes les plateformes comme Windows et Mac.

Pour s'y initier, il faut en apprendre la syntaxe de base et se familiariser avec des concepts particuliers, comme les *objets*, les *fonctions*, les *commandes* et les *script*. Mais avant tout, il faut l'installer !

## 1. Installer R
R est le "moteur" qui exécutera les calculs. C'est la première application à installer. 
1. Rendez-vous sur le site officiel du CRAN (Comprehensive R Archive Network) : https://cran.r-project.org/
2. Cliquez sur le lien correspondant à votre système d'exploitation (Windows, Mac, ou Linux).  
   **Pour Windows** : Cliquez sur `base`, puis sur le gros lien de téléchargement en haut de la page (`Download R-X.X.X for Windows`).  
   **Pour Mac** : Choisissez le fichier `.pkg` correspondant à votre processeur (Apple Silicon M1/M2/M3 ou Intel).
   * Note : •	Si vous ne savez pas quel type de processeur vous avez, lire ceci : [https://support.apple.com/fr-ca/116943](https://support.apple.com/fr-ca/116943)
4. Exécutez le fichier téléchargé et suivez les instructions.

## 2. Tester la console R
Une fois installé, ouvrez R dans vos applications. La fenêtre qui s'ouvre s'appelle une console. Chaque fois qu'on y écrit une commande et qu'on tape la touche _retour_, on demande à R de l'exécuter et le résultat s'affiche. Une utilisation très banale est celle d'une calculatrice. Tapez, par exemple, 
```
sqrt(9)
```
et vous obtiendrez la racine carrée (**sq**uare **r**oo**t**) de 9, soit 3. 

R est un language dit « orienté objet ». Ainsi, on travaille typiquement en sauvant des valeurs dans un objet qui porte un nom, pour pouvoir le réutiliser plus tard sans devoir recalculer cette valeur à chaque fois. Par exemple, créons l'objet `valeur_A` et multiplions-la par deux :
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
Ici, `runif()` est une fonction prédéfinie dans R. Elle requiert trois arguments, soit le nombre `n` de valeurs aléatoires qu'on veut avoir, et l'étendue dans laquelle cette valeur doit être pigée (ici, entre 0 et 1 inclusivement). Amusez-vous à changer ces arguments pour modifier le comportement de la fonction.

Il existe des centaines de fonctions prédéfinies dans R qui servent à faire toutes sortes d'opérations; la génération de nombres aléatoires n'est qu'un exemple parmi d'autres. Pour une liste d'exemples, visitez ce [site web](https://sparkbyexamples.com/r-programming/r-base-functions/) (en anglais).

## 3. Installer RStudio

Si R est le moteur, RStudio est le tableau de bord, le volant et les pédales. C'est une interface de développement intégrée (IDE) qui rend l'utilisation de R beaucoup plus simple et intuitive. Elle permet de: 
- Écrire un script, soit une liste de commandes à exécuter séquentiellement, et de le sauvegarder ;
- Voir les objets créés par l'utilisateur et visualiser leur contenu (e.g. des bases de données, des vecteurs, des figures)
- Accéder facilement au manuel d'utilisation de n'importe quelle fonction pour comprendre comment elle fonctionne

Pour l'installer, [rendez-vous sur ce lien](https://posit.co/download/rstudio-desktop/). Le site devrait détecter automatiquement votre système d'exploitation et vous proposer le bon fichier à télécharger. Cliquez sur le bouton de téléchargement pour la version gratuite ("RStudio Desktop"), puis exécutez le fichier téléchargé et suivez les instructions.

## 4. Créer un premier projet sur RStudio
Il est bonne pratique de travailler en mode « projet » sur RStudio.

1. Ouvrez l'application RStudio.
2. Allez dans le menu **File** et cliquez sur **New Project...**
3. Choisissez **New Directory**
4. Ensuite, choisissez **New Project**.
5. Dans le champ _Directory name_, donnez un nom à votre projet, par exemple _BIO310_projet_
6. Cliquez sur **Browse...** pour choisir où ce nouveau dossier sera créé sur votre ordinateur (je recommande fortement d'avoir un dossier BIO310 où centraliser tous vos travaux pour le cours)
7. Cliquez sur **Create Project**.

Ainsi, un dossier aura été créé dans votre ordinateur, lequel contiendra un fichier terminant en .Rproj. Dorénavant, pour utiliser RStudio pour ce cours, vous n'avez qu'à ouvrir ce fichier et RStudio sera lancé.

## 5. Créer un premier script R
Un script est essentiellement un petit programme, soit une suite d'instructions à exécuter séquentiellement. Par exemple, un script pourrait contenir une série de commandes permettant de :
1. Importer des données brutes
2. Extraire un sous-ensemble de ces données
3. Produire une figure permettant de visualiser ces données
4. Tester une hypothèse à l'aide d'un test statistique appliqué à ces données
5. Exporter les résultats du test sous forme de fichier texte et la figure sous forme d'image.

Le language R est capable de faire chacune de ces étapes. Pour y arriver, on doit apprendre à utiliser toutes sortes de fonctions pour manipuler nos données, ce que nous pratiquerons dans le cours. RStudio nous permet de construire un tel programme – un script – de manière interactive en vérifiant que chaque fonction R produise bel et bien ce qu'on attend d'elle. Cela permet de facilement trouver nos erreurs et de produire un programme qui s'exécute du début à la fin.

Créons un premier script très simpliste, qui servira à calculer la concentration finale suite à une dilution :  
1. Allez dans le menu **File** et cliquez sur **R Script**. Un nouveau fichier ouvrira dans le panneau supérieur gauche.
2. Allez dans le menu **File** et cliquez sur **Save as...** pour enregistrer ce fichier dans votre dossier de travail
3. Inscrivez-y les fonctions ci-bas et sauvegardez votre script. Je vous encourage fortement à écrire le tout vous-même plutôt qu'à copier coller, l'objectif étant de vous rendre autonome en vous laissant faire vos erreurs. À chaque ligne, vous pouvez utiliser le raccourci-clavier ctrl+Enter (ou cmd+Enter pour Mac) pour exécuter une ligne en isolation et vous assurer qu'elle ne produise pas d'erreur. Le bouton Run en haut à droite du script fait la même chose.
```
C1 <- 100
V1 <- 50          
V2 <- 500           
C2 <- (C1 * V1) / V2
C2_arrondi <- round(C2, digits = 2)
message(paste("Concentration finale calculée:", C2_arrondi, "uM"))
```
- La fonction `round()` sert à arrondir une valeur numérique; l'argument `digits =` spécifie combien décimales conserver.
- La fonction `message()` sert à imprimer du texte dans la console R.
- La fonction `paste()` sert à coller ensemble différents morceaux de texte et peut évaluer la valeur d'un objet, par exemple celle de C2.

4. Finalement, cliquez sur le bouton "Source" en haut à droite de la fenêtre du script pour exécuter ce script en entier. 

Ici, chaque commande a été exécutée séquentiellement (de haut en bas) en respectant la priorité des parenthèses lorsqu'il y en a plusieurs, comme dans une équation mathématique. La dernière commande sert spécifiquement à imprimer du texte dans la console, ce qu'on observe quand on clique Source.

# Déposez une capture d'écran sur Moodle
Pour me montrer que vous avez complété cet exercice et que RStudio est bien installé, prenez une capture d'écran où l'on voit bien ce script et sa sortie dans la console. Déposez cette capture d'écran sur Moodle avant la première séance du cours, soit au plus tard à 10h00 AM le mardi 16 septembre 2025.

