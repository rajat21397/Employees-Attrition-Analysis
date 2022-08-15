#  Prediction of Attrition of Employees using Machine Learning 
##  Project Description
The objective of this project is to predict whether an employee will resign or not based on given parameters. Data is analysed, preprocessed and feature engineering was done
before using machine learning algorithms. Different ML algorithms are compared on the basis of accuracy, precision, recall, F1 and ROC scores. Based on these metrics final model 
is selected and its hyperparamaters are tuned using grid search and stratified k-fold cross validation. 

## Data
Data is taken from IBM HR Analytics Employee Attrition & Performance at kaggle https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset/download
The downloaded file is present in Data folder. 

## Exploratory Data Analysis
1. Graphs of features vs. attrition is plotted to examine effect of features on attrition.
2. Histogram of numerical features is used to examine distribution.
3. Plot of attrition distribution shows **highly imbalanced data**.

## Preprocessing and feature engineering
1. Categorical features are encoded using **one hot encoding scheme**.
2. Numerical features with **skewness** value greater than 0.8 are transformed using **log transformation.**
3. Three **new features** viz. tenure per job, years without change and compensation ratio were **created** using existing features.
4. **Irrelevant attributes** viz. EmployeeNumber, EmployeeCount, Over18 and StandardHours were **dropped**.
5. **One hot encoding** is used to transform cardinal categorical features.
6. **Label encoding** is used to transform ordinal categorical features and target labels.
7. Sybthetic Minority Oversampling Technique **SMOTE** is used to tackle data imbalance.
8. **Principal Component Analysis** is used for dimensionality reduction of data.

## ALgorithm tried
1. LogisticRegression
2. SVC
3. DecisionTreeClassifier 	    
4. RandomForestClassifier 	    
5. ExtraTreesClassifier 	      
6. GradientBoostingClassifier 	
7. AdaBoostClassifier 	        
8. GaussianNB 	

## Metrics used
Above models are compared on the basis of following metrics.
1. Accuracy
2. Precision
3. Sensitivity
4. F1
5. ROC

## Performance of various models
| Sr. No. |                      Model |  Accuracy | Precision | Sensitivity | Specificity | ROC Score |
|--------:|---------------------------:|----------:|----------:|------------:|------------:|----------:|
|    1    | LogisticRegression         | 77.966102 | 51.428571 | 66.666667   | 81.318681   | 0.739927  |
|    2    | SVC                        | 85.593220 | 75.000000 | 55.555556   | 94.505495   | 0.750305  |
|    3    | DecisionTreeClassifier     | 78.813559 | 54.545455 | 44.444444   | 89.010989   | 0.667277  |
|    4    | RandomForestClassifier     | 79.661017 | 63.636364 | 25.925926   | 95.604396   | 0.607652  |
|    5    | ExtraTreesClassifier       | 81.355932 | 77.777778 | 25.925926   | 97.802198   | 0.618641  |
|    6    | GradientBoostingClassifier | 83.898305 | 75.000000 | 44.444444   | 95.604396   | 0.700244  |
|    7    | AdaBoostClassifier         | 84.745763 | 73.684211 | 51.851852   | 94.505495   | 0.731787  |
|    8    | GaussianNB                 | 72.033898 | 43.478261 | 74.074074   | 71.428571   | 0.727513  |



Comparison of model on basis of these metrics revealed that random forest can be used as final model for predicting attrition.
After finalising the model, **grid search** over range of hyperparameters is used and models were compared using **stratified k-fold cross validation**.
Feature importance is plotted for the final model.

## Observations
1. From the feature importance it was seen that our engineered features i.e. "TenurePerJob", "CompRatioOverall" and "YearsWithoutChange" have higher importance values compared to many of the other given features. Thus it is concluded that feature engineering was successful.
2. Using SMOTE oversampling helped in improving model's predictions. Earlier models were biased towards predicting majority class only, after using SMOTE this is no longer the case.

