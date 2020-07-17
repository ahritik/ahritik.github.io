---
layout: post
title:  "First Post"
date:   2020-06-26 21:52:16 -0700
categories: [python,life]
---
This is my first post on my blog to test the capabilities of Jekyll. I will also be showcasing some data visualization and simple linear regression using python.

# Hritik Arasu Linear Regression

### Import neccessary packages


```python
#matplotlib to display graphs
import matplotlib.pyplot as plt
#numpy for storing the data
import numpy as np
#scikit learn for its linear regression model
import sklearn.linear_model as sklm
```

### Creating Data


```python
#seeding the randomity so the results can be redone
np.random.seed(6)

#create a random array of integers from -25 to 25 for both the x & y coordinates
x = np.random.randint(-25,25,(18)).reshape(-1,1)
y = np.random.randint(-25,25,(18))

#show the numbers in a pyplot
plt.plot(x,y,'ro')
plt.axis([-30,30,-30,30])
plt.axhline(y=0, color='k')
plt.axvline(x=0, color='k')
plt.show()
```


![png](/_posts/FirstLinearRegression_files/FirstLinearRegression_4_0.png)


### Create a Linear Regression Model


```python
#create the model based on the x & y
model = sklm.LinearRegression().fit(x,y)

#y-coordinates for the predicted 
predictX = np.arange(-25,25)
predictY = np.array(model.predict(predictX.reshape(-1,1)))

plt.plot(x,y,'ro')
plt.plot(predictX,predictY)
plt.axhline(y=0, color='k')
plt.axvline(x=0, color='k')
plt.show()
```


![png](/_posts/FirstLinearRegression_files/FirstLinearRegression_6_0.png)