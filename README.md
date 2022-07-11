# Neural_Network_Charity_Analysis

## Overview

### Purpose
We developed a binary classifier to predict whether applicants will be successful if funded by Alphabet Soup, a non-profit philanthropic organization.

## Results

### Data Preprocessing

- An applicant organization's success or failure is determined by the variable IS_SUCCESSFUL, which indicates whether or not the application has been successful. In order to better understand the success drivers of an applicant organizations, this is our target variable or dependent variable.
- As features for the model, we consider the following variables to be features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS AND ASK_AMT. In order to make a prediction, we use these independently variable inputs.
- in the datasets, EIN and NAME have been removed since they are neither targets nor features. Since an ID number or the name of the organization can't be used to make reasonable predictions, we have removed these variables.

### Compiling, Training, and Evaluating the Model

- A ReLU activation function was used in both hidden layers and a sigmoid activation function was used in the output layer for the first run of the model. As a general rule of thumb, for a simple model, use 2-3 times as many nodes as inputs in order to avoid overfitting the model. I chose two hidden layers in order to avoid overfitting, and I used 110 total nodes in order to avoid overfitting. Based on the number of inputs from the string of datatypes, 110 nodes fit nicely between 2-3 times the 44 inputs after the strings were encoded into numbers. Due to its ability to identify nonlinear characteristics from input data, ReLU activation is the best choice for the hidden layers. As the output layer, I used the sigmoid activation function since it is ideal for binary classification given its normalized values between 0 and 1.

![DNN](https://user-images.githubusercontent.com/99752443/178239094-2f0cd597-8dc5-45b9-b026-abff19bba38c.png)

- A prediction accuracy of 73% was achieved after the first run of the model, which is lower than the target prediction accuracy of 75%.

![before_the_attempt](https://user-images.githubusercontent.com/99752443/178239114-40fa5c99-c484-4e51-8335-5dc893a00f1c.png)

- In order to increase the model's performance, I made three attempts:

#### Attempt 1

When I first tried to bucket the data, I created categorical values and reassigned the data points to new values based on the unique values in the ASK_AMT variable. Based on the median value of 5000, I felt that it was best to divide the values into five buckets that distributed them evenly.

![attempt#1_binning](https://user-images.githubusercontent.com/99752443/178239141-7a8523e7-70f1-460b-b48b-e111b0de408c.png)

I did not achieve the original predictive accuracy of 73% with my first attempt at improving the model performance. I achieved a predictive accuracy of 72% instead.

![attempt#1](https://user-images.githubusercontent.com/99752443/178239166-311de5db-47f7-41c3-b322-b63092797dc8.png)

#### Attempt 2

During my second attempt, I added as many hidden layers as possible in addition to adding nodes to each of those layers. I increased the number of layers to four and the total number of nodes to 500.

![attempt#2_DNN](https://user-images.githubusercontent.com/99752443/178239208-943285c6-7c13-47e4-a24e-e48bd0e70af5.png)

As a result of the second attempt, an accuracy of about 72% was achieved when the model was further improved.

![attempt#2](https://user-images.githubusercontent.com/99752443/178239260-e89920bd-ad8e-472d-814e-aa9ca28a42c5.png)

#### Attempt 3

After my third attempt, I decided to change the activation function of the hidden layers from ReLU to Leaky ReLU. I chose Leaky ReLU because it offered a good nonlinear alternative. It may also be better to choose activation functions that are a little more complex when optimizing models, so sigmoid and tanh functions may not be the best ones.

![attempt#3_DNN](https://user-images.githubusercontent.com/99752443/178239314-2fa25965-5b3f-4b1e-b5d3-f64cef0122ba.png)

Despite three attempts to increase performance, the model was only able to achieve 72% predictive accuracy.

![attempt#3](https://user-images.githubusercontent.com/99752443/178239341-0ac4d15f-87f7-4283-9968-0f5d8ee621eb.png)

## Summary

Despite 3 attempts to optimize the model, I was unable to achieve the target predictive accuracy of 75% with an initial accuracy of 73%, resulting in performance decreasing by about a percentage point of 72%. An alternative model, such as a logistice regression or random forest, may be more suitable for this analysis since the model could not provide the required accuracy. A logistice regression model would be the ideal approach for improving the accuracy of analysis run on this dataset. This dataset contains continuous and categorical variables, so a logistic regression model can be used to analyze it. Logistic regression models are generally used to predict success or failure of applicants in this situation, it is predicting the success or failure of an organization. Furthermore, we used a sigmoid curve to model the sigmoid activation function of a neural network.
