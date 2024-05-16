# PowerCo Customer Churn Project

### Project Overview

This Project aims to discover the causes of customer churn for PowerCo (A power and energy service provider).
The repository contains three notebooks:
- Data Visualization notebook : Viualizations were done to understand the data
- Feature engineering notebook : New columns were created and unnecessary columns wre dropped.
- Modelling and prediction notebook : A RandomForestClassifier model was trained to predict customer churn and evaluated to check its performance.

### Tools
Python programming

### Code snipet

- Conversion of date columns
~~~python
df["column_name"] = pd.to_datetime(df["column_name"], format='%Y-%m-%d')
~~~

- Converting categorical columns to dummy variables
~~~python
pd.get_dummies(dataset, columns = ['column1', 'column2'])
~~~

- Dropping unnecessary columns
~~~python
df.drop(columns = 'column_name', axis = 1, inplace = True)
~~~

- Importing metrics and libraries for splitting data and Modelling
~~~python
from sklearn import metrics
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
~~~

- Setting values and target variables
~~~python
y = df['ctarget_column']
X = df.drop(columns=['id_column', 'target_column'])
~~~

- Splitting Data into train and test sets
~~~python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.25, random_state=42)
~~~

- Training Model
~~~python
model = RandomForestClassifier(criterion = "gini",min_samples_split = 2, random_state = 7)
model.fit(X_train, y_train)
~~~

- Running prdiction
~~~python
y_pred = model.predict(X_test)
~~~

- Checking accuracy
~~~python
from sklearn.metrics import accuracy_score
accuracy_score(y_test, y_pred)
~~~
