# Identifying Unsatisfied Customers

Understanding drivers of customer behaviour and predicting likely outcomes is a commercially-relevant problem that can be solved through Machine Learning models. When it comes to client engagement, firms are interested to know what factors led to customer dissatisfaction. With this knowledge, they can make necessary changes to their practices, products and services and even their business model.

Conceptually this problem meets many criteria for a machine learning task:

1. Probabilistic Setting. We say that past data is a set of independent draws from an overall population and that (barring major changes in the organisation and client engagment models) future draws would follow the same stochastic process

2. Stationarity. We loosely accept that the data follows a stationary stochasitic process whose parameters do not change dramatically over time. For instance practically we can argue that poor service (however measured) equals dissatified customers now and in future.

3. A priori knowledge. The sponsoring firm will have considerable domain knowledge of the type of variables that affect the probability of client satisfaction and what data to consider.

This notebook applies and evaluates the Random Forest and AdaBoost models on a publicly available data from Santander Bank. This data was published in 2016 as part of a Kaggle competition. The task is to predict the probability that each customer in the test set is an unsatisfied customer. The data has already been analysed by many particpants of that competition.

The models fit the training data well, but do not generalise as well, when applied to the validation data. Attempts to improve performance through optimisation of model parameters yield only marginal benefits.

Further details on the original competition can be found here: https://www.kaggle.com/competitions/santander-customer-satisfaction/overview

Contact: aa2009@caa.columbia.edu
