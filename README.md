# 🧠 Obesity Prediction Project

This project was developed as part of an Artificial Intelligence university workshop. The aim is to train machine learning models that predict an individual's obesity level based on personal, dietary, and lifestyle features. In addition, we explore how factors such as high-calorie food consumption frequency, physical activity, calorie monitoring, vegetable consumption, and water intake impact obesity.

---

## Objective

- **Develop predictive models** (using Linear Regression, Logistic Regression, and Support Vector Machine) to forecast obesity levels.
- **Analyze the impact** of variables such as calorie-dense food consumption, physical activity, and calorie monitoring on obesity.
- **Demonstrate the complete workflow** from data ingestion and preprocessing to model training, evaluation, and visualization.

---

## Project Structure

The project folder contains the following key files:

- **ObesityDataSet.csv** – The dataset with 2111 records.
- **data_preprocessing.py** – Contains functions for loading, cleaning, and preprocessing the data.
- **model.py** – Contains functions for training and evaluating the models.
- **main.py** – The main script that integrates all components and runs the entire process.

This simple structure ensures that all components are directly accessible in one folder, making the project easy to manage and execute.

---

## Methodology

1. **Data Preprocessing**:  
   - **Loading**: Reads 2111 records from the CSV file.  
   - **Cleaning**: Missing numeric values are imputed using the mean, and remaining missing values in categorical variables are filled with a placeholder.  
   - **Encoding**: Categorical variables are transformed into numerical features using One-Hot Encoding.  
   - **Normalization**: Features are normalized using StandardScaler.  
   - **Balancing**: The dataset is balanced with SMOTE to address class imbalance.

2. **Data Splitting**:  
   - The balanced dataset is divided into:
     - **70% for training** (≈1477 records)
     - **25% for testing** (≈528 records)
     - **5% for final evaluation** (≈106 records)
   - Splitting is performed using Scikit-learn's `train_test_split` with a fixed random state.

3. **Model Training & Evaluation**:  
   - **Linear Regression** is used to predict obesity levels.  
   - The model's performance is evaluated using metrics such as **Mean Squared Error (MSE)**, **Mean Absolute Error (MAE)**, and **R² Score** on both test and evaluation sets.
   - For classification approaches, models like **Logistic Regression** and **SVM** are tuned using GridSearchCV and evaluated via accuracy, precision, and confusion matrices.

---

## Visualizations

### Feature Importance

The Linear Regression model's coefficients reveal the importance of each feature. Positive coefficients indicate that an increase in the feature value raises the predicted obesity level, while negative coefficients suggest that higher values reduce it.

![Feature Importance](images/feature_importance.png)

*Figure: Feature Importance Bar Chart showing model coefficients.*

### Regression Results

A scatter plot compares actual obesity levels against the model's continuous predictions for the test set. The red dashed line represents the ideal prediction (y = x).

![Regression Plot](images/regression_plot.png)

*Figure: Actual vs Predicted Obesity Levels*

---

## Evaluation Metrics

- **Mean Squared Error (MSE)**: Measures the average squared difference between actual and predicted values. Lower values indicate a better model.
- **Mean Absolute Error (MAE)**: Represents the average absolute differences.
- **R² Score**: Indicates the proportion of variance in the dependent variable that is predictable from the independent variables.

For example, in our evaluations we obtained:
- MSE on test set: ~0.2023
- MSE on final evaluation set: ~0.1976

These values suggest that the model achieves a low average error.

---

## How to Run the Project

1. **Install Dependencies**

   Ensure you have Python 3.12+ installed. Install required libraries with:

   ```bash
   pip install -r requirements.txt
