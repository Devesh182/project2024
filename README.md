import pandas as pd
salary= pd.read_csv("https://github.com/YBIFoundation/Dataset/raw/main/MBASalary.csv')
salary.head()
salary.info()
salary.decsribe()
y=salary['Salary']
x=salary[['Percentage Marks']]
x.shape
y.shape
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,train_size=0.75)
x_train.shape
x_test.shape
y_train.shape
y_test.shape
from sklearn.linear_model import LinearRegression
model= LinearRegression()
model.fit(x_train,y_train)
model.intercept_
model.slope_
y_pred = model.predict(x_test)
from sklearn.metrics import mean_absolute_percentage_error
mean_absolute_percentage_error(y_test,y_pred)


