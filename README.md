# Charity Analysis

## Overview of Charity Analysis
The purpose of this analysis is to predict whether applicants will be successful if funded using data on more than 34,000 organizations that have previously received funding. 

## Results

### Data Preprocessing
* **Target:** 
    * IS_SUCCESSFUL
* **Features:** 
    * APPLICATION_TYPE
    * AFFILIATION
    * CLASSIFICATION
    * USE_CASE
    * ORGANIZATION
    * STATUS
    * INCOME_AMT
    * SPECIAL_CONSIDERATIONS
    * ASK_AMT
* **Variables to Remove:** 
    * EIN
    * NAME
    
### Compiling, Training, and Evaluating the Model
#### How many neurons, layers, and activation functions did you select for your neural network model, and why?
* The model has three layers including the output layer. The first two layers both have 16 neurons and the output layer has one neuron. 
* The first layer uses the ReLU activation function, the second layer uses the Sigmoid activation function and the output layer uses the Sigmoid activation function. The ouput layer uses the Sigmoid activation function to categorize whether the application is successful. 

#### Were you able to achieve the target model performance? What steps did you take to try and increase model performance?
I was not able to achieve the target model performance of 75%. I took the following steps to try to increase the model performance. 
1. I updated the binning thresholds for both Application Type and Classification less than 100. 
2. I used chi square to determine what features are most predictive of success. I dropped the features that had p > 0.1 to remover the features that are least predictive of success. 
2. I increased the number of hidden layers to four hidden layers rather than two. 
3. I changed all activation functions in the hidden layers to ReLU because it resulted in the highest accuracy scores. 
4. I increased the number of neurons to 500 per hidden layer. 
5. I increased the number of epochs to 500. 

#### Original Model
**Summary** <br/>
![Model Summary](https://github.com/rabascoh/neural-network-charity-analysis/blob/main/Resources/Model.png)

**Accuracy & Loss** <br/>
Loss: 0.55 <br/>
Accuracy: 0.73 <br/>

#### Optimized Model
**Summary** <br/>
![Optimized Model Summary](https://github.com/rabascoh/neural-network-charity-analysis/blob/main/Resources/Model_Optimized.png)

**Accuracy & Loss** <br/>
Loss: 1.2 <br/>
Accuracy: 0.73 <br/>

## Summary
Both the original and the optimized models had an accuracy of 0.73 even after substantial changes to the optimized model. The loss also *increased* for the optimized model indicating that it is worse at predicting success compared to the original model. 

### Alternative Model
A logistic regression model could also be used to predict success. This model would allow for classification as 'successful' or 'unsuccessful' similar to the Sigmoid activation function used in the deep learning model. 
