Mental Health in Tech - Analysis & Modeling
Problem Statement

Identify factors influencing whether a tech professional develops mental health issues and seeks treatment.

Motivation

The tech industry is known for high stress and burnout.

Early identification of factors influencing mental health can help employers design better interventions and wellness programs.

This project analyzes survey data to explore these factors and build predictive models.

Dataset

Source: OSMI Mental Health in Tech Survey

Description: Survey of tech professionals including demographic, workplace, and mental health-related information.

Columns Include: Age, Gender, family_history, treatment, work_interfere, no_employees, remote_work, tech_company, benefits, care_options, wellness_program, seek_help, anonymity, leave, mental_health_consequence, phys_health_consequence, coworkers, supervisor, mental_health_interview, phys_health_interview, mental_vs_physical, obs_consequence, comments.

Preprocessing & Cleaning

Dropped unnecessary columns: Timestamp, state, comments, self_employed, Country.

Filled missing values for work_interfere with "Don't know".

Standardized Gender to Male, Female, Other.

Filtered invalid Age values (0–100) and removed duplicates.

Encoded categorical columns using LabelEncoder.

Converted treatment to a binary target for classification and probability target for regression.

Exploratory Data Analysis (EDA)

Visualized distributions of key features.

Analyzed correlations between workplace factors and mental health treatment.

Explored demographic trends, work interference, and employee counts.

Modeling
Regression

Target: Probability of seeking treatment (treatment_prob)

Models Used:

Linear Regression

Decision Tree Regressor

Random Forest Regressor

Performance:

Decision Tree and Random Forest regressors achieved perfect R² = 1.0 (overfit indication)

Classification

Target: treatment (Yes = 1, No = 0)

Models Used:

Logistic Regression

Decision Tree Classifier

Random Forest Classifier

Best Accuracy:

Logistic Regression: 0.792

Decision Tree: 0.784

Random Forest: 0.80

Confusion matrices and evaluation metrics (Precision, Recall, F1-Score) used for model assessment.

Hyperparameter Tuning

GridSearchCV used for Decision Tree Classifier.

Best parameters found:

{'criterion': 'entropy', 'max_depth': 5, 'max_features': None, 'min_samples_leaf': 4, 'min_samples_split': 2}

Best cross-validated accuracy: 0.814

Visualizations

Confusion matrices for classification models.

Decision Tree visualization showing feature splits and importance.

Tools & Libraries

Python 3.x

pandas, numpy, matplotlib, seaborn

scikit-learn (preprocessing, modeling, evaluation)

ucimlrepo (optional for dataset access)

Insights

Workplace size, family history, and work interference are strong indicators of whether a professional seeks treatment.

Decision Trees and Random Forests can overfit regression targets if not carefully tuned.

Logistic Regression provides a simple and interpretable model for classification tasks.
