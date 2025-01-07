# Visualisation et conversion : classe FichierTexte

20/12/2024

## Objectif

Réalisé dans le cadre d'un cours de Programmation Orientée Objet, ce projet vise à développer une classe Python `FichierTexte` permettant de manipuler des fichiers textes de différents formats : **txt**, **WebAnno** et **Glozz**. Cette classe offre les fonctionnalités suivantes :

- Afficher le texte brut d'un fichier.
- Compter le nombre de caractères dans le fichier.
- Compter le nombre de mots dans le fichier.


## Fonctionnalités

1. **Afficher le texte brut** : Permet de lire et d'afficher le contenu d'un fichier texte indépendamment de son format.

2. **Compter les caractères** : Compte le nombre total de caractères présents dans le fichier.

3. **Compter les mots** : Compte le nombre de mots dans le fichier en utilisant des techniques de segmentation simples.

Plus d'informations au début du notebook (détails des fonctions et des classes filles).


## Organisation du code

Le code est divisé en plusieurs sections pour faciliter la compréhension :

1. Importation des bibliothèques.
2. Téléchargement des fichiers.
3. Définition de la classe `FichierTexte`.
4. Tests et exemples d'utilisation.

## Pistes d'amélioration

- A l'heure actuelle, il est impossible de convertir un fichier WebAnno en fichier Glozz et inversement.
- Il est aussi impossible de visualiser les annotations de type coréférences de manière "claire" en format WebAnno et Glozz.
- Notre méthode `afficher_annotations` pour la classe Glozz ne semble récupérer aucune relation entre les unités.