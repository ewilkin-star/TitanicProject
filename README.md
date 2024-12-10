# Titanic Final Project Model Card

### Basic Information

* **Person or organization developing model**: Kevynne Callwood, 'callwoodk25@gwu.edu'; Masha Krukow, 'masha.krukow@gwmail.gwu.edu'; Maya Serna, 'mayalserna@gwmail.gwu.edu'; Elias Wilkin, 'ewilkin1@gwmail.gwu.edu' 
* **Model date**: December, 2024
* **Model version**: 0.1
* **License**: MIT
* **Model implementation code**: [INSERT LINK]

### Intended Use
* **Primary intended uses**: Educational purposes (students learning about machine learning.)
* **Primary intended users**: Students in GWU DNSC 3288_10, or people learning about machine learning.
* **Out-of-scope use cases**: Everything that exists outside of educational purposes.

### Training Data

* Data dictionary: 

| **Name**         | **Modeling Role**     | **Measurement Level** | **Description**                                                                 |
|-------------------|-----------------------|------------------------|---------------------------------------------------------------------------------|
| **PassengerID**   | ID                   | Nominal               | Unique identifier for each passenger.                                          |
| **Survived**      | Target               | Binary                | Indicates if the passenger survived (0 = No, 1 = Yes).                         |
| **Pclass**        | Predictor            | Ordinal               | Ticket class, representing socioeconomic status (1 = 1st, 2 = 2nd, 3 = 3rd).   |
| **Name**          | Predictor            | Nominal               | Full name of the passenger.                                                    |
| **Sex**           | Predictor            | Nominal               | Passenger's sex (male or female).                                              |
| **Age**           | Predictor            | Interval              | Passenger's age in years.                                                      |
| **SibSp**         | Predictor            | Ratio                 | Number of siblings/spouses aboard the Titanic.                                 |
| **Parch**         | Predictor            | Ratio                 | Number of parents/children aboard the Titanic.                                 |
| **Ticket**        | Predictor            | Nominal               | Alphanumeric ticket number.                                                    |
| **Fare**          | Predictor            | Ratio                 | Passenger fare in currency.                                                    |
| **Cabin**         | Predictor            | Nominal               | Cabin number (alphanumeric, may contain missing values).                       |
| **Embarked**      | Predictor            | Nominal               | Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton).          |

* **Source of training data**: Kaggle: “Titanic - Machine Learning from Disaster” https://www.kaggle.com/competitions/titanic/data
* **How training data was divided into training and validation data**: 80% training data, 20% validation data. We also used a random seed of 1 to ensure that the split stayed consistent throughout the model building process.
* **Number of rows in training and validation data**:
  * Training rows: 712
  * Validation rows: 179

### Test Data
* **Source of test data**: Kaggle: “Titanic - Machine Learning from Disaster” https://www.kaggle.com/competitions/titanic/data
* **Number of rows in test data**: The test dataset contains 418 rows, representing 418 passengers.
* **State any differences in columns between training and test data**: The survival (target variable) column is absent in the test dataset. This is because the purpose of the test data is to predict survival outcomes using the model trained on the training data. Each other column remains the same.


### Model details
* **Columns used as inputs in the final model**: 'Age', 'Fare', 'Sex_male' (dummy variable for the "Sex" column), 'Pclass_3' (dummy variable for class 3 in the "Pclass" column)
* **Column(s) used as target(s) in the final model**: 'Survived'
* **Type of model**: Random Forest Classifier
* **Software used to implement the model**: Python; Libraries: sklearn (scikit-learn), pandas, and numpy
* **Version of the modeling software**:
  * Python: 3.10.12
  * scikit-learn: 1.5.2
  * pandas: 2.2.2
  * numpy: 1.26.4
  * matplotlib: 3.8.0

* **Hyperparameters or other settings of your model**: 
```
RandomForestClassifier(max_depth=6,
                       min_samples_split=40,
                       random_state=1)
```
### Quantitative Analysis

* Model Accuracy

| Train Accuracy | Validation Accuracy | Test Accuracy |
| -------------- | ------------------- | ------------- |
| 0.85534        | 0.75978             | 0.78229       |

* Model AUC

| Training AUC | Validation AUC |
|--------------|----------------|
| 0.91887      | 0.83309        |

(*Test AUC taken from 
(*Test AUC taken from https://github.com/jphall663/GWU_rml/blob/master/assignments/model_eval_2023_06_21_12_52_47.csv)

* ROC Curve

![image](https://github.com/user-attachments/assets/5c49f69e-df93-4e2a-9b6a-7e8c2f24adc8)

* Model AIR

| Group | Validation AIR |
|-------|-----|
| Black vs. White | 0.8345 |
| Hispanic vs. White | 0.8765 |
| Asian vs. White | 1.098 |
| Female vs. Male | 1.245 |






