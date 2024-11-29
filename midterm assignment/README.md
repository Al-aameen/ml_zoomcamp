# Depression Prediction Project

This project aims to predict depression levels in individuals using data on lifestyle, work conditions, and demographic factors. The workflow involves exploratory data analysis (EDA), preprocessing, feature engineering, and classification modeling.

## Project Overview

The primary goal is to classify individuals as **Depressed** or **Not Depressed** based on responses to survey data. The project includes the following steps:

1. **Data Loading and Initial Checks**  
2. **Exploratory Data Analysis (EDA)**  
3. **Data Preprocessing and Feature Engineering**  
4. **Modeling and Evaluation**

## Workflow

### 1. Data Loading and Initial Checks
- The dataset contains 11 columns:
  - **Categorical Features:** Gender, sleep duration, dietary habits, family history of mental illness, suicidal thoughts, etc.
  - **Numerical Features:** Age, work pressure, job satisfaction, work hours, and financial stress.
- The data was checked for missing values, inconsistencies, and proper column formatting.  
- There were no missing values or inconsistencies in the original dataset.

---

### 2. Exploratory Data Analysis (EDA)
Key insights from EDA include:
- **Age Distribution**: Majority of individuals were aged between 30 and 60.  
- **Class Imbalance**: About 10% of the data represents depressed individuals.
- **Correlations**:
  - Age had weak correlations with other features.
  - Work-related variables such as job satisfaction and work hours showed no strong correlation with depression.  
- **Visualization Techniques**:
  - Histograms and bar charts were used to explore feature distributions.
  - A heatmap was employed to visualize correlations among numerical features.

---

### 3. Data Preprocessing and Feature Engineering
Steps performed during preprocessing:

- **Encoding Categorical Variables**:
  - Applied one-hot encoding to categorical variables (e.g., gender, dietary habits).
  - Binary columns like "Yes/No" responses were encoded into 0/1.  
- **Feature Engineering**:
  - **Age Grouping**: Grouped age into bins (`18-30`, `31-45`, `46-60`, `61+`) for better interpretability.
  - **Sleep Duration Transformation**: Converted sleep categories into numerical averages:
    - `7-8 hours` → 7.5
    - `5-6 hours` → 5.5, etc.  
- **Final Features**:
  - Dropped redundant columns like `age` after creating `age_group`.  

---

### 4. Modeling and Evaluation
Several machine learning models were trained and evaluated for depression prediction:

#### **1. Logistic Regression**
- Served as a baseline model for binary classification.

#### **2. Decision Tree Classifier**
- Highlighted feature importance and interactions.

#### **3. Random Forest Classifier**
- Improved accuracy using ensemble learning.

#### **4. XGBoost Classifier**
- Applied gradient boosting for the best predictive performance.

---

### Model Evaluation Metrics:
- **Accuracy**: Overall correctness of predictions.
- **Precision**: Correctly identified positive cases.
- **Recall**: Ability to find all depressed individuals.
- **F1 Score**: Balanced measure of precision and recall.
- **ROC AUC Score**: Evaluated model performance across classification thresholds.

### Results:
- The **XGBoost Classifier** outperformed all other models with the best ROC AUC and balanced metrics, making it the most effective for depression prediction.

---

## Results and Conclusion
The project demonstrated that:
- **Lifestyle features**, such as sleep duration and dietary habits, are significant predictors of depression.
- Work-related variables (e.g., work hours and job satisfaction) showed limited impact on depression prediction.
- Advanced models like **XGBoost** significantly outperform simple models like logistic regression in capturing subtle patterns in the data.

---

## How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/Al-aameen/ml_zoomcamp/tree/main/midterm%20assignment
   ```
2. Navigate to the project directory:
   ```bash
   cd depression-prediction
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Open and execute the notebook:
   ```bash
   jupyter notebook midterm.ipynb
   ```