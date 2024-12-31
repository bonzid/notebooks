# Opinion classifier

## Description
**Opinion classifier** est un projet de classification des opinions (ou sentiments) utilisant l'apprentissage automatique. Ce projet a été conçu dans le cadre d'un cours de programmation Python et d'algorithmique lors de ma première année de master. 

Ce projet a pour but de classifier des avis Google de restaurants comme positif, négatif ou neutre. Notre dataset est constitué d'avis récupérés directement sur Google Maps et nettoyés avec pour chacun d'eux : une note donnée par l'utilisateur (nombre d’étoiles), un label “positif”, “négatif” ou “neutre” et un texte d'évaluation. Nous estimons :

- 🙁 1-2 étoiles : avis négatif,
- 😐 3 étoiles : avis neutre,
- 🙂 4-5 étoiles : avis positif.

L'utilisation du modèle DistilBERT permet de classer un avis comme positif, négatif ou neutre selon le texte contenu dans l’avis posté.


Le fichier principal, `opinion_classification.ipynb`, contient le code et les étapes nécessaires pour :
- Extraire des données d'opinion via le web scraping (avis Google sur divers restaurants : crawl et scrap)
- Préparer les données pour l'entraînement du modèle
- Entraîner et évaluer le modèle

---

## Fonctionnalités
1. **Scraping des données** : utilisation de selenium et parsel pour extraire des avis Google sur des pages de restaurants
2. **Préparation des données** : nettoyage, étiquetage et transformation des données pour l'entraînement
3. **Classification des opinions** : entraînement du modèle basé sur DistilBERT
4. **Évaluation du modèle** : analyse des performances (précision, rappel, F1)

---
### Bibliothèques Python principales utilisées
- `selenium`
- `parsel`
- `torch`
- `transformers`
- `sklearn`
- `tqdm`

---

## Données
Dans ce projet, nous utilisons un dataset divisé en deux partitions : train_data et test_data.
-  train_data : il est utilisé pour entraîner le modèle. Il est composé de paires texte-label où le texte représente les avis des utilisateurs et le label représente la classe (positive, négative, neutre) associée à chaque avis.
- test_data : il est utilisé pour évaluer les performances du modèle après l'entraînement. Il est également composé de paires texte-étiquette, mais il est séparé de l'ensemble d'entraînement. Son but est d'évaluer la prise de décision du modèle des données qu'il n'a pas vues pendant l'entraînement.


---

## Pistes d'amélioration

**Récupération des données :**
L’action de scrolling ne semble pas tout à fait opérationnelle sur ces deux fonctions.
Le bouton “See more” n’est pas systématiquement pris en compte pour chacun des avis. 
Les avis récupérés par scrap sont uniquement en anglais, ce qui limite la quantité d’avis récupérés notamment sur les restaurants français. 
Nous avons pu observer que notre ChromeDriver démarre parfois en langue chinoise, ce qui bloque la récupération des URLs “Reviews”. Nous avons essayé de sélectionner la langue française ou anglaise dans les options de notre ChromeDriver ou même de décoder les URLs de recherche avant de les boucler dans la fonction crawl. Mais ces solutions ne semblent pas fonctionner car le problème reste présent pour certaines exécutions du programme (pb de cookies?). 

**Prétraitement des données :**
L’ajout d’une stoplist pourrait être bénéfique dans le cadre du prétraitement de nos données.
Une lemmatisation ou bien la correction de fautes d’orthographe, d’erreurs de saisie peuvent éventuellement être envisagées pour améliorer la performance de notre modèle. 

**Entraînement, inférence et évaluation du modèle :**
Notre modèle ne semble prédire des avis comme “positifs” malgré la présence d’avis neutres et négatifs dans notre partition test. Cette optimisme excessif de notre modèle peut s’expliquer de différentes manières : 
Nous avons, dans un premier temps, un certain déséquilibre dans nos données en termes d’avis aux labels “positifs”, “négatifs” et “neutres”. En effet, la grande majorité des avis récupérés sont “positifs”, ce qui peut entraîner un biais dans notre modèle et favoriser la prédiction d’avis positifs. Récupérer des avis “négatifs” ou “neutres” en priorité est une de nos problématiques : Google Maps met en avant des restaurants aux notes positives, peu importe les filtres donnés dans nos recherches. 
Il est également possible que les caractéristiques extraites de nos avis ne sont pas représentatives de l’ensemble des caractéristiques qui permettraient de déterminer un avis comme positif, négatif ou neutre. Nous pourrions envisager d’élargir notre base de données pour affiner l’entraînement de notre modèle.
