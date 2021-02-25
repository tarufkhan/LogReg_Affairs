# Logistic Regression on Extra Marital Affairs dataset
### Aim - To predict whether a woman had an extra marital affair or not, using Logistic Regression.
### Brief about dataset -
The dataset is the affairs dataset that comes with Stats models. It was derived from a survey of women in 1974 by Red book magazine, in which married women were asked about their participation in extramarital affairs. Treating this as a classification problem and trying to predict the classification for each woman. Variables that are present in the dataset for prediction are :-
* rate_marriage(women’s rating for her marriage)
* age(women’s age)
* yrs_married(number of years married)
* children(no. of children she has)
* religious(on the scale of 1 -5 whether she believe in religion or not)
* education(level of education)
* occupation(of women)
* occupation(of husband)
* affairs
### Required libraries / modules -
1. Pandas 
2. Numpy
3. Sklearn
4. Statsmodels
5. Matplotlib
6. Seaborn
7. Patsy
8. Imblearn
9. Warnings
### Workflow & results-
* Import all the required libraries and modules.
* Load dataset from the statsmodels library. 
* Shape of the dataset is (6366, 9), has no null values.
* Also, Generate descriptive statistics.
* Now, convert affairs column into binary values so that we can treat this as a classification problem and predict whether the woman had an affair or not.
* Use patsy.dmatrices, it’s main task is to analyze the independent variable and dependent variable and add some data if it is needed based on the target variable. This changes the shape of the dataset (6366, 18).
* Now, rename the features generated after patsy so that it will be easy to work.
* Check null values and also look whether the dataset is balanced or not.
* On checking for the balance in the dataset we get this result.
![screenshot1](/img/log1.PNG)
* As the dataset is highly imbalanced so we will use RandomOverSampler to balance the dataset. On performing that we got this.
![screenshot2](/img/log2.PNG)
* After balancing the dataset, our rows have increased but there are no null values.
* Shape of the dataset (8626, 18).
* Now plot the data distribution and perform outlier detection. Observing the results we get that there are no such outliers to care about.
![screenshot3](/img/log3.PNG)
* Here now, we dropped some columns, named = 'Intercept', 'occ_1', 'occ_2', 'occ_3', 'occ_4', 'occ_5', 'occ_husb_2', 'occ_husb_3', 'occ_husb_4', 'occ_husb_5', 'occ_husb_6'. And plot how other independent variables are affecting the dependent variable.
![screenshot4](/img/log4.PNG)
* Prepare data for the model, apply Standard Scaler and train_test_split.
* On checking the VIF values, the results are in normal range.
* Fit data into Logistic Regression and start the prediction.
* Our values of Evaluation Metrics for this problem are : -
  * Accuracy - 0.6852109411219286
  * Precision - 0.6974789915966386
  * Recall - 0.677858439201452
  * F1 Score - 0.6875287620800736
  * Specificity - 0.6928909952606636
  * AUC - 0.6852956652274168
* And the Confusion Matrix -
![screenshot5](/img/log5.PNG)
* Lastly, the AUC ROC curve is -
![screenshot6](/img/log6.PNG)
* We can also give some new values to check what our model might predict.
