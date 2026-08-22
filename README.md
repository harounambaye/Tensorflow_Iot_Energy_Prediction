# Tensorflow_Iot_Energy_Prediction

## Description

Projet pratique de Deep Learning avec **TensorFlow/Keras**, construit dans le cadre du DeepLearning appliqué à l'**IoT (Internet des objets)**.

L'objectif est d'entraîner un **réseau de neurones** capable de prédire la **consommation énergétique** d'un bâtiment à partir de trois caractéristiques mesurées par des capteurs : la **température**, l'**humidité** et le **nombre d'occupants**.

Ce projet s'inscrit dans une suite d'ateliers couvrant l'écosystème Python pour la Data Science et l'IA (NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn), et se concentre ici sur le **Deep Learning**, à travers un problème de **régression**.

## Objectif

Construire, entraîner, évaluer et réutiliser un modèle de régression capable d'estimer la consommation énergétique d'un bâtiment, en suivant le workflow classique du Machine Learning :

```
Génération des données → X/y → Train/Test → Modèle → Compilation → Entraînement
→ Évaluation → Prédiction → Sauvegarde → Chargement → Fonction d'inférence
```

## 🗂️ Structure du dépôt

```
Tensorflow_Iot_Energy_Prediction/
│
├── notebooks/
│   └── Tensorflow_Iot_Energy_Prediction.ipynb   # Notebook complet du projet
│
└── models/
    └── modele_consommation.keras      # Modèle entraîné, sauvegardé au format Keras
```

## Approche

Les données ne proviennent pas d'un fichier externe : elles sont **générées aléatoirement** (1000 observations), selon des lois statistiques réalistes (loi normale pour la température, loi uniforme pour l'humidité, tirage entier pour le nombre d'occupants), puis combinées à une **formule de consommation avec bruit aléatoire**, afin de se rapprocher d'un contexte réel où aucune formule physique n'est parfaite.

Le modèle est un **réseau de neurones séquentiel** simple :

| Couche | Neurones | Activation |
|---|---|---|
| Couche 1 | 16 | ReLU |
| Couche 2 | 8 | ReLU |
| Couche 3 (sortie) | 1 | linéaire |

## Technologies utilisées

- **Python 3**
- **TensorFlow / Keras** — construction, entraînement et sauvegarde du réseau de neurones
- **NumPy** — génération et manipulation des données
- **Matplotlib** — visualisation de l'apprentissage et des prédictions
- **Jupyter Notebook**

## Installation

```bash
pip install tensorflow matplotlib numpy
```

## Utilisation

1. Ouvrir le notebook `notebooks/Tensorflow_Iot_Energy_Prediction.ipynb` dans Jupyter.
2. Exécuter les cellules dans l'ordre : génération des données, découpage train/test, construction et compilation du modèle, entraînement, évaluation, prédiction.
3. Le modèle entraîné est automatiquement sauvegardé dans `models/modele_consommation.keras`.
4. Une fonction `predire_consommation()` est fournie en fin de notebook pour réutiliser le modèle chargé sur de nouvelles observations (température, humidité, occupants).

## Contenu du Projet

- Génération d'un dataset synthétique réaliste
- Séparation des données en ensembles d'entraînement et de test
- Construction d'un réseau de neurones avec Keras (API séquentielle)
- Compilation (optimiseur, fonction de perte, métrique)
- Entraînement avec suivi de la validation (courbes de perte et de MAE)
- Évaluation du modèle sur les données de test
- Comparaison visuelle prédictions vs valeurs réelles
- Sauvegarde et rechargement du modèle
- Fonction d'inférence prête à l'emploi

## Auteur

**Harouna MBAYE**

Projet réalisé dans le cadre de ma formation en **Intelligence Artificielle** à la **SONATEL ACADEMY - ORANGE DIGITAL CENTER**.
