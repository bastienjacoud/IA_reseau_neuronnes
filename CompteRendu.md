# Compte Rendu Projet

[Git]: https://github.com/bastienjacoud/IA_reseau_neuronnes

[Eq1]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn1.gif
[Eq2]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn2.gif
[Eq3]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn3.gif
[Eq4]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn4.gif

[Kohonen]: https://github.com/bastienjacoud/IA_reseau_neuronnes/blob/master/kohonen_3.py

+  Dépôt du projet : [GitHub][Git]

## Question 1 : Étude théorique du comportement de l'algorithme

**Quelle sera la prochaine valeur du poids du neurone gagnant dans le cas où η=0 ?**

+ On applique la formule ![Equation][Eq1] avec η=0, on trouve ainsi que la différence de poids sera toujours nulle, donc le poids restera le même pour tous les neurones, donc pour le neurone gagnant à fortiori.

**Quelle sera la prochaine valeur du poids du neurone gagnant dans le cas où η=1 ?**

+  On applique à nouveau la formule ![Equation][Eq1] mais on fixe η=1, on trouve ainsi ![Equation][Eq2] et on en déduit que la prochaine valeur du poids du neurone gagnant sera égale à la valeur de son prototype à l'itération actuelle.

**En déduire géométriquement la prochaine valeur du poids dans le cas normal η∈]0,1[.**

+  Dans le cas normal, la nouvelle valeur du poids du neuronne sera comprise entre sa valeur actuelle et la valeur de son prototype.

**Si σ augmente, est ce que les neurones vont plus ou moins apprendre l'entrée courante ?**

+  Si σ augmente, la différence augmente, donc l'entrée courante aura plus d'impact sur les neurones. En d'autres termes, plus σ augmente, plus les neurones apprennent l'entrée courante.

**En déduire l'influence que doit avoir σ sur la "grille" de neurones, sera-t-elle plus "lâche" ou plus "serrée" si σ augmente ?**

+  Les différences seront plus grandes, la "grille" de neurones sera donc plus "lâche".

**Prenons le cas d’une carte avec un seul neurone qui rȩcoit 2 entrées x1 et x2. Durant l’apprentissage x1 (respectivement x2) est présenté n1 (respectivement n2) fois. Après l’apprentissage où se situera géométriquement le poids du neurone ?**

+ Il y a un unique neurone, on peut donc appliquer la formule en ayant ![Equation][Eq4], ainsi on trouve, après avoir appliqué l'entrée x1 n1 fois et l'entrée x2 n2 fois, ![Equation][Eq3].

## Question 2 : Implémentation de l'algorithme

+  Algorithme implémenté dans le script [Kohonen][kohonen].

## Question 3 : Étude pratique du comportement de l'algorithme

**Taux d'apprentissage η :**

+  Qualitatif : 
    +  Lorsque η augmente, on remarque que l'apprentissage est beaucoup plus rapide.
+  Quantitatif :
    +  Pour η = 0.05
        + X = 0.004782894021075809
    +  Pour η = 0.2
        + X = 0.005402302488511184
    +  Pour η = 0.8
        + X = 

**Largeur du voisinage σ :**

+  Qualitatif :
    +  Plus le voisinage est large (i.e. plus σ est grand), plus l'apprentissage est rapide
+  Quantitatif :
    +  TODO

**Nombre de pas de temps d'apprentisage N :**

+  Qualitatif :
    +  TODO
+  Quantitatif :
    +  TODO

**Taille de la carte :**

+  Qualitatif :
    +  TODO
+  Quantitatif :
    +  TODO

**Jeu de données :**

+  Qualitatif :
    +  TODO
+  Quantitatif :
    +  TODO

**Topologie de la carte : *(Bonus)***

+  Qualitatif :
    +  TODO
+  Quantitatif :
    +  TODO
    
## Question 4 : *Bonus*

**Comment ce type de réseau pourrait-il être utilisé pour faire de la classification/reconnaissance de chiffres ?**