# Conférence sur le NLP et les Applications Génératives

## Table des Matières
1. [Introduction](#introduction)
2. [Traitement du Langage Naturel (NLP)](#traitement-du-langage-naturel-nlp)
   1. [Tokenization](#tokenization)
   2. [Les Expressions Régulières](#les-expressions-régulières)
   3. [Suppression des Mots Vides](#suppression-des-mots-vides)
   4. [Stemming](#stemming)
   5. [Lemmatisation](#lemmatisation)
3. [Modèles Génératifs](#modèles-génératifs)
4. [Applications](#applications)
5. [Conclusion](#conclusion)

## Introduction
Bienvenue à la conférence sur le NLP et les Applications Génératives. Dans cette conférence, nous couvrirons les bases du NLP, explorerons les modèles génératifs et discuterons de leurs applications.

## Traitement du Langage Naturel (NLP)
Le NLP est un domaine de l'intelligence artificielle qui se concentre sur l'interaction entre les ordinateurs et les humains à travers le langage naturel. [En savoir plus sur le NLP](https://fr.wikipedia.org/wiki/Traitement_automatique_des_langues).

### Tokenization
La tokenization est le processus de division d'un texte en plus petites unités appelées tokens, comme des mots ou des phrases. 
Nous utiliserons la librairie SpaCy.\
Lien colab: [![Ouvrir Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1I6g9fNEL-RszTPupXUgCoZ0MAUK89oEH?authuser=1#scrollTo=_ZMRclVSFhVs)\
Ressources Youtube: [![video YouTube](https://img.shields.io/badge/Watch%20on-YouTube-red?logo=youtube)](https://www.youtube.com/watch?v=_lR3RjvYvF4&list=PLeo1K3hjS3uuvuAXhYjV2lMEShq2UYSwX&index=8)
### Les Expressions Régulières
Les expressions régulières sont des séquences de caractères qui définissent un modèle de recherche. Elles sont utilisées pour trouver et manipuler des chaînes de texte.

### Suppression des Mots Vides
### Stemming
**Stemming** est une technique de traitement automatique du langage naturel (NLP) utilisée pour réduire les mots à leur forme de base ou racine. Elle supprime les flexions ou les affixes dérivationnels des mots, généralement en suivant un ensemble de règles simples ou d'algorithmes. L'objectif principal du stemming est de regrouper les mots ayant le même sens de base afin qu'ils puissent être traités comme équivalents lors de l'analyse de texte.

#### Exemples :
- **Running, runs, runner** → **Run**
- **Studies, studying** → **Studi**

Le stemming est souvent utilisé dans les moteurs de recherche, les systèmes de récupération d'informations et le text mining pour améliorer la performance des tâches telles que l'indexation de documents et la correspondance de mots-clés.

Un algorithme de stemming populaire est le **Porter Stemmer**, qui applique une série de règles pour retirer les suffixes de manière itérative. Cependant, le stemming peut parfois entraîner une sur-réduction (par exemple, *"generalization"* → *"general"*) ou une perte de sens.

Pour des résultats plus précis, on utilise souvent la **lemmatisation**, qui prend en compte le contexte et la grammaire du mot.


### Lemmatisation
**Lemmatisation** est une technique de traitement automatique du langage naturel (NLP) qui consiste à ramener un mot à sa forme canonique ou **lemme**, en prenant en compte son contexte grammatical et son sens. Contrairement au stemming, qui applique des règles simples pour supprimer les suffixes, la lemmatisation utilise des dictionnaires et une analyse linguistique pour obtenir des résultats plus précis.

#### Exemples :
- **Running** → **Run** (verbe à l'infinitif)
- **Better** → **Good** (adjectif au degré positif)

La lemmatisation est souvent utilisée dans des applications nécessitant une compréhension linguistique plus fine, comme :
- L'analyse de sentiments
- La traduction automatique
- Les systèmes de recherche d'information

Elle est préférée au stemming lorsque la précision est cruciale, car elle évite les problèmes de sur-réduction ou de perte de sens. Cependant, elle peut être plus complexe et exigeante en termes de calcul, car elle nécessite une connaissance contextuelle et l'utilisation de ressources comme des lexiques ou des bases de données linguistiques.\
*spaCy supporte seulement la lemmatization. selon le créateur de spaCy Matt Honnibal dans issue #327 sur GitHub, stemmers sont rarement une bonne idée*.\
Lien colab: [![Ouvrir Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1I6g9fNEL-RszTPupXUgCoZ0MAUK89oEH?authuser=1#scrollTo=_ZMRclVSFhVs)\
Ressources Youtube: [![video YouTube](https://img.shields.io/badge/Watch%20on-YouTube-red?logo=youtube)](https://www.youtube.com/watch?v=HHAilAC3cXw&list=PLeo1K3hjS3uuvuAXhYjV2lMEShq2UYSwX&index=10)

## Modèles Génératifs
Les modèles génératifs sont une classe de modèles d'apprentissage automatique qui génèrent de nouvelles instances de données. [En savoir plus sur les Modèles Génératifs](https://fr.wikipedia.org/wiki/Modèle_génératif).