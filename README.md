# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required packages and print the present data.

2.Print the placement data and salary data.

3.Find the null and duplicate values.

4.Using logistic regression find the predicted values of accuracy , confusion matrices.

5.Display the results.

## Program and Output:
```
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: HARIHARAN J
RegisterNumber:  212223240047
import pandas as pd
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
dataset = pd.read_csv('/content/Placement_Data_Full_Class (1).csv')
dataset.head()
dataset.tail()
```
![image](https://github.com/user-attachments/assets/f56568fe-a470-4362-81a0-b0b2abcce566)
![image](https://github.com/user-attachments/assets/92767f96-7960-4faf-a409-597aae2d5365)

```
dataset.info()
```
![image](https://github.com/user-attachments/assets/91821b3a-e316-4aad-85bf-3ae3a0ff92f6)

```
dataset.drop('sl_no',axis=1)
dataset = dataset.drop('sl_no',axis=1)
dataset.info()
```
![image](https://github.com/user-attachments/assets/01eb6dd5-2477-4a5a-824a-516397852b38)

```
dataset["gender"] = dataset["gender"].astype('category')
dataset["ssc_b"] = dataset["ssc_b"].astype('category')
dataset["hsc_b"] = dataset["hsc_b"].astype('category')
dataset["hsc_s"] = dataset["hsc_s"].astype('category')
dataset["degree_t"] = dataset["degree_t"].astype('category')
dataset["workex"] = dataset["workex"].astype('category')
dataset["specialisation"] = dataset["specialisation"].astype('category')
dataset["status"] = dataset["status"].astype('category')
dataset.info()
```
![image](https://github.com/user-attachments/assets/20d41f9a-f384-4501-8751-34aa309f5392)

```
dataset["gender"] = dataset["gender"].cat.codes
dataset["ssc_b"] = dataset["ssc_b"].cat.codes
dataset["hsc_b"] = dataset["hsc_b"].cat.codes
dataset["hsc_s"] = dataset["hsc_s"].cat.codes
dataset["degree_t"] = dataset["degree_t"].cat.codes
dataset["workex"] = dataset["workex"].cat.codes
dataset["specialisation"] = dataset["specialisation"].cat.codes
dataset["status"] = dataset["status"].cat.codes
dataset.info()
```
![image](https://github.com/user-attachments/assets/03f15b24-0e0e-4068-a5c6-f0671d0dc031)

```
x=dataset.iloc[:,:-1]
y=dataset.iloc[:,-1]
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)clf = LogisticRegression()
clf.fit(x_train, y_train)
```
![image](https://github.com/user-attachments/assets/7bd3c9e5-befe-4957-8f37-a942befb1f9d)

```
y_pred=clf.predict(x_test)
print(y_pred)
```
![image](https://github.com/user-attachments/assets/495ec59c-1013-496c-b87b-cf11cdc05795)

```
from sklearn.metrics import confusion_matrix,accuracy_score
cf=confusion_matrix(y_test,y_pred)
print(cf)
```
![image](https://github.com/user-attachments/assets/1e3e5a6c-bf64-4abb-a4c9-d022cf976f1b)

```
accuracy = accuracy_score(y_test, y_pred)
print(accuracy)
```
![image](https://github.com/user-attachments/assets/003dfd6f-c547-442f-858e-e139539409d2)


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
