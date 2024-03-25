This repository has the bank campaign data and the Jupiter notebook of the classification models created to predict the loan conversion


The link to the Jupiter noteboom is https://github.com/praloysinha/Bank_campaigns/blob/main/Praloy_practical_3.ipynb

**Objective:** 

The Business Objective is to evaluate the different classifers like KNN, Logistic Regression, Decision Tree and Support Vector Machines on the bank campaigns dataset in predicting the right classification whether the persons are 
agreeing to the loan offer made in the campaign.


**Approach**

The approach will be to model using these classifiers on the different demographic and campaign data of the persons reached out via telephone from the bank. In this business problem, we should ideally be able to predict as many people who are 
likely to take the loan. Hence **precision score** is very important to monitor and optimize.


**Data Exploration and Preparation**

1. A 10% dataset comprising of 4,119 rows was selected for ML computation which was getting stuck for the entire dataset
2. No missing values were found in the dataset
3. The "no" class is 7 times the "yes" class and hence is greatly imbalanced. We need to balance the data with SMOTE for better modelling
4. Unknown values were imputed for job, marital, education, housing, loan
5. "default", "pdays", "previous", "poutcome", "duration" columns were removed due to a variety of reasons like non - existent values, only single class values and other non- imputable reasons


**Data Encoding and oversampling**

1. Encoded the categorical values and scaled the numerical values
2. Balanced the target class using SMOTE
3. Created the train - test split for modelling


**Baseline target**

1. Created the baseline model using the Dummy Classifier
2. We have to beat a baseline of accuracy of 50.5% and precision of 51.8% of the Dummy Classifier by the other models
3. The accuracy of a simple Logistic Model is 72% and a precision of 78.6%


**Modelling with default hyperparameters**

1. The Decision Tree is reaching the accuracy of almost 90% in accuracy and precision and taking relatively less time as well. SVM also has a good precision of 87% but takes higher time to train.
2. KNN and Logistic regression has precision in higher 70s


**Model Improvement**

1. Grid Search was used to optimise the model which regularized the model for feature selection, reduced complexity for easy comprehension. This was done with hyperparameter tuning
2. Confusuion Matrix, Trees and Support Indices were plotted
3. Logistic Regression coefficients were observed


**Observations:**

1. We can see that KNN has vastly increased its precision from 77% to 85%
2. The Logistic Regression has a similar accuracy at 78% but halved its inference time which means lesser complexity
3. Decision Tree has a similar accuracy of ~90% in comparison to the initial one but the inference time is reduced 4 times
4. SVM has a slight betterment of precision to 88.5% and the inference time has been halved


**Optimized model:**

1. The best model of KNN has a n of 1 which means it is a highly complex model and prone to outliers influence.
2. The Decision Tree best model has a max depth of 5 which is relatively easy to comprehend and does not complicate the model too much
3. The Logistic Regression best model is a highly regularized one wwith C = 0.2 and lasso as penalty and hence will have lesser complexity. Feature selection was automatically done with this highly regularized model
4. The SVC best model is at polynomial degree 5 and is at medium complexity which justifes the reduction in inference time
5. Month of calling, Contact method, Marital status, job type and a couple of indices are important features which affect the loan conversion


**Conclusion:**

1. The data had highly imbalanced classes which had to be balanced and a few values not known which had to be imputed
2. The classifiers provide a much higher performance scores than the base dummy model to predict loan conversion
3. Decision Tree and Support Vector Machines are the best performing classifiers with ~90 % precision scores
4. Logistic Regression provides clarity on the top features which can be actioned upon; however has a lower precision score of 78%
5. KNN has a good 85 % precision but uses a complex model
6. Decision Tree provided clarity through its 5 level tree; however SVM is a litte bit of a black box with only indices information


**Recommendation and next steps:**

1. The bank can use the Decision tree to predict the loan conversion and also understand the features values (from the tree) to be able to action on them
2. Have a look at the top features of the Logistic Regression for better performance focus
3. Rerun the model evaluation every 6 months to understand any potential changes to the parameters

