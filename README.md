# Neural Network Model for Nonprofit Success

## Purpose
The goal of this model is to develop a tool to review funding applications for nonprofit organizations and predict whether they will be successful.  The models developed here are neural networks which are trained on data from approximately 32,000 applications.  The output of each model is a binary indication of whether the venture will be successful or not.  The training data on past applications includes whether the venture was successful, along with other factors such as:
- Application type
- Sector or industry
- Government classification
- Use-case
- Income classification
- Asking amount

## Preprocessing
The following steps were taken to preprocess the initial data set before feeding training the neural network.
- Application types with fewer than 100 instances had their application type changed to Other.
- Classification types with fewer than 100 instances had their type changed to Other.
- All categorical data was changed to binary values using one-hot encoding.
- All values were scaled using StandardScaler.

## Initial Learning Model
The initial neural network in `AlphabetSoupCharity.ipynb` was created with an input layer and one hidden layer, each with 16 neurons and using the ReLU activation function.  The output layer includes just one output unit (0 for an unsuccessful venture and 1 for a successful venture) and uses a sigmoid activation function.

After training the model with 50 epochs, it achieved an accuracy of 72.05% when tested against further data from the data set.

## Optimizing the Learning Model
A second neural network (contained the in the `AlphabetSoupCharity_Optimization.ipynb` file) was created to optimize accuracy of the model.  Changes from the first model are as follows:
- Application types with fewer than 500 instances (rather than 100) were changed to Other.
- Classification types with fewer than 500 instances (rather than 100) were changed to Other.
- The split between the training and test data was changed by changing the random state of the splitting function.
- The neural network was altered to have 4 hidden layers, each with 32 neurons using a ReLU activation function.
- The number of training epochs was increased from 50 to 100.

These changes resulted in only modest gains, resulting in a model whose accuracy was 73.35%.

## Summary
After several iterations and improvements to optimize the model, we were not able to achieve our goal of 75% accuracy.  However, this tool may still provide insights and influence decision making when determining whether to fund new ventures.  There may be further improvements to this model which could yield marginally better accuracy, but future analysis may explore using logarithmic regression or decision tree-based machine learning models to more accurately predict the success of business ventures.  Additionally, collecting more data or adding/reducing features may generate in a more accurate model.

## Authorship
Starter code and training data for this project were provided by the UNC Data Analytics Bootcamp.  Data processing, development of the neural networks, and analysis were created by Hazel Mena.
