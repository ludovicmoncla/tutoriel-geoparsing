
# Tutoriel - Python Geoparsing 


Ce tutoriel reprend ceux proposés pour l'atelier [Librairies Python et Services Web pour la reconnaissance d’entités nommées et la résolution de toponymes](https://anf-tdm-2022.sciencesconf.org/resource/page/id/11) de la formation CNRS [ANF TDM 2022](https://anf-tdm-2022.sciencesconf.org) et pour la session [Natural Language Processing (NLP) for historical texts](https://github.com/ludovicmoncla/SunoikisisDC-Summer2022-Session9) de la formation [SunoikisisDC Summer 2022 Course](https://github.com/SunoikisisDC/SunoikisisDC-2021-2022/wiki/SunoikisisDC-Summer-2022-Session-9).


Dans ce tutoriel, nous montrons comment utiliser des librairies Python pour la reconnaissance des entités nommées (*Named Entity Recognition*) et pour la résolution de toponymes (*Geocoding*). 
Pour cela, nous utiliserons les librairies [spaCy](https://spacy.io), [Stanza](https://stanfordnlp.github.io/stanza/index.html) et [Perdido](https://github.com/ludovicmoncla/perdido).

Nous expérimenterons et comparerons ces librairies au travers deux études de cas : le traitement d'articles encyclopédiques (corpus issu du projet [GEODE](https://geode-project.github.io)) et le traitement de descriptions de randonnées (corpus issu du projet [ANR CHOUCAS](http://choucas.ign.fr)).



### Tâches et problématiques abordées

 1. Reconnaissance et classification des entités nommées en français
 2. Résolution de toponymes (problématique de désambiguïsation)
 3. Créer et afficher une carte à partir d'un texte


Vous pouvez exécuter le notebook à distance en utilisant [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lmoncla/tutoriel-geoparsing/blob/main/Tutoriel-geoparsing.ipynb) ou [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lmoncla/tutoriel-geoparsing/main?filepath=Tutoriel-geoparsing.ipynb).
Sinon, pour exécuter ce tutoriel depuis un environnement local sur votre ordinateur, vous pouvez suivre les instructions ci-dessous. 

## Installer conda

[Conda](https://conda.io/projects/conda/en/latest/index.html) est un système de gestion de paquets et d'environnement open source. Il installe, exécute et met à jour rapidement les paquets et leurs dépendances. 
Nous l'utiliserons pour gérer l'environnement python et toutes les bibliothèques python nécessaires pour les tutoriels.
Il existe plusieurs façons d'installer conda sur votre ordinateur :
1. [Anaconda distribution](https://www.anaconda.com/products/distribution): fournit des applications, de nombreux paquets de science des données et d'apprentissage automatique sont déjà installés.
2. [Miniconda](https://docs.conda.io/en/latest/miniconda.html): une installation minimale pour conda, sans application graphique
3. [Miniforge](https://github.com/conda-forge/miniforge): une autre installation minimale pour conda, sans application graphique (recommandée pour les puces Mac ARM M1 ou M2 (Apple Silicon))


## Configurer un environnement conda

### Cloner ce dépôt git

```bash

git clone https://github.com/ludovicmoncla/tutoriel-geoparsing.git
```

### Configurer l'environnement avec toutes les dépendances nécessaires

#### Méthode 1

* Uilisateurs MacOS/Linux : Créer un nouvel environnement nommé `tutoriel-geoparsing-py39` avec toutes les dépendances nécessaire en utilisant le fichier de configuration `environment-osx-linux.yml` :

```bash
conda env create -f environment-osx-linux.yml
```

* Uilisateurs Windows : Créer un nouvel environnement nommé `tutoriel-geoparsing-py39` avec toutes les dépendances nécessaire en utilisant le fichier de configuration `environment-win64.yml` :

```bash
conda env create -f environment-win64.yml
```

* Activer l'environnement

```bash
conda activate tutoriel-geoparsing-py39
```


#### Méthode 2

* Créer un nouvel environnement nommé `tutoriel-geoparsing-py39`

```bash
conda create -n tutoriel-geoparsing-py39 python=3.9
```

* Activer l'environnement

```bash
conda activate tutoriel-geoparsing-py39
```

* Installer le paquet `fiona` avec conda (évite une erreur lors de l'installation de cette dépendence avec `pip`)

```bash
conda install fiona==1.8.21
```

* Installer les dépendances avec `pip`

```bash
pip install -r requirements.txt
```


### Lancer le serveur Jupyter

```bash
jupyter notebook
```





