# Prédiction de la gravité des accidents routiers en France - analyse de la période 2019-2022


## Contexte et objectifs

Le projet consiste à analyser des données historiques sur les accidents corporels, recueillies par les forces de l'ordre, et disponibles en [open data](https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2022/). 

Les principaux objectifs de ce projet sont de :
* **prédire le nombre d'accidentés par catégorie, par jour**,
* **prédire la gravité de l'état d'un usager impliqué dans un accident corporel en France** (indemne, blessé léger, blessé hospitalisé, décès), en fonction de caractéristiques de l'accident, du lieu, de l'usager et du contexte.

Ce projet a été développé par l'équipe suivante, durant notre [formation Data Scientist](https://datascientest.com/en/data-scientist-course) chez [DataScientest](https://datascientest.com/). : 

- Matthieu Claudel ([GitHub](https://github.com/matthieuclaudel) / [LinkedIn](http://www.linkedin.com/in/matthieu-claudel-8a927857))
- Vanessa Ibert ([GitHub](https://github.com/Vanessa-DS) / [LinkedIn](http://www.linkedin.com/in/vanessa-ibert))
- Camille Pelat ([GitHub](https://github.com/cpelat) / [LinkedIn](http://www.linkedin.com/in/camille-pelat-08a7b68a))
- Nadège Reboul ([GitHub](https://github.com/Nadege-R) / [LinkedIn](http://www.linkedin.com/in/nadege-reboul))

## Tâches réalisées
**Traitement, exploration des données**
Le jeu de données final contient **:blue[447136 entrées]** et il est composé de 35 variables **dont 30 catégorielles** (possédant jusqu'à 10 modalités différentes) et 5 variables quantitatives.
<img src="images/CarteMentale_ApresPrepro.jpg?raw=true"/>

**Entraînement, évaluation et optimisation de modèles de classification supervisés**
Des algorithmes de classification issus de différentes familles ont été analysés, à savoir :
* des algorithmes linéaires : régression logistique,
* des algorithmes de regroupement : machines à vecteurs de support (SVM), K plus proches voisins (KNN)
* des algorithmes à arbres de décision : arbre de décision, forêt aléatoire,
* des apprentissages d’ensemble : CatBoost, XGBoost
* des modèles de deep learning 

Certains modèles ont nécessité un encodage des variables catégorielles et une standardisation des variables continues.
Un travail d'optimisation a été fait sur les hyperparamètres de chacun de ces modèles et leurs performances ont alors pu être comparées. 

<img src="images/ComparaisonPerformances.png?raw=true"/>
