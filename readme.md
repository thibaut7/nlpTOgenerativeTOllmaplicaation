# Natural Language Processing(Traitement du langage Naturel) et les Applications Génératives

## Table des Matières
1. [Introduction](#introduction)
    1. [NLP worklow](#NLP-worklow)
       - [Comprendre le problème](#Comprendre-le-problème)
       - [Comprendre et préparer la donnnée](#Comprendre-et-préparer-la-donnnée)
       - [Approches de solution](#Approches-de-solution)
       - [Itération et amélioration du résultat](#Itération-et-amélioration-du-résultat)
       - [Evaluation et déploiement](#Evaluation-et-déploiement)
2. [Traitement du Langage Naturel (NLP)](#traitement-du-langage-naturel-nlp)
   1. [Tokenization](#tokenization)
   2. [Les Expressions Régulières](#les-expressions-régulières)
   3. [Suppression des Mots Vides](#suppression-des-mots-vides)
   4. [Stemming](#stemming)
   5. [Lemmatisation](#lemmatisation)
   6. [Part of Speech et NER(Named Entity Recognition)](#Part-of-Speech-and-NER)
3. [Modèles Génératifs](#modèles-génératifs)
4. [Applications](#applications)
5. [Conclusion](#conclusion)

## Introduction
Bienvenue à la conférence sur le NLP et les Applications Génératives. Dans cette conférence, nous couvrirons les bases du NLP, explorerons les modèles génératifs et discuterons de leurs applications.
## NLP worklow
### Comprendre le problème
Dans cette partie on essaie de répondre aux questions suivantes:
    - Quel est le principal problème? on n'essayera de Comprendre le problème de manière abstraite: les hypothèses et les attentes du projet
    - Comment résoudre le problème: Faire une liste de d'idée qui sera utilisé comme plan 
### Comprendre et préparer la donnnée
Comme nous allons travailler avec des données textuelles non structurées, cela peut necessité une nettoyage.
C'est à dire remplacer les abbréviations, les acronymes, effacer les ponctuations...
Une pratique répandue est de sélectionner un gold dataset(qui est la meilleure jeu de données disponible sous certaines conditions). L'obtention de ce jeu de données peut nécessité un nettoyage et etiquetage manuel.
### Approches de solution
Faire ressortir les types de combinaisons d'algorithme et de jeu de données qui marchent pour notre problème puis se concentrer sur eux et les étudier en profondeur.
Tout cela te permettra d'estimer la quantité de travail à faire.
### Itération et amélioration du résultat
Ici on a déja selectionné les algorithmes, données et méthodes avec un résultat encourangeant.
### Evaluation et déploiement
L'évaluation et le déploiement sont essentiels pour rendre votre travail accessible et fiable. Une bonne évaluation garantit la confiance dans vos modèles, tandis que le déploiement permet leur utilisation pratique via des appels simples ou des API REST.

#### Évaluation
Un modèle avec 99 % de précision, comme dans le cas de la classification des tumeurs cérébrales, n'est pas forcément fiable. Si le modèle prédit que personne n'a de tumeur, il atteint une précision élevée simplement parce que les cas réels de tumeurs sont rares.  
Pour une utilisation pratique, il est crucial de dépasser la précision et d'examiner la **matrice de confusion** pour identifier les erreurs. Comprendre ce que le modèle fait bien ou mal permet de l'améliorer.  
Des techniques de visualisation, comme **t-SNE**, aident à comprendre le fonctionnement interne des modèles.  
Dans des applications NLP continues (ex. : filtres anti-spam ou chatbots), une évaluation régulière est indispensable pour éviter la dégradation des performances.

#### Déploiement
Le model peut etre souvent déployer sous forme d'API REST.
## Traitement du Langage Naturel (NLP)
Le NLP est un domaine de l'intelligence artificielle qui se concentre sur l'interaction entre les ordinateurs et les humains à travers le langage naturel. [En savoir plus sur le NLP](https://fr.wikipedia.org/wiki/Traitement_automatique_des_langues).

### Tokenization
La tokenization est le processus de division d'un texte en plus petites unités appelées tokens, comme des mots ou des phrases. 
Nous utiliserons la librairie SpaCy.\
Lien colab: [![Ouvrir Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1I6g9fNEL-RszTPupXUgCoZ0MAUK89oEH?authuser=1#scrollTo=_ZMRclVSFhVs)\
Ressources Youtube: [![video YouTube](https://img.shields.io/badge/Watch%20on-YouTube-red?logo=youtube)](https://www.youtube.com/watch?v=_lR3RjvYvF4&list=PLeo1K3hjS3uuvuAXhYjV2lMEShq2UYSwX&index=8)
### Les Expressions Régulières
Les expressions régulières sont des séquences de caractères qui définissent un modèle de recherche. Elles sont utilisées pour trouver et manipuler des chaînes de texte.
#### Introduction aux Expressions Régulières

##### Qu'est-ce qu'une Expression Régulière (Regex) ?

Les Expressions Régulières (souvent abrégées en **regex**) sont des séquences de caractères qui définissent un modèle de recherche. Elles sont utilisées pour :

- Faire correspondre des chaînes de texte.
- Valider des entrées (par exemple, des adresses email, des numéros de téléphone).
- Extraire des informations à partir de données structurées.
- Remplacer ou modifier du texte basé sur des modèles.

##### Pourquoi utiliser les Regex ?

Les regex sont incroyablement puissantes pour :
- Simplifier les manipulations complexes de chaînes de caractères.
- Permettre une correspondance concise et flexible des modèles de texte.

Exemples d'applications dans le monde réel :
- Valider les entrées des utilisateurs (par exemple, vérifier si une adresse email est valide).
- Rechercher et remplacer du texte dans des documents.
- Analyser des données à partir de journaux ou de formats structurés comme JSON ou XML.

---

##### Exemple : Correspondance de Modèle Basique

Voici un exemple en Python utilisant le module `re` pour une correspondance de modèle basique :

```python
import re

# Définir un texte à rechercher
texte = "Bonjour, je m'appelle ChatGPT !"

# Rechercher un modèle
correspondance = re.search(r"ChatGPT", texte)

if correspondance:
    print(f"Trouvé : {correspondance.group()}")  # Sortie : Trouvé : ChatGPT
else:
    print("Aucune correspondance trouvée.")
```

##### Explications :
- `r"ChatGPT"` : Le `r` avant la chaîne garantit qu'elle est traitée comme une chaîne brute (évitant les problèmes avec les séquences d'échappement).
- `re.search()` : Recherche la première occurrence du modèle dans le texte.
- `correspondance.group()` : Renvoie le texte correspondant si une correspondance est trouvée.

---

##### Points Clés à Retenir
- Les regex vous permettent de définir des modèles pour rechercher et manipuler du texte.
- Le module `re` de Python est la bibliothèque de référence pour travailler avec les regex.
- Commencez par des modèles simples et explorez progressivement des modèles plus complexes au fur et à mesure que vous gagnez en confiance.\
Lien colab: [![Ouvrir Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1JPKER9-cidEqEtMfmiknNZ4_-l8RZvWC#scrollTo=fdoXPwaT1tt1)\
Ressources Youtube: [![video YouTube](https://img.shields.io/badge/Watch%20on-YouTube-red?logo=youtube)](https://www.youtube.com/watch?v=lK9gx4q_vfI&list=PLeo1K3hjS3uuvuAXhYjV2lMEShq2UYSwX&index=3)


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
### Part of Speech and NER
Dans cette partie on essaie de voir les classes grammaticales des mots.
#### Entity
Lien colab: [![Ouvrir Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1WlhmfGZEjnF1zhcF6-gUAJ3tL5pBlj4I?authuser=0#scrollTo=ZqeXPFELl9eK)\
Ressources:\
Lien colab: Lien colab: [![Ouvrir Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/futuremojo/nlp-demystified/blob/main/notebooks/nlpdemystified_preprocessing.ipynb#scrollTo=o9HLYYUt1kOP)\
YouTube:[![video YouTube](https://img.shields.io/badge/Watch%20on-YouTube-red?logo=youtube)](https://www.youtube.com/watch?v=aeUE9AXO5Ss&list=PLw3N0OFSAYSEC_XokEcX8uzJmEZSoNGuS&index=4)

#### Installation de SpaCy

Installation de spaCy :

```bash
pip install spacy
```

Charger un modèle linguistique, par exemple le modèle pour le français :

```bash
python -m spacy download fr_core_news_sm
```

## Exemple de code pour identifier les POS

Voici un script simple pour analyser les POS dans une phrase donnée :

```python
import spacy

# Charger le modèle linguistique
nlp = spacy.load("fr_core_news_sm")

# Exemple de texte
texte = "SpaCy est une bibliothèque incroyable pour les tâches de NLP."

# Traitement du texte
doc = nlp(texte)

# Affichage des mots avec leurs POS
print("Word\t\tPOS\t\tExplanation")
print("-" * 30)
for token in doc:
    print(f"{token.text}\t\t{token.pos_}\t\t{spacy.explain(token.pos_)}")
```

## Résultat attendu

Pour le texte donné, le script produit une sortie similaire à :

```
Word        POS        Explanation
------------------------------
SpaCy       PROPN      Proper noun
est         AUX        Auxiliary verb
une         DET        Determiner
bibliothèque NOUN      Noun
incroyable  ADJ        Adjective
pour        ADP        Adposition
les         DET        Determiner
tâches      NOUN      Noun
de          ADP        Adposition
NLP         PROPN      Proper noun
.           PUNCT      Punctuation
```

## Explication

- **token.text** : Le mot ou le symbole dans le texte.
- **token.pos_** : L'étiquette POS attribuée au mot.
- **spacy.explain()** : Donne une explication claire de l'étiquette POS.

## Exemples d'applications des POS

L'analyse des **part of speech** a de nombreuses applications dans le NLP :

1. **Analyse syntaxique** : Comprendre la structure grammaticale d'une phrase pour l'analyse syntaxique ou la création de parse trees.
2. **Extraction d'entités nommées (NER)** : Identifier et catégoriser les entités importantes comme les noms propres, les lieux ou les organisations.
3. **Classification de texte** : Utiliser les informations grammaticales pour améliorer la classification des documents ou des phrases.
4. **Résumé automatique** : Identifier les éléments importants dans un texte, comme les verbes et les noms, pour générer un résumé.
5. **Traduction automatique** : Améliorer la traduction en comprenant les rôles grammaticaux des mots dans une phrase.
6. **Analyse des sentiments** : Étudier les adjectifs et adverbes pour mieux évaluer le ton émotionnel d'un texte.

## Modèles Génératifs
Les modèles génératifs sont une classe de modèles d'apprentissage automatique qui génèrent de nouvelles instances de données. [En savoir plus sur les Modèles Génératifs](https://fr.wikipedia.org/wiki/Modèle_génératif).