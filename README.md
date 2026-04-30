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

## Concrete Strength Prediction Repository

This is a **machine learning regression project** written in Jupyter Notebooks that predicts concrete compressive strength based on its chemical composition and age.

### Project Overview

**Objective:** Predict concrete compressive strength (MPa) from 8 input features representing the concrete mix composition and curing time.

### Dataset Features

The dataset contains 9 columns:
- **8 Input Features:** Cement, slag (blast furnace slag), fly ash, water, superplasticizer, coarse aggregate, fine aggregate, and age (in days)
- **1 Target Variable:** Compressive strength (MPa)

### Key Project Activities

The project focuses on:
- **Correlation Analysis:** Understanding relationships between concrete components and final strength
- **Regression Modeling:** Training models like Linear Regression and Random Forest
- **Concrete Formulation Optimization:** Using ML insights to improve mix designs

### Tech Stack

- **Language:** Python (100% Jupyter Notebooks)
- **Libraries:** pandas, numpy, scikit-learn, seaborn, matplotlib
- **Type:** Regression task

### Getting Started

To run this project:
1. Clone the repository
2. Install dependencies: `pip install pandas numpy scikit-learn seaborn matplotlib`
3. Open the main notebook: `jupyter notebook notebooks/TP5_mergedDatasets.ipynb`

