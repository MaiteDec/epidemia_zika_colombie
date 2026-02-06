#############################################################################
### PROJET MEPI - Modélisation d'une épidemie de Zika en Colombie en 2015 ###
### Capucine Benoit-Grignard, Maite Decenciere (M2 MODE)                  ###
#############################################################################

## Description du projet ##
Le script accompagnant ce document permet d'inférer des paramètres d'un modèle SEAIR appliquée à une épidémie de Zika observée à San Andres, en 2015, avec une méthode d'inférence Approximate Bayesian Computation (ABC Rejection).
Il permet de simuler la dynamique épidémiologique, d'estimer les paramètres clés (p, beta et theta), d'évaluer les performances du modèle par validation croisée et comparer les dynamiques simulées à celle observée.

## Fonctionnalites ##

## Environnement logiciel ##
Les analyses ont été réalisées avec les versions suivantes : 
- Langage R (version ≥ 4.2.2)
- RStudio
- Système d'exploitation non spécifique (Windows, Linux)

## Bibliothèques R utilisées ##
# Packages dont sont issues les données :
- `outbreaks`
# Packages pour la gestion des données : 
- `lubridate`: Gestion des dates 
- `dplyr` et `data.table`: Gestion des data.frame
- `readr`: Lecture fichier .txt / .csv
# Packages pour la simulation / l'inférence / l'ABC 
`deSolve`: Resoltion d'équations différentielles
- `abc`: Méthode d'ABC rejection et cross validation
`BRREWABC`:
# Packages graphiques :
- `ggplot2`: Visualisation des résultats 
- `grid`, `gridExtra`, `ggpubr`: Rearrange les figures
- `GGally`:
- `devtools`:
Toutes les bibliothèques nécessaires sont directement téléchargées au début du code si non installées 

## 1 seul script R : simulation_zika.qmd ##
Peut être knitté en format .html ou .pdf pour un meilleur rendu

## Paramètres principaux modifiables ##
Les principaux paramètres contrôlant les analyses sont : 
# Paramètres du modèle : 
- p : proportion d'individus symptomatiques
- beta : taux de transmission
- theta : infectiosité relative des asymptomatiques
# Paramètres ABC : 
- T : nombre de simulations (ici : 10 000)
- Tol : seuil de tolérance de l'ABC (ici : 0.05)
- method : méthode ABC (ici "rejection)
# Paramètres de validation croisée :
- nval : nombre de jeux de validation (ici : 500)
Ces paramètres peuvent être modifiés dans le script simulation_zika.qmd

## Reproductibilité ##
Les résultats obtenus dans l'étude sont reproductibles à condition d'utiliser les mêmes versions de R et des bibliothèques listées précédemment.
Pour permettre cette reproductibilité, la graine a été fixée avec set.seed(). 
