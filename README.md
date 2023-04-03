# deep-learning-challenge

# Overview - Explain the purpose of this analysis.

This machine learning model's purpose is to create a tool for Alphabet Soup to select applicants for funding with the highest chance of success. A dataset of previous organizations that have been funded by Alphabet soup was provided, which contained categorical and numerical data including industry sectors, use cases, income, funding request, and success or failure. A neural network will be trained to predict the success or failure of an organization, with a goal of 75% accuracy. 

# Results 

The sole target variable is the success or failure of an organization after funding. 

- IS_SUCCESSFUL

The following are the features used by the model, 

- APPLICATION (categorical, examples are 'T10, T3, T5')
- AFFILIATION (Independent, Sponsored, etc.)
- CLASSIFICATION (categorical, examples are 'C1000, C2000, C3000')
- USE_CASE (ProductDev, Preservation, Healthcare, etc)
- ORGANIZATION (Association, Co-operative, Trust, etc)
- STATUS (Binary 1 or 0)
- INCOME_AMT (binned amounts such as 0, 1-9999, 10000-24999, as strings)
- SPECIAL_CONSIDERATIONS ( Y or N )
- ASK_AMT (numerical)

The following data was not processed by the model, as names and record number were assumed to not be indicative of success. 

- EIN (record number)
- NAME (name of the project/organization)

The columns APPLICATION_TYPE and CLASSIFICATION had some of their categories binned into 'Other' to avoid the influence of outliers, as some of the categories had a very small sample size compared to the overall dataset. 

The first attempt at training this neural network model included an input layer with 80 neurons with ReLu activation, about twice the amount of input variables after encoding the cateogorical data. One hidden layer was used with 30 neurons and ReLu activation as an initial attempt. The output layer will consist of one neuron and sigmoid activation, as the target variable is a binary result. This initial model was reported to have a loss of 56% and an accuracy of 72.2%, so further optimization is needed. 

Keras Tuner was used to suggest an architecture for this neural network. The top 3 structures suggested were trained with a variety of activation functions and hidden layers, and reported an accuracy of 72.3%, 72.4%, 47.4%. This attempt of model optimization fell short of the target accuracy of 75%.  

# Summary 

In short, this model does not yet meet the required accuracy. Further optimization could include individually removing certain columns to test the individual effect on accuracy. Keras Tuner was used to optimize the model, but other tools should be used in order to optimize the model. 
