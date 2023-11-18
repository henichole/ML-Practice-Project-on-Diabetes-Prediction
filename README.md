# ML-Practice-Project-on-Diabetes-Prediction

>The project started with a diabetes dataset containing various predictors like 'Pregnancies', 'Glucose', 'BloodPressure', etc., and an 'Outcome' variable. The goal of this project is to use machine learning algorithms to predict the 'Outcome' variable using other variables.

>Part I: EDA - Exploratory Data Analysis

1. Initial EDA was conducted to understand data distributions, relationships between variables, and presence of missing values.
2. Key findings included no missing values and certain relationships between predictors and the outcome.
3. Identified implausible zero values in 'SkinThickness', 'BloodPressure', 'BMI', and 'Insulin'.
4. Implemented median imputation to address these zeros.

>Part II: Data Preprocessing & Feature Engineering

Handling Implausible Zero Values:
1. Explored creation of new features and transformations.
2. Recognized the need to address data imbalance, considering techniques like SMOTE.

Initial Model Training:
1. Trained Logistic Regression and RandomForest models.
2. Evaluated using metrics like accuracy, precision, recall, F1-score, and ROC-AUC.

Model Performance Issues:
1. Both models initially showed suboptimal performance.
2. Implemented RandomForest hyperparameter tuning using GridSearchCV.

>Part III: Training ML Model and Bug Fix

Step 1: Identification of a Critical Issue:
1. Realization of Data Leakage:
2. Realized that data preprocessing steps were applied before splitting the dataset into training and testing sets.
3. Acknowledged this as a violation of the golden rule of machine learning, potentially leading to data leakage and overestimated model performance.

Step 2: Resolving the Splitting Order Issue:
1. Correcting Data Splitting Order:
2. Revised the process to first split the data and then apply preprocessing steps like imputation and scaling separately on training and testing sets.
3. Ensured that information from the test set did not influence the training process, thus maintaining the integrity of the evaluation.

Step 3: Model Re-evaluation:
1. Retraining Models with Corrected Process:
2. Models were retrained using the revised approach.
3. Performance metrics were recalculated to reflect true model efficacy.
4. Exploration of Additional Models: Explored GBM and SVM models for potential improvements in prediction accuracy.

Step 4: Final Observations:
1. Enhanced Model Performance: Post-adjustment, models showed more reliable performance metrics.
2. Importance of Correct Data Handling: Emphasized the importance of correct data handling and preprocessing order in machine learning.
3. Continuous Learning and Improvement: See conclusion section in "Supervised Learning - Project copy" File.

> Part IV: Results Intepretation

Evaluation Metrics Overview:
Accuracy: 77%
Precision: 79% for class 1 (Diabetes Positive)
Recall: 54% for class 1
F1 Score: 64% for class 1
ROC AUC Score: 72.4%

1. Accuracy: At 77%, the model correctly predicts the outcome in about 3 out of 4 instances. This is a moderate level of accuracy, indicating reasonable predictive power.
Precision and Recall:
2. A precision of 79% for the positive class suggests that when the model predicts diabetes, it's correct about 79% of the time.
3. The recall of 54% indicates that the model correctly identifies 54% of all actual diabetes cases. This suggests there's room for improvement, as almost half of the positive cases are being missed.
4. F1 Score: The F1 score, which balances precision and recall, is at 64%. This is moderate, reflecting the trade-off between precision and recall in your model.
5. ROC AUC Score: The ROC AUC score of 72.4% indicates a good ability to discriminate between the positive and negative classes. However, there is still potential for improvement, as a score closer to 100% is ideal.

The balance between precision and recall could be further optimized. A higher recall would mean better identification of actual positive cases, which is often crucial in medical predictions. The ROC AUC score suggests the model has a good degree of separability power, but again, it's not in the high-excellence range.

>Recommendations for Increased Confidence & Last Words to Improve:

1. Advanced Feature Engineering: Revisit the features to see if more informative features can be created, or if different transformations could yield better results.

2. Cross-Validation: Use cross-validation techniques to ensure the model's performance is consistent across different subsets of the data.