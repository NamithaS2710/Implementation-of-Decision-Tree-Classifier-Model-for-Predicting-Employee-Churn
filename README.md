# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas library to read csv or excel file.
2.Import LabelEncoder using sklearn.preprocessing library.
3.Transform the data's using LabelEncoder.
4.Import decision tree classifier from sklearn.tree library to predict the values.
5.Find accuracy.
6.Predict the values.
7.End of the program. 

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: NAMITHA.S
RegisterNumber: 212221040110 
*/
```
```
import pandas as pd
data=pd.read_csv("Employee.csv")
print("data.head()")
data.head()

print("data.info()")
data.info()

print("isnull() and sum()")
data.isnull().sum()

print("data value counts()")
data["left"].value_counts()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

print("data.head() for salary")
data["salary"]=le.fit_transform(data["salary"])
data.head()

x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()

y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
print("Accuracy value")
accuracy

print("data.prediction")
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/0456fe4e-2428-4128-894c-186244332325)
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/411218a6-b197-498b-8683-198e1e1fea8f)
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/62935a83-d39c-45d4-af89-88b45efdb765)
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/4c559877-9dfe-4d77-92c4-d8ffea50cc3e)
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/74cc2643-19bc-4b7b-9db0-b5cec66862b7)
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/b5879de7-8745-4434-8b9c-402ebb0fba75)
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/98b8c6f2-aa0d-459a-894a-42bec033b4f7)
![image](https://github.com/NamithaS2710/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/133190822/cd5d3e17-662f-459e-aa8b-bc7960f49989)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
