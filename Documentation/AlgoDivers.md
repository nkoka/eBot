Mouvement 
-------------------------

Le principe utilisé par le robot est basé sur la logique Flou. Il fonctionne par objectif à atteindre.

Objectif
---------------

Un objectif se constitue d'action à mener à bien
exemple : aller de l'autre coté de la pièce :

Tant que pas de l'autre coté de la pièce
 - Déterminer la direction globale
 - Déterminer la direction locale
 - Si nécessaire, éviter obstacle, recalculer direction globale, recalculer direction locale
 
Les actions sont déterminées selon un comportement défini par l'environnement "ROBOT"

Environnement
----------------------------

Les éléments faisant varier l'environnement sont :
- un obstacle (y compris "trou")
- une batterie faible robot
- la visibilité du robot

Actions
----------------------

les actions disponibles sont les suivantes:
 - Connection SSH à un hôte distant via wifi
 - Suivre une direction
 - Recevoir un ordre distant
 
Détermination direction
--------------------------------

Afin de déterminer la direction à prendre le robot devra être capable de déterminer une direction et de déterminer des points de passage en fonction des différents obstacles sur son passage. Si un obstacle se ddresse devant lui, il devra l'eviter au mieux et redefinir une direction vers son objectif à atteindre.

# Algorithme envisagé

Tant que objectif non atteint
 - Déterminer la direction globale
 - Déterminer la direction locale
 - Si nécessaire, éviter obstacle, recalculer direction globale, recalculer direction locale

# Problème de l'algorithme

L'utilisation de cette algorithme entraîne un effet transitoire dans les déplacement pour éviter les obstacles. Il est nécessaire de vérifier via les capteurs situé sur les cotés du robot que l'obstacle est bien franchi pour déterminé la nouvelle direction globales et locale

#Algorithme final

Tant que objectif non atteint
 - Déterminer la direction globale
 - Déterminer la direction locale
 - Si nécessaire, Début évitement obstacle
 - Tanque obstacle non franchi
  - Eviter obstacle  
 - recalculer direction globale, recalculer direction locale

Variation d'environnement
------------------------------------

# les causes de variation

Ce robot possède des capteurs :
 
- éclairement
- erreurs de mesures et de calcul

#Solutions aux différents problèmes des capteurs

## Eclairement
Afin de s'abstrait du niveau de variation d'eclairement, au démarrage il devra définir le 0 associé à la variation de lumùière en effectuant sur ses capteurs un échantillonnage du niveau 0

##Erreurs de mesures et de calcul
Afin d'obtenir des mesures réalistes, il est nécessaire de moyeenné les mesures. Et d'ajouter un système de détermination d'erreur de mesure et/ou de calcul. Un delta d'erreur devra être calculé afin de corriger l'erreur

exemple : vitesse et/ou position des moteur du robot pour effetcuer un déplacement donné
