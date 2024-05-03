# Datasheet

The data is provided by Santander Bank, which consists of large number of anonymized numeric variables, relating to their customers. The "TARGET" column is the variable to predict. It equals one for unsatisfied customers and 0 for satisfied customers. The data is shared in three files, a training dataset which includes the target variable. A test dataset which only includes predictor and was used to submit model-based predictions to the bank. Finally a sample file is provided, showing the submission format. 

Data files can be found at: https://www.kaggle.com/competitions/santander-customer-satisfaction/data
 

## Motivation

Santander Bank invited data scientists to a competition, where the objective was to create algorithms to predict which customers are likely to be unsatisfied early on in the relationship. The competition awared a total prize of $60,000 to the three best performing submission. The competition closed in 2016.

Customer satisfaction is an important indicator of success of a bank's frontline team as well as senior leadership. Santander Bank noted that "unhappy customers don't stick around. What's more, unhappy customers rarely voice their dissatisfaction before leaving." 

Therefore banks shared data on their customers and asked "Kagglers to help them identify dissatisfied customers early in their relationship. Doing so would allow Santander to take proactive steps to improve a customer's happiness before it's too late."


 
## Composition

There are 76020 instances in the dataset, which reflect individual customers of the bank. 

There are 370 anonymised features relating to each customer. The dataset contains no personal information and since it is publicly available, it is not considered confidential. 

The dataset is well structured and there is no missing data. However, the data is sparse on these features and a vast majority of observations are zero. We assume that zero values are intended and are not a substitution for null values.

The target variable is binary. Value of 1 indicates unsatisfied customers. Only 4% of all instances are those of unsatisfied customers, which is the category of interest. Therefore this dataset is unbalanced. 


## Collection process

It is not known to the author how data was collected.


## Preprocessing/cleaning/labelling

As mentioned above, the column headers of predictor variables are anonymised. However, one can deduce the type of some data in some columns; for instance many relate to "saldo", possibly the account balance. 

Since the data is sparse, it needs to be scaled appropriately before using in most machine learning models.  


## Uses

The dataset could be used to practice machine learning tasks, particularly building predictive models for client engagement purposes. It can also be used to benchmark parameters of hyperparameter optimisation tasks; these can then be used to "warm start" these optimisers when faced with similar problems. 

One clear limitation of this data is that feature names are not meaningful and therefore the results cannot be interpreted from a business perspective. 


## Distribution

The data was provided specifically for the purpose of the competition. The rules of the competition, do limit the rights of use of this data. More can be seen here: https://www.kaggle.com/competitions/santander-customer-satisfaction/rules#data . 
 

## Maintenance

The dataset is available on Kaggle and as such its integrity would be based on the data management policy of this website.

