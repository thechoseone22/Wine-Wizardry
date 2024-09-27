# Wine-Wizardry
Project 2 - Brianna, Derek, Eric, Josh
# Wine Quality Prediction Using Random Forest Model

## Project Overview

This project involves building a machine learning model to predict the quality of wine based on its chemical properties. 
The dataset includes both **red and white wine** samples, with features like acidity, sugar content, alcohol, and more. 
The project uses **Random Forest Classifier** to predict the wine's quality score, with additional efforts to improve model accuracy.

---

## Table of Contents
1. [Dataset](#dataset)
2. [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
3. [Model Used](#model-used)
4. [Improvement Strategies](#improvement-strategies)
5. [Evaluation Metrics](#evaluation-metrics)
6. [Conclusion](#conclusion)

---

## Dataset

The dataset used in this project contains information on both **red** and **white** wines, with several chemical attributes typically 
found in the wine fermentation process.

- **Features**: 
  - `fixed acidity`
  - `volatile acidity`
  - `citric acid`
  - `residual sugar`
  - `chlorides`
  - `free sulfur dioxide`
  - `total sulfur dioxide`
  - `density`
  - `pH`
  - `sulphates`
  - `alcohol`
  - **Wine Type**: (red/white)
  
- **Target**: 
  - `quality` (wine quality score ranging from 3 to 8)

---

## Data Cleaning and Preprocessing

Before building the model, several data cleaning and preprocessing steps were applied:

1. **Missing Values**: No missing values were found in the dataset.

2. **Encoding**: 
   - The **Wine Type** feature (categorical) was converted into binary values (`0` for red wine, `1` for white wine).

3. **Train-Test Split**: 
   - The dataset was split into training (80%) and testing (20%) sets.

4. **Scaling**: 
   - Feature scaling was considered but not necessary for Random Forest as it is less sensitive to unscaled features.

---

## Model Used

The primary machine learning model used was the **Random Forest Classifier**. It was chosen for its ability to handle a large 
number of features and its robustness against overfitting due to its ensemble nature.

### Hyperparameters:
- **n_estimators**: 200
- **max_depth**: 20
- **min_samples_split**: 5
- **min_samples_leaf**: 2
- **class_weight**: 'balanced'

---

## Improvement Strategies

Efforts were made to improve the model's performance:

1. **Hyperparameter Tuning**:
   - A **GridSearchCV** was conducted to find the best hyperparameters.

2. **Handling Class Imbalance**:
   - The dataset was imbalanced, so `class_weight='balanced'` was used to ensure the model does not favor the majority class.

3. **Feature Importance**:
   - Feature importance analysis identified the most significant attributes. This helps in future iterations where less important features may be dropped.

4. **Alternative Models**:
   - Other models, such as **Linear Regression** and **XGBoost**, were tested. However, Random Forest provided the best results.

---

## Evaluation Metrics

The model performance was evaluated using the following metrics:

1. **Accuracy**:
   - The Random Forest model achieved an accuracy of **65%** on the test data.

2. **Confusion Matrix**:
   - A confusion matrix visualized the distribution of correct and incorrect predictions across quality levels.

3. **Classification Report**:
   - Precision, recall, and F1-score were calculated for each class (wine quality levels).

---

## Conclusion

The **Random Forest Classifier** provided a reasonable accuracy of **65%** for predicting wine quality based on the chemical properties of the wine. 
Potential improvements include:

- Further hyperparameter tuning.
- Collecting more balanced data.
- Exploring advanced models like **Gradient Boosting** or **SVM**.

---

## Future Work
- Apply **Stacking** or **Ensemble** methods to combine multiple models.
- Explore the impact of additional domain-specific features such as wine origin.

