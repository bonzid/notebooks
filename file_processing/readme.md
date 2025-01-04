# Traitement des fichiers texte

## Description du projet
Ce notebook a été rédigé à l'occasion d'un mini travail en algorithmique et Python en novembre 2023. Il a pour objectif de :
- Segmenter et tokeniser des fichiers texte.
- Générer des fichiers de sortie au format `seg.json` et `stats.tsv`.

Il comprend plusieurs étapes clés, depuis l'importation des modules nécessaires jusqu'à la mise en œuvre de fonctions pour automatiser le traitement de répertoires complets.

---

## Sections principales

1. **Importation des modules et téléchargement de fichiers test**  
   Mise en place des outils et jeux de données requis

2. **Segmentation en phrases**  
   Découpe des textes en phrases exploitables

3. **Tokenisation avec suppression des espaces**  
   Transformation des textes pour une analyse plus fine

4. **Lecture d'un répertoire**  
   Traitement de plusieurs fichiers dans un répertoire

5. **Création du fichier avec le texte segmenté et tokenisé**  
   Génération d'un fichier `seg.json` pour les résultats segmentés.

6. **Création du fichier stats**  
   Calcul et sauvegarde des statistiques dans un fichier `stats.tsv`

7. **Automatisation avec une fonction globale**  
   Intégration des différentes étapes dans une fonction unique pour traiter des répertoires

---

## Fonctionnalités principales
- **Segmentation** : conversion de textes bruts en phrases structurées
- **Tokenisation** : transformation des phrases en une série de tokens
- **Extraction des statistiques** : génération d'informations quantitatives (e.g., nombre de mots, de phrases)
- **Traitement en lot** : lecture et traitement automatique de plusieurs fichiers dans un répertoire
