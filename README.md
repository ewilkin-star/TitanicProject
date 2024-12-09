# Credit Line Increase Model Card

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

| **Name**        | **Modeling Role**     | **Measurement Level** | **Description**                                                                 |
|------------------|-----------------------|------------------------|---------------------------------------------------------------------------------|
| **survival**     | target               | binary                | Indicates if the passenger survived (0 = No, 1 = Yes).                         |
| **pclass**       | predictor            | ordinal               | Ticket class, representing socioeconomic status (1 = 1st, 2 = 2nd, 3 = 3rd).   |
| **sex**          | predictor            | nominal               | Passenger's sex (male or female).                                              |
| **age**          | predictor            | interval              | Passenger's age in years.                                                      |
| **sibsp**        | predictor            | ratio                 | Number of siblings/spouses aboard the Titanic.                                 |
| **parch**        | predictor            | ratio                 | Number of parents/children aboard the Titanic.                                 |
| **ticket**       | predictor            | nominal               | Alphanumeric ticket number.                                                    |
| **fare**         | predictor            | ratio                 | Passenger fare in currency.                                                    |
| **cabin**        | predictor            | nominal               | Cabin number (alphanumeric, may contain missing values).                       |
| **embarked**     | predictor            | nominal               | Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton).          |

* **Source of training data**: Kaggle: “Titanic - Machine Learning from Disaster” https://www.kaggle.com/competitions/titanic/data
* **How training data was divided into training and validation data**: 80% training data, 20% validation data. We also used a random seed of 1 to ensure that the split stayed consistent throughout the model building process.
* **Number of rows in training and validation data**:
  * Training rows: 712
  * Validation rows: 179

### Test Data
* **Source of test data**: Kaggle: “Titanic - Machine Learning from Disaster” https://www.kaggle.com/competitions/titanic/data
* **Number of rows in test data**: The test dataset contains 418 rows, representing 418 passengers.
* **State any differences in columns between training and test data**: Survival (Target Variable): The survival column is absent in the test dataset. This is because the purpose of the test data is to predict survival outcomes using the model trained on the training data.

