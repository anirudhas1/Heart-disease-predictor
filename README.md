# Heart-disease-predictor
Heart Disease Predictor   A Python-based machine learning project to predict heart disease risk using health data. Achieved 80% accuracy with models like Logistic Regression and Random Forest. Utilized Pandas, Matplotlib, and Scikit-Learn for data preprocessing, EDA, and modeling. Provides actionable insights for healthcare decision-making.  
# importing libraries
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score
# checking the distribution of target variable
heart_data['target'].value_counts()
# splitting features and darget

X = heart_data.drop(columns='target',axis=1)
Y = heart_data['target']
# splitting the data into training data and testing data
X_train,X_test,Y_train,Y_test = train_test_split(X, Y, test_size=0.2, stratify=Y, random_state=2)
print(X.shape , X_test.shape , X_train.shape)
# Model Training 
# Logistic Regression
model = LogisticRegression()
# training the logisticregression model with training data
model.fit(X_train.values , Y_train)
# Model evaluation 
# Accuracy score
# accuracy on training data
X_train_prediction = model.predict(X_train)
training_data_accuracy = accuracy_score(X_train_prediction, Y_train)
print('Accuracy on training data: ',training_data_accuracy)
# accuracy on test data
X_test_prediction = model.predict(X_test)
test_data_accuracy = accuracy_score(X_test_prediction, Y_test)
print('Accuracy on test data: ',test_data_accuracy)
# Building a predictive system
input_data = (41,0,1,130,204,0,0,172,0,1.4,2,0,2)

# changing the data into numpy array

input_data_as_numpy_array = np.asarray(input_data)

# reshape the numpy array for only one instance

input_data_reshaped = input_data_as_numpy_array.reshape(1,-1)

prediction = model.predict(input_data_reshaped)
print(prediction)

if(prediction[0]==0):
    print('The person does not have heart disease')
else:
    print('The person have heart disease')
