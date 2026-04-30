# Prédiction de la Résistance du Béton (Machine Learning)

Ce projet vise à prédire la résistance à la compression du béton en fonction de sa composition chimique et de son âge.

## Description du Dataset
Le jeu de données contient les colonnes suivantes :

| Colonne | Description | Type |
| :--- | :--- | :--- |
| **Ciment** | Quantité de ciment utilisée ($kg/m^3$) | Numérique |
| **Laitier** | Laitier de haut fourneau (matériau secondaire) | Numérique |
| **Cendres volantes** | Autre matériau cimentaire | Numérique |
| **Eau** | Quantité d'eau dans le mélange | Numérique |
| **Superplastifiant** | Adjuvant pour la maniabilité | Numérique |
| **Gros granulat** | Masse du gravier ou granulat grossier | Numérique |
| **Granulat fin** | Masse du sable ou granulat fin | Numérique |
| **Age** | Âge du béton au moment du test (jours) | Numérique (Entier) |
| **Résistance** | **Variable Cible** : Résistance à la compression ($MPa$) | Numérique |

## Objectifs du Projet
Ce jeu de données est utilisé pour :
* **Analyses de corrélation** entre les composants et la résistance.
* **Entraînement de modèles de régression** (Régression Linéaire, RandomForest, etc.).
* **Optimisation des formulations** du béton[cite: 1].

## Installation et Utilisation
1. Clonez le dépôt : `git clone https://github.com/votre-nom/Concrete-Strength-Prediction.git`
2. Installez les dépendances : `pip install pandas numpy scikit-learn seaborn matplotlib`
3. Ouvrez le notebook : `jupyter notebook notebooks/TP5_mergedDatasets.ipynb`
