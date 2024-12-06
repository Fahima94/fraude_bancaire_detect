# CAHIER DES CHARGES

## Contexte du Projet
L'Organisation nationale de lutte contre le faux-monnayage (ONCFM) est une organisation publique visant à mettre en place des méthodes d’identification des contrefaçons de billets en euros.  
Dans ce cadre, notre objectif est de développer un algorithme capable de différencier automatiquement les vrais billets des faux.

## Objectifs
Lorsqu’un billet est analysé, une machine consigne ses caractéristiques géométriques.  
Au fil des années, des différences de dimensions entre vrais et faux billets ont été constatées.  
Ces variations, bien que difficiles à détecter à l’œil nu, peuvent être identifiées par une machine.  

Le but est de construire un algorithme qui, à partir des dimensions géométriques d’un billet, détermine s’il s’agit d’un vrai ou d’un faux billet.

## Modèle de Données

### Dimensions Géométriques
Les caractéristiques disponibles pour chaque billet sont :
- **length** : longueur du billet (en mm) ;
- **height_left** : hauteur du billet mesurée à gauche (en mm) ;
- **height_right** : hauteur du billet mesurée à droite (en mm) ;
- **margin_up** : marge entre le bord supérieur du billet et son image (en mm) ;
- **margin_low** : marge entre le bord inférieur du billet et son image (en mm) ;
- **diagonal** : diagonale du billet (en mm).

Ces dimensions seront utilisées pour entraîner et tester l'algorithme.

### Fichier de Paramétrisation
Un fichier d’exemple contenant 1 500 billets est fourni :
- 1 000 vrais billets ;
- 500 faux billets.  

Une colonne supplémentaire précise la nature de chaque billet (vrai ou faux).  
Ce fichier permettra une analyse descriptive (répartition des dimensions, nombre de vrais/faux billets, etc.).

## Algorithme

### Langage
L’algorithme peut être développé en **Python** ou **R**.

### Fonctionnement Général
L'algorithme doit être capable de :  
1. Lire un fichier contenant les dimensions géométriques de plusieurs billets (format fourni : `billets_production.csv`).
2. Déterminer si chaque billet est vrai ou faux, uniquement sur la base des dimensions.  

Deux méthodes de prédiction seront mises en concurrence :
- **Régression logistique classique** ;
- **K-means**, en utilisant les centroïdes pour la prédiction.  

L’algorithme devra identifier un maximum de faux billets avec une évaluation précise à l’aide d’une **matrice de confusion** (faux positifs, faux négatifs).

## Livrables Attendues
L’algorithme doit être livré sous forme d’un **notebook Python ou R**, fonctionnel avec les dimensions géométriques.

## Calendrier
Le délai prévu pour l'expérimentation et la production de l'algorithme est d'**un mois**.
