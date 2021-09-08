# Description

The wine dataset contains the results of a chemical analysis of wines grown in a specific area of Italy. Three types of wine are represented in the 178 samples, with the results of 13 chemical analyses recorded for each sample. The Type variable has been transformed into a categoric variable.

The data contains no missing values and consits of only numeric data, with a three class target variable (Type) for classification.

# Machine Learning Model

The RandomForestClassifier was used and presented an accuracy of 97.78%.
~~~python
print("Accuracy score is {:.2f}%\n".format(accuracy_score(y_test, pred)*100))
~~~
Accuracy score is 97.78%

## Classification Report
~~~python
(classification_report(y_test,pred)
~~~
  precision   |   recall  |  f1-score  |   support
:---------------------------:|:----------------------------:|:---------------------------:|:-----------------------------:
 0     |    0.95    |    1.00     |   0.97     |   18
 1     |    1.00    |    0.94    |    0.97    |     17
 2    |    1.00   |    1.00    |    1.00    |     10
accuracy     |             |            |   0.98   |    45
macro avg   |      0.98    |    0.98    |    0.98    |    45
weighted avg    |     0.98    |    0.98   |    0.98    |    45


## Confusion Matrix

~~~python
sns.heatmap(confusion_matrix(y_test, pred), annot=True, cmap = 'Blues')
~~~  


![confusion_matrix](https://user-images.githubusercontent.com/83030060/132532139-93eba986-bb79-4e6e-942e-424dbec0d7d6.jpg)

## Feature Importances
~~~python
sns.barplot(x = x_test.columns, y = rfc.feature_importances_)
plt.xticks(rotation = 90)
plt.show()
~~~

![feature_importances](https://user-images.githubusercontent.com/83030060/132532453-cf160b5a-022e-4ff1-9fad-ac4f79811228.jpg)
