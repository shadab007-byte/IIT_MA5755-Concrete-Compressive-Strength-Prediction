# IIT_Madras_MA5755-Concrete-Compressive-Strength-Prediction

This project develops a machine learning pipeline to predict **concrete compressive strength** using various regression models. It includes exploratory data analysis (EDA), feature engineering, model training, evaluation, and a user interface via **Streamlit** for deployment.

---

## Project Structure

Ensure the following folder structure exists before running the code:

```
├── concrete_strength.ipynb
├── Concrete_Data.csv
├── preprocessing_data/
├── models/
├── images/
│   ├── concrete_logo.jpg
│   ├── tall_building.jpg
│   ├── medium_building.jpg
│   ├── low_building.jpg
│   └── roads.jpg
```

- `preprocessing_data/`  
  Folder where all visualizations from the EDA (histograms, heatmaps, scatter plots) will be saved. **Leave this folder empty before running the notebook.**

- `models/`  
  Folder where all trained machine learning models and preprocessing scalers will be saved as `.pkl` files. **Leave this folder empty before running the notebook.**

- `images/`  
  Required folder containing all the static images used in the Streamlit application. Upload this folder manually before running the app.

---

## Setup Instructions

### 1. Install Dependencies

Make sure the following libraries are installed:

```bash
pip install streamlit xgboost scikit-learn matplotlib seaborn
```

### 2. Load the Dataset

Place `Concrete_Data.csv` in the root directory. The notebook will handle preprocessing, visualization, and saving results.

---

## Features

### Exploratory Data Analysis
- Target variable distribution
- Feature histograms and scatter plots
- Correlation heatmap
- Boxplots for outlier detection

### Preprocessing
- Outlier capping and Z-score filtering
- Skewness correction using log transform
- Feature scaling using StandardScaler and MinMaxScaler

### Models Trained
- Linear Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- Support Vector Regressor  
- K-Nearest Neighbors Regressor  
- XGBoost Regressor

All models are trained and evaluated using RMSE and R² score. Results are visualized for comparison.

### Streamlit Interface
An interactive web app is provided using Streamlit where users can input feature values and obtain predicted concrete strength. Recommendations are shown based on the predicted value.

---

## How to Run the Streamlit App

In a local environment or Colab with tunneling:

```bash
streamlit run concrete_strength.ipynb  # If saved as .py, else use `%run` inside notebook
npx localtunnel --port 8501            # Optional for external access
```

**Note**: Ensure the `images/` folder is uploaded before launching the app to avoid missing UI elements.

---

## Output

- Model performance visualizations saved automatically
- Best-performing model (XGBoost) used for final predictions
- Compressive strength predictions categorized into recommended usage types (roads, low-rise, medium-rise, tall buildings)

---
