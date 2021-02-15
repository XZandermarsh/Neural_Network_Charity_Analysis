# Neural_Network_Charity_Analysis
 
# Overview
### This analysis attempted to build a machine learning model for predicting the success of charity efforts using deep learning.

## Data Preprocessing
### What variables are considered the target for your model?
* "IS_SUCCESSFUL" was the target value used for this model, because this is the variable we are trying to predict.

### What variables are considered the features for your model?
* "APPLICATION_TYPE", "AFFLIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "SPECIAL_CONSIDERATIONS", and "ASK_AMT" were the features used.

### What variables are neither targets nor features, and should be removed from the input data?
* "EIN" and "NAME" were removed from the data because they are unique identifiers of the charity entries and do not have relevance to the model.


## Compiling, Training, and Evaluation
### How many neurons, layers, and activation functions did you select for your neural network model, and why?
* On my first model, I used 2 hidden layers, with 80 and 30 neurons, respectively. I utilized the ReLu activation function for both layers, and sigmoid for the output layer. For the optimized model, I used 3 hidden layers, with 317 , 929, and 873 neurons, respectively, again with ReLu for the hidden layers and sigmoid for the output layer.

### Were you able to achieve the target model performance?
* Even after optimization, I was not able to hit 0.75 accuracy. My un-optimized model achieved an accuracy of 0.7293 after 50 epochs, while the fully "optimized" version actually went down to 0.7289 after 100 epochs. This could indicate that the model may have been over-fit to the training data, as the last epochs were around 0.74-0.745, but had lower accuracy when evaluated against the actual test data.

### What steps did you take to try and increase model performance?
* To improve the performance, I first used a RandomForestClassifier to evaluate the impact of each feature. After doing so, I filtered out the features which had a score below 0.005 to reduce noise in the model. Next, I tried adding a third hidden layer and increasing the number of nodes. Since did not improve the score and I was unsure how many nodes would be best, I setup a for loop to use a random integer (1-1000) for the number of neurons in each of the 3 hidden layers. The for loop ran 25 times and recorded the best accuracy score and associated neuron numbers. The final result was an accuracy score of 0.732 and 317 , 929, and 873 for the neurons. Finally, I ran the model again with these neuron numbers for 100 epochs to try to maximize the performance further, and achieved an accuracy of 0.7289.
![alt text](https://github.com/XZandermarsh/Neural_Network_Charity_Analysis/blob/main/Optimization_For_Loop.png "Optimization For Loop")

## Summary & Recommendation
* In conclusion, it took a lot of time and work to get only a very small performance boost in the model from the initial result. It may be beneficial to get more features to include in the model, or this may just be a poor application of machine learning if the goal is to very accurately predict the success of charity efforts.
