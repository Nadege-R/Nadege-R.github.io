# Prédiction de la gravité des accidents routiers en France - analyse de la période 2019-2022


## Contexte et objectifs

Le projet consiste à analyser des données historiques sur les accidents corporels, recueillies par les forces de l'ordre, et disponibles en [open data](https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2022/). 

Le principal objectif de ce projet sont de **prédire la gravité de l'état d'un usager impliqué dans un accident corporel en France** (indemne, blessé léger, blessé hospitalisé, décès), en fonction de caractéristiques de l'accident, du lieu, de l'usager et du contexte.

Ce projet a été développé par l'équipe suivante, durant notre [formation Data Scientist](https://datascientest.com/en/data-scientist-course) chez [DataScientest](https://datascientest.com/). : Matthieu Claudel ([GitHub](https://github.com/matthieuclaudel) / [LinkedIn](http://www.linkedin.com/in/matthieu-claudel-8a927857)), Vanessa Ibert ([GitHub](https://github.com/Vanessa-DS) / [LinkedIn](http://www.linkedin.com/in/vanessa-ibert)), Camille Pelat ([GitHub](https://github.com/cpelat) / [LinkedIn](http://www.linkedin.com/in/camille-pelat-08a7b68a)), Nadège Reboul ([GitHub](https://github.com/Nadege-R) / [LinkedIn](http://www.linkedin.com/in/nadege-reboul))

## Actions réalisées
**Exploration des données** 
Des disparités socio-démographiques et territoriales persistantes :
* 👨 Hommes : 77,6% des décès  
* 👨‍🎓 18-24 ans : 91 tués par million d'habitants (vs 48 en moyenne)  
* 🌎 Outre-mer vs métropole : 91 tués par million d'habitants sur 2019-2023 (vs 46 en métropole)  
et... selon le mode de transport, la météo, le mois de l'année, le type de route etc...  
<p float="left">
  <img src="images/gravite/Camembert_region.png" height="200" />
  <img src="images/gravite/Deces_Dpt.png" height="200" /> 
  <img src="images/gravite/Mortalite_hommes_femmes_age.png" height="200" />
</p>

**Traitement des données**
Après gestion des valeurs manquantes, doublons, sélection/création de variables, le jeu de données final contient **447136 entrées** et il est composé de 35 variables dont 30 catégorielles (possédant jusqu'à 10 modalités différentes) et 5 variables quantitatives.
<img src="images/gravite/CarteMentale_ApresPrepro.jpeg?raw=true"/>

**Entraînement, évaluation et optimisation de modèles de classification supervisés**  
Des algorithmes de classification issus de différentes familles ont été analysés, à savoir :
* des algorithmes linéaires : régression logistique,
* des algorithmes de regroupement : machines à vecteurs de support (SVM), K plus proches voisins (KNN)
* des algorithmes à arbres de décision : arbre de décision, forêt aléatoire,
* des apprentissages d’ensemble : CatBoost, XGBoost
* des modèles de deep learning 

Certains modèles ont nécessité un encodage des variables catégorielles et une standardisation des variables continues.  
Un travail d'optimisation a été fait sur les hyperparamètres de chacun de ces modèles et leurs performances ont alors pu être comparées.  

<img src="images/gravite/ComparaisonPerformances.png?raw=true"/>

Le meilleur modèle est celui de type **Random Forest**, avec les paramètres {'bootstrap': True, 'class_weight': 'balanced', 'criterion': 'entropy', 'max_depth': 13, 'min_samples_leaf': 1, 'min_samples_split': 2, 'n_estimators': 100}, conduisant aux performances suivantes :  
<img src="images/gravite/RF_classifreport.jpg?raw=true" width="200"/>


**Interprétabilité des résultats**  
L'analyse des valeurs de Shap, classées ci-dessous par ordre d'importance pour chaque catégorie d'usagers, permet d'identifier les variables les plus influentes et la façon dont elles influent sur le résultat.  
<img src="images/gravite/SHAP_Rf.jpg?raw=true"/>

## Conclusion
Ainsi, un modèle a été proposé pour prédire l'état de gravité d'une personne accidentée, dont les performances sont jugées honorables. 
il apparaît par exemple ici que le fait de rouler hors agglomération, de ne pas porter de ceinture de sécurité et d'heurter un obstacle fixe sont des critères qui influencent positivement le fait de décéder dans l'accident. 

Pour retrouver tous les détails de ce projet, rendez-vous sur le  [repo GitHub](https://github.com/Nadege-R/Gravite-des-accidents-routiers) qui vous donnera également la possibilité, en lançant l'application streamlit, de visualiser les résultats des modèles, en fonction des variables que vous aurez choisies.
<img src="images/gravite/Modeles_gravite.png?raw=true"/>