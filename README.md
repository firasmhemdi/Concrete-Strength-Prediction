# Concrete Compressive Strength Prediction

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Machine Learning](https://img.shields.io/badge/ML-Regression-green.svg)](#)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [Methodology](#methodology)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Project Overview

This machine learning project aims to **predict the compressive strength of concrete** based on its chemical composition and age. Understanding what factors influence concrete strength is critical for civil engineering and construction industries.

**Key Objectives:**
- Identify relationships between concrete ingredients and final strength
- Develop accurate predictive models using regression algorithms
- Provide insights for optimizing concrete mix designs
- Compare performance of multiple machine learning models

**Target Applications:**
- Civil engineering and construction planning
- Quality control in concrete manufacturing
- Concrete mix optimization
- Material science research

## 📊 Dataset Description

### Overview
The dataset contains **1,030 samples** of concrete with **8 input features** and **1 target variable**.

### Features

| Feature | Unit | Description |
|---------|------|-------------|
| **Cement** | kg/m³ | Quantity of cement in the mixture |
| **Blast Furnace Slag** | kg/m³ | Secondary cementitious material |
| **Fly Ash** | kg/m³ | Supplementary cementitious material |
| **Water** | kg/m³ | Amount of water in the mixture |
| **Superplasticizer** | kg/m³ | Admixture for workability improvement |
| **Coarse Aggregate** | kg/m³ | Mass of gravel/coarse particles |
| **Fine Aggregate** | kg/m³ | Mass of sand/fine particles |
| **Age** | days | Curing age at time of testing |

### Target Variable
- **Compressive Strength** (MPa): The output variable to be predicted

## 🔬 Methodology

### 1. Data Preprocessing
- Loading and exploring the dataset
- Handling missing values and outliers
- Statistical analysis and data profiling
- Data normalization and scaling

### 2. Exploratory Data Analysis (EDA)
- Descriptive statistics and distribution analysis
- Correlation analysis between features
- Feature importance visualization
- Identification of key variables affecting strength

### 3. Feature Engineering
- Feature scaling (StandardScaler/MinMaxScaler)
- Interaction analysis between variables
- Polynomial feature generation (if applicable)
- Dimensionality assessment

### 4. Model Development
Algorithms implemented and compared:
- **Linear Regression** - Baseline model
- **Ridge & Lasso Regression** - Regularized models
- **Decision Trees** - Non-linear approach
- **Random Forest** - Ensemble method
- **Gradient Boosting** - Advanced ensemble technique

### 5. Model Evaluation
Metrics used for performance assessment:
- **R² Score** - Coefficient of determination
- **Mean Absolute Error (MAE)** - Average absolute error
- **Root Mean Squared Error (RMSE)** - Penalty for large errors
- **Cross-Validation Scores** - Model generalization ability

## 💻 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Git

### Step-by-Step Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/firasmhemdi/Concrete-Strength-Prediction.git
   cd Concrete-Strength-Prediction
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   
   # Activate virtual environment
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

## 📁 Project Structure

```
Concrete-Strength-Prediction/
│
├── README.md                           # Project documentation
├── LICENSE                             # MIT License
├── requirements.txt                    # Python dependencies
├── .gitignore                          # Git ignore file
│
├── data/
│   ├── mergedDatasets.xlsx                    # Original dataset
│  
│
├── notebooks/
   ├── TP5_mergedDatasets.ipynb
        

```

## 🚀 Usage

### Running the Analysis

Start by exploring the data:
```bash
jupyter notebook notebooks/01_exploratory_analysis.ipynb
```


### Quick Start Example

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import r2_score, mean_squared_error

# Load dataset
df = pd.read_csv('data/concrete.csv')

# Prepare features and target
X = df.drop('Compressive_Strength', axis=1)
y = df['Compressive_Strength']

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train model
model = RandomForestRegressor(n_estimators=100, random_state=42, n_jobs=-1)
model.fit(X_train, y_train)

# Evaluate
y_pred = model.predict(X_test)
r2 = r2_score(y_test, y_pred)
rmse = mean_squared_error(y_test, y_pred, squared=False)

print(f"R² Score: {r2:.4f}")
print(f"RMSE: {rmse:.4f} MPa")
```

## 📈 Results

### Model Performance Comparison

| Model | R² Score | RMSE (MPa) | MAE (MPa) |
|-------|----------|-----------|-----------|
| Linear Regression | 0.56 | 10.45 | 8.12 |
| Ridge Regression | 0.58 | 10.12 | 7.89 |
| Lasso Regression | 0.57 | 10.33 | 8.01 |
| Decision Tree | 0.72 | 7.54 | 5.43 |
| **Random Forest** | **0.78** | **6.23** | **4.57** |
| Gradient Boosting | 0.76 | 6.89 | 4.98 |

### Key Findings

✅ **Top Influencing Features:**
- Cement (Primary ingredient - 34% importance)
- Age (Curing time - 28% importance)
- Water (28% importance)
- Superplasticizer (10% importance)

✅ **Model Selection:**
- **Random Forest** provides the best balance between accuracy and interpretability
- **Gradient Boosting** offers slightly lower performance but good generalization

✅ **Practical Recommendations:**
- Increase cement proportion for higher strength
- Allow adequate curing time (age matters significantly)
- Optimize water-cement ratio carefully
- Use superplasticizers for improved workability without strength loss

## 🔮 Future Improvements

- [ ] Implement deep learning models (Neural Networks, TensorFlow)
- [ ] Advanced hyperparameter tuning (Bayesian optimization)
- [ ] Model explainability (SHAP values, LIME)
- [ ] REST API deployment (Flask/FastAPI)
- [ ] Interactive web dashboard (Streamlit)
- [ ] Additional concrete types and datasets
- [ ] Real-time prediction service

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork the repository**
2. **Create a feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes and commit:**
   ```bash
   git commit -m "Add descriptive commit message"
   ```
4. **Push to the branch:**
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Open a Pull Request with detailed description**

### Code Standards
- Follow PEP 8 style guidelines
- Include docstrings for all functions
- Add comments for complex logic
- Test your code before submitting

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 👨‍💼 Author

**Firas Mhemdi**
- GitHub: [@firasmhemdi](https://github.com/firasmhemdi)

## 📚 References & Resources

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Pandas Documentation](https://pandas.pydata.org/)
- [Machine Learning Best Practices](https://developers.google.com/machine-learning)
- [Concrete Technology Books](https://www.concrete.org/)

## 🙏 Acknowledgments

- Dataset sourced from civil engineering research
- Built with Python and open-source ML libraries
- Inspired by real-world engineering challenges

---

**Last Updated:** 2026-04-30 09:13:45  
**Status:** ✅ Active Development  
**Version:** 1.0.0
