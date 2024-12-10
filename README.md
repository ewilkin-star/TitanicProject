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


### Model Details
* **Columns used as inputs in the final model**: 'Age', 'Fare', 'Sex_male' (dummy variable for the "Sex" column), 'Pclass_3' (dummy variable for class 3 in the "Pclass" column)
* **Column(s) used as target(s) in the final model**: 'Survived'
* **Type of model**: Random Forest Classifier
* **Software used to implement the model**: Python; Libraries: sklearn (scikit-learn), pandas, numpy, matplotlib, and seaborn
* **Version of the modeling software**:
  * Python: 3.10.12
  * scikit-learn: 1.5.2
  * pandas: 2.2.2
  * numpy: 1.26.4
  * matplotlib: 3.8.0
  * seaborn: 0.13.2

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
| 0.85534        | 0.75978             | 0.78229*      |

(*Test AUC taken from "titanic_test_data_predictions.csv" when submitted to Kaggle)

* **Model AUC**

| Training AUC | Validation AUC |
|--------------|----------------|
| 0.91887      | 0.83309        |

* ROC Curve

![image](https://github.com/user-attachments/assets/5c49f69e-df93-4e2a-9b6a-7e8c2f24adc8)
* The ROC curve displays the model's performance vs a random classifier (indicated by the grey line)

* **Model AIR**

| Group                    | Validation AIR |
|---------------------------------|---------|
| Female vs. Male                 | 17.6647 |
| 3rd Class vs. 1st & 2nd Classes | 0.3340  |

![image](https://github.com/user-attachments/assets/000810ac-78f1-477b-9850-780c514f274f)
* This chart compares the selection rate between female and male titanic passengers. The plot shows a much higher selection rate for female passengers as opposed to male passengers.

![image](https://github.com/user-attachments/assets/07ba7391-c1a9-4ad7-812b-e9945be571aa)
* This chart compares the selection rate between 3rd class and both 1st/2nd class. The plot shows a higher selection rate for passengers in the 1st and 2nd classes as opposed to 3rd class.

* **Confusion Matrix for Validation Dataset**

![image](https://github.com/user-attachments/assets/a52b97f9-34f7-4666-a014-76806436dc34)
* The confusion matrix shows the model's True Positives, True Negatives, False Positives and False Negatives

* **Feature Importance Plot**

![image](https://github.com/user-attachments/assets/b6e454c7-3c65-4494-bcbd-a7d45b697028)
* The feature importance plot shows the most important features the model takes into account when creating predictions. It shows that sex is the most important feature considered.

* Precision-Recall Curve

![image](https://github.com/user-attachments/assets/2691d409-cd91-4644-acb3-01401c445a7d)

* Learning Curve

![image](https://github.com/user-attachments/assets/a1f93f1c-5e04-4efb-bc80-4b94f7bba287)

### Ethical Considerations

* **Potential Negative Impacts**:
  * Python: 3.10.12
  * scikit-learn: 1.5.2
  * pandas: 2.2.2
  * numpy: 1.26.4
  * matplotlib: 3.8.0
  * seaborn: 0.13.2

