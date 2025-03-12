# Classification model - Predicting if a client will be leaving the telecom company

## Objective
The goal is to explore 3 different classification models to predict if a client will be leaving a fictional telcom company 'churning'. A thorough analysis will be performed in order to select one model that predict the churning the most accurately. The most accurate model will be tested against the fictional telecom company's model.


### Data source
Here is the fictional data source [dataset](churn.xlsx) used and more info about the dataset can found here:

- [ibm](https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/11/telco-customer-churn-1113)

---
### Step 1: Data Cleaning,

Data cleaning is crucial for data analysis. The cleaned data can be found here [Cleaned Dataset](data/churn_cleaned.xlsx)

1. Columns with information not needed for the analysis will be discarded
2. Similar terms in a column will be replaced.
3. Missing values will be replaced or discarded.

---
### Step 2 : Data Analysis

Data Analysis is necessary to understand 
   - the dataset
   - the various trends
   - the distribution
   - the range
     
of the various information available in the dataset.

The investigation of the churn value with all the type of data available in the dataset will provide us information of the utmost importance about the most suitable predictors in our classification model.


---
### Step 3 : Feature Engeneering

Most classification models can only accept numeric values. Therefore, feature engineered is a crucial step to transform categorical columns into numerical columns.  The featured engineered data can be found here [Engineered Dataset](data/churn_cleaned_featEng.xlsx)

In addition, this is where we will be finding the correlation of the predictors with 'Churn Value' and trying to see which predictors are the best for our classification model. 

Two methods will be use and compared to find the best predictors:
1. Retaining the highest correlated data in regards of Churn Value
2. Using SelectKBest from the Scikit Learn module to find the best predictors

The best predictors will be used to find the best suitable classification model for the Logistic Regression model only. 

---
### Step 4 : Classification Models

Four classification models will be compare. Here are the three types of classification model we will be trying.

1. Logistic Regression model
2. K-Nearest Neighbor model 
3. Random Forest model
4. Decision Tree Classifier model

All modules originate from the SciKit Learn module.

---
### Step 5 : Validation of the Regression Models
A simple cross-validation technique, "The Train - Test Split", was used to evaluate our models performance.
</br>
Each model was train on 70% of the dataset, while it was tested on 15% of the dataset. Only two selected models (Random Forest model, Decision Tree Classifier) were validated on the remaining 15% of the dataset.
</br>
</br>
The following performance score were calculated for each models :

**Precision**: The proportion of true positive predictions out of all positive predictions.
</br></br>
**Recall**: The proportion of true positive predictions out of all actual positive instances.
</br></br>
**F1-score**: The harmonic mean of precision and recall, balancing both metrics.
</br></br>
**Support**: The number of actual occurrence.
</br></br>
**Accuracy**: The number of all correct predictions divided by the total number of the dataset.
</br></br>
**balanced_accuracy**: The arithmetic mean of sensitivity and specificity, and it is used when dealing with imbalanced data.
</br></br>

---
### Step 6 : Validation of the selected Classification Models
---
More detailed results can be found here [Results](Notebook/Results.md)


The accuracy is not the only scores that matters. As seen during this project, the scoring method best suited to optimize a Classification model is really dependent on the goal that the model need to achieve.

In this case, the client wanted to forecast the hit event the most accurately while minimizing the missed event. Therefore, a scoring method that would have balanced the dataset and try to find the best model that tend to have 0 False Negative, while optimizing the balanced accuracy would have been the best scoring method for this project.

![Confusion Matrix](../graph/tempo.png)
</br></br>

It is a lesson learn that a model with the most accuracy does not always provide the best forecast.

We were not able to provide a better model than the pre-existing model used to produce the Churn Score and suit better the client's needs.


| Balanced Model</br>DecisionTreeClassifier              | Balanced Model</br>Random Forest                  | Client pre-existing model</br> Churn Score               |
|-----------------------|-----------------------|-----------------------|
| ![Confusion Matrix Balanced Model](../graph/ConfusionMatrix_val_BalancedModel.png) | ![Confusion Matrix Best Model](../graph/ConfusionMatrix_val_BestModel1.png) |  ![Confusion Matrix Balanced Model](../graph/ConfusionMatrix_val_ChurnScore.png) | 

</br></br></br>
<center>
    
####  Balanced Model (DecisionTreeClassifier)

</center>

| Metric       | Precision | Recall | F1-Score | Support |
|-------------|:---------:|:------:|:-------:|:-------:|
| **Class 0** | 0.93     | 0.72   | 0.81    | 538     |
| **Class 1** | 0.47     | 0.83   | 0.60    | 166     |
| **Accuracy**| -        | -      | 0.74    | 704     |
| **Macro Avg** | 0.70    | 0.77   | 0.71    | 704     |
| **Weighted Avg** | 0.82 | 0.74   | 0.76    | 704     |


</br></br>
<center>
    
####  Balanced Model (Random Forest)

</center>

| Metric       | Precision | Recall | F1-Score | Support |
|-------------|:---------:|:------:|:-------:|:-------:|
| **Class 0** | 0.86     | 0.91   | 0.88    | 538     |
| **Class 1** | 0.64     | 0.50   | 0.56    | 166     |
| **Accuracy**| -        | -      | 0.82    | 704     |
| **Macro Avg** | 0.75    | 0.71   | 0.72    | 704     |
| **Weighted Avg** | 0.80 | 0.82   | 0.81    | 704     |

</br></br>
<center>
    
####  Client Pre-existing Model (Churn Score)

</center>

| Metric       | Precision | Recall | F1-Score | Support |
|-------------|:---------:|:------:|:-------:|:-------:|
| **Class 0** | 1.00     | 0.49   | 0.65    | 538     |
| **Class 1** | 0.37     | 1.00   | 0.55    | 166     |
| **Accuracy**| -        | -      | 0.61    | 704     |
| **Macro Avg** | 0.69    | 0.74   | 0.60    | 704     |
| **Weighted Avg** | 0.85 | 0.61   | 0.63    | 704     |

</br></br>




    





