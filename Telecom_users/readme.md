# [Description](https://colab.research.google.com/drive/1zxI_aqxLLldGpG0fC4jTNaQwKjRozO2t#scrollTo=Descritption)
Any business wants to maximize the number of customers. To achieve this goal, it is important not only to try to attract new ones, but also to retain existing ones. Retaining a client will cost the company less than attracting a new one. In addition, a new client may be weakly interested in business services and it will be difficult to work with him, while old clients already have the necessary data on interaction with the service.

Accordingly, predicting the churn, we can react in time and try to keep the client who wants to leave. Based on the data about the services that the client uses, we can make him a special offer, trying to change his decision to leave the operator. This will make the task of retention easier to implement than the task of attracting new users, about which we do not know anything yet.

You are provided with a dataset from a telecommunications company. The data contains information about almost six thousand users, their demographic characteristics, the services they use, the duration of using the operator's services, the method of payment, and the amount of payment.

The task is to analyze the data and predict the churn of users (to identify people who will and will not renew their contract). The work should include the following mandatory items:

# [Data Analysis](https://colab.research.google.com/drive/1zxI_aqxLLldGpG0fC4jTNaQwKjRozO2t#scrollTo=Data_Visualization)

## Total Churn Rate
<img src = "https://github.com/MateusFreitas-C/Introduction_SkLearn/blob/main/Telecom_users/graphs/churn_plot.png?raw=true">

## Customers with larger families, married, with dependents and multiple lines, had a lower cancelation rate.

Dependents            |  Partners          | Multiple Lines
:-----------------------------------:|:-----------------------------------:|:-----------------------------------:
<img src = "https://github.com/MateusFreitas-C/Introduction_SkLearn/blob/main/Telecom_users/graphs/dependents_plot.png?raw=true">  |  <img src = "https://github.com/MateusFreitas-C/Introduction_SkLearn/blob/main/Telecom_users/graphs/partners_plot.png?raw=true">  |  <img src = "https://github.com/MateusFreitas-C/Introduction_SkLearn/blob/main/Telecom_users/graphs/multiple_lines_plot.png?raw=true">

## Customers cancel more in the first months and monthly plans had a higher cancellation rate.
Months as Clients            |  Contract
:-----------------------------------:|:-----------------------------------:|
![image](https://user-images.githubusercontent.com/83030060/129968237-819a9330-3a80-4682-834f-a683b0dcacc7.png) | ![image](https://user-images.githubusercontent.com/83030060/129968397-41224a9a-dbb3-4cb3-8581-dfbed00eb8a7.png)

## Services and Payment
- Customers who have more services in their plans had a lower cancellation rate
- Fiber Optic customers had a very high cancellation rate.
- Customers who pay by electronic check had a higher rate of cancellation

Device Protection Service            |  Online Backup Service          | Online Security Service
:-----------------------------------:|:-----------------------------------:|:-----------------------------------:
![image](https://user-images.githubusercontent.com/83030060/129968819-ccb37196-2c77-4b22-bca5-dd1d4ae7025f.png)| ![image](https://user-images.githubusercontent.com/83030060/129968928-e3ad99c2-37e1-4126-a56c-8ff1b098bcc9.png) | ![image](https://user-images.githubusercontent.com/83030060/129969087-e8ca86bb-f793-460f-a2e6-86c7a88f6c4e.png)

Tech Support            |  Internet Service          | Payment Method
:-----------------------------------:|:-----------------------------------:|:-----------------------------------:
![image](https://user-images.githubusercontent.com/83030060/129969584-f36d95d0-d008-4608-b823-ce6956cb3f52.png) | ![image](https://user-images.githubusercontent.com/83030060/129969607-f8647a06-93eb-49b0-8755-cb69a4f2b229.png)  | ![image](https://user-images.githubusercontent.com/83030060/129969623-398ffd17-3521-4970-95b7-300c90c63fc5.png)

# [Machine Learning Model](https://colab.research.google.com/drive/1zxI_aqxLLldGpG0fC4jTNaQwKjRozO2t#scrollTo=Creating_Model)

## Accuracy Score

The Logistic Regression model was used and presented an accuracy of 79.05%.
~~~python
print("Accuracy score of {} is {:.2f}%\n".format(model, accuracy_score(y_test, pred)*100))
~~~
Accuracy score of LogisticRegression is 79.05%
## Classification Report
~~~python
(classification_report(y_test,pred)
~~~
  
  precision   |   recall  |  f1-score  |   support
:---------------------------:|:----------------------------:|:---------------------------:|:-----------------------------:
 0     |    0.83    |    0.90     |   0.86     |   1085
 1     |    0.65    |    0.50    |    0.57    |     409
accuracy     |             |            |   0.79    |    1494
macro avg   |      0.74    |    0.70    |    0.71    |    1494
weighted avg    |     0.78    |    0.79    |    0.78    |    1494

## Confusion Matrix

~~~python
sns.heatmap(confusion_matrix(y_test, pred), annot=True)
~~~  


![confusion_matrix](https://user-images.githubusercontent.com/83030060/129972567-6f277148-d8c7-4d52-b605-9e49d770309e.jpg)









