# Compte Rendu Projet

[Git]: https://github.com/bastienjacoud/IA_reseau_neuronnes

[Eq1]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn1.gif
[Eq2]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn2.gif
[Eq3]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn3.gif
[Eq4]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/Eqn4.gif

[Out1]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/res1.png
[Out2]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/res2.png
[Out3]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/res3.png
[Out4]: https://raw.githubusercontent.com/bastienjacoud/IA_reseau_neuronnes/master/img/res4.png

[Kohonen]: https://github.com/bastienjacoud/IA_reseau_neuronnes/blob/master/kohonen_3.py

+  Dépôt du projet : [GitHub][Git]

## Question 1 : Etude théorique du comportement de l'algorithme

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
    +  Lorsque η augmente, on remarque que l'apprentissage est beaucoup plus rapide, mais il faut qu'il reste raisonnable, sinon les neurones oublient en totalité leurs apprentisages précédents.
+  Quantitatif :
    +  Pour η = 0.005
        + X = 0.005224761871506615
    +  Pour η = 0.05
        + X = 0.004782894021075809
    +  Pour η = 0.2
        + X = 0.005402302488511184
    +  Pour η = 0.4
        + X = 0.0041503514523293155
    +  Pour η = 0.8
        + X = 0.0041503514523293155

**Largeur du voisinage σ :**
+  Situation :
    +  Tests effectués avec η = 0.05
+  Qualitatif :
    +  Plus le voisinage est large (i.e. plus σ est grand), plus l'apprentissage est rapide. On remarque de même que plus σ augmente, plus la grille est "lâche".
+  Quantitatif :
    +  Pour σ = 2.5
        +  X = 0.015154390151735983
    +  Pour σ = 2.0
        +  X = 0.008718179897472523
    +  Pour σ = 1.2
        +  X = 0.0033529229725718177
    +  Pour σ = 1.0
        +  X = 0.004033354837024771
    +  Pour σ = 0.8
        +  X = 0.002967916774870829

**Nombre de pas de temps d'apprentisage N :**
+  Situation :
    +  Tests effectués avec η = 0.05
    +  Tests effectués avec σ = 1.4
+  Qualitatif :
    +  En diminuant le nombre de pas de temps d'apprentissage, on obtient un résultat plus rapidement mais celui-ci est de moins en moins précis.
+  Quantitatif :
    +  Pour N = 3000
        +  X = 0.005105609095703494
    +  Pour N = 10000
        +  X = 0.0047450242038698555
    +  Pour N = 30000
        +  X = 0.004477690197699073
    +  Pour N = 100000
        +  X = 0.004382704076633421

**Taille de la carte :**
+  Situation :
    +  Tests effectués avec η = 0.05
    +  Tests effectués avec σ = 1.4
    +  Tests effectués avec N = 30000
+  Qualitatif :
    +  Avec une taille de carte supérieure, le programme demandera un peu plus de ressources et sera plus long mais aura une meilleure précision. Par exemple avec une carte de 15 par 15, le programme est capable de défaire les "noeuds" dans la grille, alors qu'il n'y arrive presque jamais avec une carte de taille 10 par 10. De plus si la hauteur est différente de la largeur, le résultat ne correspond pas à celui attendu car la répartition n'est plus uniforme.
+  Quantitatif :
    +  Pour une taille de 10 par 10 :
        +  X = 0.005757773265740345
    +  Pour une taille de 15 par 15 :
        +  X = 0.0017108354144597844
    +  Pour une taille de 25 par 10 :
        +  X = 0.0020157156537776695
    +  Pour une taille de 5 par 5 :
        +  X = 0.01977696710996399

**Jeu de données :**
+  Situation :
    +  Tests effectués avec η = 0.05
    +  Tests effectués avec σ = 1.4
    + Test efféctués avec une taille de 20 par 20
+  Qualitatif :
    +  L'utilisation des second et troisième jeux de données donne comme résultat une grille qui ne s'étend pas ou très peu sur les cadrants dans lesquels aucun point n'est généré.
    +  On peut voir que dans le cas du quatrième jeu de données (MNIST), nous n'avons jamais la totalité de la carte découverte. En effet, le programme, lancé deux fois d'affilées avec les mêmes paramètres donnera deux sorties différentes. Dans les résultats ci-dessous, on peut voir qu'une seule zone est visible, mais que ce n'est jamais la même.
    ![Output_1][Out1]
    ![Output_2][Out2]
    ![Output_3][Out3]
    ![Output_4][Out4]
+  Quantitatif :
    +  Avec le second jeu de données :
        +  X = 0.004512250568130622
    +  Avec le troisième jeu de données :
        +  X = 0.002604291656635881
    +  Avec le quatrième jeu de données :
        +  X = 30.37634923248643
    +  Avec le quatrième jeu de données (taille 50 par 50) :
        +  X = 28.406642023333518
