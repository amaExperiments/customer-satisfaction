# Model Card

## Model Description

The model shared in this folder can be used to predict the likelihood of a customer being unsatisfied. It is specifically trained on data shared by Santander Bank for a competition and therefore its results are only relevant for that instance. However, one can deduce from this analysis how such models will perform when faced with similar problems of predicting customer behaviour.

The model uses two different classifiers - Random Forest and a Boosting algorithm. It then fine tunes the performance of the Random Forest algorithm using Bayesian optimisation. 


**Input:** The input data consists of 370 features and 1 binary target variable, taking 0/1 values. The class of interest is 1, which indicates a unsatisfied customer  

**Output:** The model outputs are predictions on client satisfaction, using a validation or test data on the input features


**Model Architecture:** The following are key components of the model:

1. Load necessary libraries

2. Data Loading
The model loads data from .csv files from a local directory

3. Data Pre-processing
Conducts a series of pre-processing tasks on this data. Specifically it: 
* Checks for missing data (no missing values were found)
* Checks for imbalance in target categories
* Removes columns with no content - that is only zero values
* Scales all columns using either standard (mean, standard deviation) scaling or maximum absolute scaling

4. Training and Validation dataset creation
The target variable is unbalanced (there are relatively very few instances of the category of interest). Therefore the model uses under-sampling to create a training dataset that includes equal instances of 0 and 1 target variable. It then creates a validation dataset which preserves the ratio of 0/1 target values in the original dataset.

5. Execution and Evaluation Functions
The model creates a series of functions to easily iterate through multiple models.

6. Algorithm Executions
The model executes two different algorithms (Random Forest and AdaBoost) and aggregates their performance measures in a table.

7. Hyperparameter Tuning
Finally the model uses Bayesian Optimization to tune hyperparameters of the Random Forest algorithm.

8. Results Summary



## Performance

A summary table of model performance is shared in the folder. The algorithms were evaluated using three different measures: precision,recall and F1 score. 

Both models fit the data very well; F1 score for Random Forest (RF) was 0.9860 on the training data. However they performed less well on validation data. The F1 scores of RF and AdaBoost algorithms on validation data were 0.1846 and 0.1865, respectively.

After applying Bayesian Optimisation on the RF hyperparameters, the F1 score improved to 0.1936. 


## Limitations

The tree based classifiers using in the model do not appear to generalise well as show in the performance results. In particular both models had a high number of False Positives -- that is, it made too many predictions of unsatisfied customers. 

This may call for more complex models to be considered. For instance models that could account for the interaction between multiple features. Neural Networks come to mind. 

The model is run on data at a point in time. For the purpose of predicting customer behaviour, time series of certain data may also be relevant. It is not clear whether such trending data was included in Santander's dataset. 


## Trade-offs

A few points to bear in mind. 

1) Hyperparameter tuning using Bayesian Optimiser took a several minutes to run and was thus not explored on other models
2) There was no significant difference in scaling the data using Standard Scaler or using Max Absolute Scaler
3) Model performance was somewhat variable when resampling the training and validation data, however for consistency one instance of a random draw is used 
