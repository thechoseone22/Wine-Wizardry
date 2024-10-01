# Wine-Wizardry: Machine Learning for Wine Quality Prediction
**Team Members**: Brianna, Derek, Eric, Josh  
**Project 2**

## Project Overview
Our project aims to build a **machine learning model** that predicts **wine quality** based on its chemical properties. Using both **red and white wine datasets**, we sought to classify wines into **quality categories** and identify the key factors that affect wine quality. We primarily used the **Random Forest Classifier**, which achieved an accuracy of over **85%** when classifying wines into quality classes.

## Download
- Please download the datasets from the Red & white wine datasets folder above to use our datasets. We apologize if there are absolute paths for csv file access in our notebooks, please use relative paths to access them if needed, thank you.

### Key Goals
1. Predict wine quality (Poor, Acceptable, or High) based on chemical attributes.
2. Classify wine type as either red or white.
3. Identify which features (acidity, alcohol, etc.) most influence wine quality.

---

## Table of Contents
1. Dataset
2. Data Cleaning & Preprocessing
3. Model Selection & Optimization
4. Evaluation Metrics
5. Results & Conclusions
6. Future Work

---

## 1. Dataset
We used two wine datasets containing **chemical attributes** for red and white wines. Each wine was scored for quality, ranging from **3 to 8**.

### Features:
- **Fixed Acidity**
- **Volatile Acidity**
- **Citric Acid**
- **Residual Sugar**
- **Chlorides**
- **Free Sulfur Dioxide**
- **Total Sulfur Dioxide**
- **Density**
- **pH**
- **Sulphates**
- **Alcohol**
- **Wine Type** (Red or White)

### Target:
- **Quality Score** (from 3 to 8)

---

## 2. Data Cleaning & Preprocessing

### Key Steps:
1. **No Missing Values**: The dataset was clean, with no missing entries.
2. **Encoding**:  
   - Wine Type was encoded into binary values (0 for Red, 1 for White).
3. **Train-Test Split**:  
   - Dataset split into **80% training** and **20% testing** sets.
4. **Feature Scaling**:  
   - Although Random Forest doesn't strictly require scaling, **StandardScaler** was applied for consistency.
   
---

## 3. Model Selection & Optimization

### Random Forest Classifier:
- **Chosen Model**: The Random Forest Classifier was selected for its robustness in handling **non-linear relationships** and **feature importance** evaluation.
- **Initial Models**: We initially tried **Logistic Regression**, but Random Forest consistently delivered better results.

### Hyperparameter Tuning:
- We used **GridSearchCV** to find the best hyperparameters, with the following values:
  - `n_estimators`: 200  
  - `max_depth`: 20  
  - `min_samples_split`: 5  
  - `min_samples_leaf`: 2  
  - `class_weight`: 'balanced' (to handle the slight class imbalance in quality scores)

### Improvement Strategies:
1. **Feature Engineering**:  
   - We introduced a **Quality Class** (Low, Medium, High) to better categorize wine quality. This led to an improved accuracy of **85%**.
2. **Feature Importance**:  
   - Identified key features like **volatile acidity** and **citric acid** that had the most significant impact on wine quality.

---

## 4. Evaluation Metrics
The following metrics were used to evaluate the performance of the model:

- **Accuracy**:  
  - Achieved **85%** accuracy for classifying wines into **Quality Classes** (Low, Medium, High).
- **Confusion Matrix**:  
  - Visualized the performance across different quality levels.
- **Classification Report**:  
  - Precision, recall, and F1-score were calculated for each class.

---

## 5. Results & Conclusions
- **Random Forest Model** (with Quality Classes):
  - Achieved **85% accuracy** for predicting wine quality classes.
  - The **confusion matrix** confirmed that most predictions fell within the correct category (Low, Medium, or High).

- **Red and White Wines Analyzed Separately**:
  - When predicting the **exact quality score** (3-8) without classification, both models achieved accuracy between **65%-70%**.

### Key Findings:
1. **Volatile acidity** and **citric acid** are among the top features influencing wine quality.
2. **Random Forest** outperformed other models in terms of accuracy and feature interpretability.

---

## 6. Future Work
### Additional Questions:
- Could we include more features such as **weather conditions** or **soil quality** to improve predictions?
  
### Future Research:
- Expand the dataset to include **more wine types** and explore external factors (e.g., **region**, **grape variety**).
  
### Development Plan:
- Apply the model to **real-time applications** for winemakers or retailers, like a recommendation application based on wine make-up.

### Data Source: 
- https://www.kaggle.com/datasets/abdullah0a/wine-quality-red-white-analysis-dataset
