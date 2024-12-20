# Analyse de données d'émission acoustique pour la détection de défauts évolutifs dans des matériaux ou structures de génie civil

**Outils utilisés** Matlab, R  
**Laboratoire d'affectation pour cette étude** LMC2 (Laboratoire des Matériaux Composites pour la Construction, Université Claude Bernard Lyon 1) 

## Contexte et objectifs
Lorsqu'un matériau est soumis à une contrainte (thermique, mécanique...), un défaut interne peut se développer. Il va alors libérer de l’énergie sous forme d’ondes élastiques transitoires, aussi appelées **émissions acoustiques**. Ces ondes (ou signaux) sont détectées par des capteurs piézoélectriques placés à la surface du matériau. Les capteurs les transforment en signaux électriques, qui peuvent ensuite être amplifiés.
Les émissions acoustiques sont générées par divers défauts - fissuration, rupture de fibres, corrosion - et il est supposé que les signaux portent la signature acoustique du mécanisme d'endommagement les ayant généré. L'objectif est alors de trouver les caractéristiques de ces signaux et de procéder à une **segmentation des signaux** pour **distinguer les différents mécanismes d'endommagement et suivre leur évolution au cours de la sollicitation**. La technique de l'émission acoustique sert donc à **établir un diagnostic de l'état de santé du matériau**.

Le présent projet consiste à utiliser cette méthode pour suivre l'endommagement d'un composite, constitué d'une matrice cimentaire et d'un renfort textile (ici, en carbone). Ce type de composite est utilisé pour le renforcement ou la réparation des maçonneries, afin de prolonger la durée de vie ou augmenter la capacité portante de ces structures.  

## Actions réalisées
**Confection des composites TRC, instrumentation et essais de traction**  
**Analyse des signaux temporels recueillis**  
Décomposition modale empirique de chaque signal, extraction de la composante de plus forte énergie, et calcul des descripteurs (variables quantitatives) temporels et fréquentiels  
**Analyse en Composantes Principales et clustering par l'algorithme des K-means**  
Une ACP permet de projeter les variables dans un espace où la séparation par clustering sera facilitée. L'algorithme des K-moyennes est utilisé pour cette segmentation et les indicateurs Silhouette et de Davies et Bouldin sont calculés pour déterminer le nombre de clusters (K)optimal.  
**Interprétation des clusters obtenus**  
Les clusters sont reliés aux mécanismes d'endommagement connus des composites à matrice cimentaire, à savoir la fissuration de la matrice, la dégradation de l'interface entre les fibres et la matrice, et la rupture de fibres textiles.  
**Lien entre données acoustiques et comportement mécanique du TRC**  
En étudiant ces dommages, il est possible de relier les données acoustiques au comportement global du matériau. Par exemple, la dégradation entre les fibres et la matrice influe sur la capacité du matériau à transférer les efforts mécaniques, ce qui provoque l'ouverture des fissures. Grâce à certaines variables extraites des signaux (notamment l'amplitude), on peut même estimer cette ouverture.

## Communication et publication sur ces travaux
Ces travaux ont fait l'objet d'une [communication](/pdf/RUGC2021-ReboulSaidiGabor.pdf) lors des Rencontres Universitaires de Génie Civil (RUGC, 2021), et d'une [publication](https://doi.org/10.1016/j.conbuildmat.2021.125216) dans le journal *Construction and Building Materials*.

## Travaux connexes
Dans le cadre de sa thèse, dirigée par Emmanuel Ferrier et Laurent Michel, Antoine Chalot a analysé expérimentalement l'efficacité d'un renforcement de liaison béton armé (poteaux poutres et dalles voiles) par des composites à matrice polymère et à fibres de carbone. Avec Cécile Grazide et Nathalie Roy, nous avons profité des analyses expérimentales menées dans ce cadre pour effectuer un monitoring de ces structures par émission acoustique, dont les résultats ont été publiés dans [Construction and Building Materials](https://doi.org/10.1016/j.conbuildmat.2020.119661)  





