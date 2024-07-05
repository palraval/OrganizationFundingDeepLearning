# OrganizationFundingDeepLearning


## Data Preprocessing for Original Model

The funding data contains 12 columns: **'EIN'**, **'NAME'**, **'APPLICATION_TYPE'**, **'AFFILIATION'**, **'CLASSIFICATION'**, **'USE_CASE'**, **'ORGANIZATION'**, **'STATUS'**, **'INCOME_AMT'**, **'SPECIAL_CONSIDERATIONS'**, **'ASK_AMT'**, and **'IS_SUCCESSFUL'**. The columns **'EIN'** and **'NAME'** are removed from this DataFrame since it will not be used to train the model. For the **'APPLICATION_TYPE'** column, the following values with the lowest counts are combined together under the name "Other" to simplify the data for the model to learn from: 'T9', 'T13', 'T12', 'T2', 'T25', 'T14', 'T29', 'T15', and 'T17'. A similar procedure is conducted on the **'CLASSIFICATION'** column for values that have a count lower than 1883. After this, the categorical data columns are converted to numeric data.

The **'IS_SUCCESSFUL'** columns is separated from the remaining columns since it is the target variable, while the remaining columns are the feature values. From this, the data from both these variables are split to be used in training or testing. The feature variable for training and testing is then standardized according to the fitting based on the features training information. 


## Original Model 

The Deep Neural Network Model is constructed for this data. The first hidden layer contains 80 neurons with a Relu Activation Function. The second hidden layer contains 30 neurons with a Relu Activation Function. The output layer has only one neuron with a Sigmoid Activation Function since the output is binary. The model is compiled with an Adam Optimizer, a Binary Cross Entropy Loss Function, and Accuracy being the metric. The weights for every five epochs is saved under the file named 'per_5_weights.h5'. This model is then trained using the training data for the features and target variables with 100 epochs. The model loss is calculated to be 0.56 and the accuracy is calculated to be 0.73 when the model is used on the testing data. The model is then saved under the file 'AlphabetSoupCharity.h5'.  


## Data Preprocessing for the Optimized Model 

The **'EIN'** column from the same DataFrame used earlier is removed. The **'APPLICATION_TYPE'** and **'CLASSIFICATION'** columns are reduced the same as they were in the preprocessing of the original model. However, for this preprocessing, the **'NAME'** column is also simplified. All the values with a count that is less than or equal to six are combined under the "Other" title. All the categorical columns are turned into numerical ones. The **'IS_SUCCESSFUL'** column is removed from the DataFrame to be used as the target variable, while the remaining columns are used as the features variable, just like it was in the previous preprocessing. After that, the data is split into training and testing sets. Standardization is done on the training and testing features data using a fitted instance of the training features data. 

## Optimized Model 

The model contains three hidden layers: The first layer has 100 neurons with a Relu Activation Function, the second layer has 80 neurons with a Sigmoid Activation Function, and the third layer has 60 neurons with a Sigmoid Activation Function. The outer layer has one neuron with a Sigmoid Activation Function. This model is compiled exactly like it was for the original model: With an Adam Optimizer, a Binary Cross Entropy Loss Function, and Accuracy being the metric. This optimized model is trained using the training data with 125 epochs. The loss was calculated to be 0.47 and the accuracy was 0.79 when the model was used on the testing data. This model is saved under the file 'Alphabet_Soup_Charity_Optimization.h5'. 

A more detailed examination of the model is written [here](model_report.md).

