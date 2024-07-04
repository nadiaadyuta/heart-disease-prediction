
# Heart Disease Prediction using Random Forest Classifier



## Project Overview

Heart disease is a major health problem worldwide and early prediction can significantly improve treatment outcomes. This project is leveraging Random Forest classifier to predict the existence of heart disease according to various health indicators.



## Dataset
This dataset contain some medical information of patients which tells whether that person has heart disease or not. It contains 1025 observations with 14 attributes.
- age: Age of the patients in years
- sex: Gender of the patient, which 0: Female and 1: Male
- cp: Type of chest pain felt by the patient, which 0: Typical chest pain; 1: Non-typical chest pain; 2: Chest pain not associated with angina; 3: No chest pain
- trestbps: Patient's resting blood pressure (mmHg).
- chol: The patient's serum cholesterol level (mg/dl)
- fbs: The patient's fasting blood sugar level, which 0: Fasting blood sugar level <120 mg/dl; 1: Fasting blood sugar level >120 mg/dl
- restecg: Resting electrocardiography result, which 0: Normal result; 1: ST-T wave abnormality (invert or ventricular hypertrophy); 2: Indicates possible left ventricular hypertrophy according to Estes criteria
- thalach: Maximum heart rate reached by the patient.
- exang: Presence of exercise-induced angina, which 0: No exercise-induced angina; 1: Exercise-induced angina present
- oldpeak: ST segment depression produced by exercise relative to rest
- slope: The slope of the ST segment during exercise, which 0: Slope is irrelevant; 1: Slope is up; 2: Slope is down
- ca: Number of major blood vessels stained with flourosopy staining, values are 0-3
- thal: Type of thalassemia, which 0: Normal; 1: Fixed defect; 2: Reversable defect
- target: A class label indicating whether or not the patient has heart disease, which 0: No heart disease; 1: Heart disease.


## Data Preprocessing

### Data Cleaning
- **Missing Value**: There are no missing values in the dataset
- **Invalid Data**: Handle invalid data in column *ca* by dropping and column *thal* by doing adjustments according to the analysis
- **Duplicated Data**: There are more than 50% of data duplicates that might happen because the Heart Disease dataset doesn't have a patient id or name as a unique identifier. So, no handling is needed to keep the number of datasets.
- **Outliers**: In case of medical data, outliers are possible to occur due to significant differences in patients' health conditions so that the information is important for the modeling process. Therefore, outliers are ignored.

### Exploratory Data Analysis (EDA)
- The majority of patients diagnosed with heart disease have a cholesterol level at 240 mg/dl and a maximum heart rate reached 162 bpm.
- The average age of patients with heart disease is 52-53 years old.
- There were 86 female patients and 410 male patients diagnosed with no heart disease. Meanwhile, 226 female and 285 male patients were diagnosed with heart disease.
- There are significant differences in the proportion of targets among the gender groups.

### Feature Engineering
- **Features Creation**: Blood pressure and cholesterol category
- **Feature Encoding**: Using one hot encoding on new features
- **Feature Selection**: Drop features blood pressure and cholesterol category because there are encoded features already

## Modelling
- **Initial Model**: Random Forest Classifier with default parameter
- **Cross Validation**: Model correctly identified 96% of all actual heart disease cases in the dataset
- **Learning Curve**: The train data reached an accuracy score of 1, indicating that the model might be too complex or overfitting.
- **Hyperparameter Tuning**: Using a 'RandomizedSearchCV' and resulted in a possible best score of 95%
- **Final Model**: Random Forest Classifier with tuning result parameter
- **Confussion Matrix**: There were 11 patients diagnosed with no heart disease when they actually had heart disease. This kind of misdiagnosis can be fatal as it puts the patient's life at risk
- **Evaluation Metric**: Using a recall metric that measures the ability of the model to correctly identify all true positive cases, resulted in an accuracy of 95%


## Acknowledgements

 - The dataset is sourced from [Kaggle](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset)
