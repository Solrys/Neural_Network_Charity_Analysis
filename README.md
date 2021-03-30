# Neural_Network_Charity_Analysis
Using Pandas and the Scikit-Learn’s in order to compile, train, and evaluate the neural network model

## Background
Neural networks have many practical uses across multiple industries. In the finance industry, neural networks are used to detect fraud as well as trends in the stock market. Neural networks are scalable and effective and excellent at detecting complex, nonlinear relationships.

For this project, I will use the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.
I will be working off  a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

* EIN and NAME—Identification columns
* APPLICATION_TYPE—Alphabet Soup application type
* AFFILIATION—Affiliated sector of industry
* CLASSIFICATION—Government organization classification
* USE_CASE—Use case for funding
* ORGANIZATION—Organization type
* STATUS—Active status
* INCOME_AMT—Income classification
* SPECIAL_CONSIDERATIONS—Special consideration for application
* ASK_AMT—Funding amount requested
* IS_SUCCESSFUL—Was the money used effectively

## Objectives

* 1: Preprocessing Data for a Neural Network Model
* 2: Compile, Train, and Evaluate the Model
* 3: Optimize the Model
* 4: Analyze my findings

## Method 

At the first attempt the model was around 70 % accurate. 
Using the data from the CSV file, for the first Model I dropped the EIN and NAME columns.
Then I determined the number of unique values for each column.
For those columns that have more than 10 unique values, I determined the number of data points for each unique value.
Next I Created a density plot to determine the distribution of the column values.
Using the density plot to create a cutoff point to bin "rare" categorical variables together in a new column, Other, and then I checked if the binning was successful.
Then I Generated a list of categorical variables.
After that I Encoded categorical variables using one-hot encoding, and placed the variables in a new DataFrame.
Finally I merged the one-hot encoding DataFrame with the original DataFrame, and drop the originals.

This is what My data frame looked like:
![dataf](https://github.com/Solrys/Neural_Network_Charity_Analysis/blob/main/visuals/Screen%20Shot%202021-03-30%20at%206.52.08%20PM.png)

Before Testing I split the preprocessed data into features and target arrays.
Then I split the preprocessed data into training and testing datasets. Using Scikit-Learn’s StandardScaler class, then scale the data.And finally I ran the model and tested for accuracy.

## Results

## * First Model Accuracy 
My First Model was under the desired 75 percent accuracy. 
![first](https://github.com/Solrys/Neural_Network_Charity_Analysis/blob/main/visuals/Screen%20Shot%202021-03-30%20at%206.53.33%20PM.png)

## * Optomizing The Models
In order to try to optimize the accuracy I tried to do the following. 

Even after adding Hidden layers, playing with the number of Epochs, setting density, grouping "others", trying various activation functions, and then retrying the activation functions in different orders, the accuracy on the best models were just shy of 75%. 


## * Final Model 
I finally went back to my orginal code and kept the "name" column and only dropped the EIN column.I simplified the code.  I also made some slight changes to aggregate the best of what was working on each model. The activation functions that worked best with this data were predominatntly relu followed by a sigmoid outer layer. 
The model didnt seem to benifit from more than 3 hidden layers or more than 100 Epochs. While I must have gone through over two dozen versions of code to figure out a formula that worked, adding these changes the model came in at over 90% accuracy.

![finalmod](https://github.com/Solrys/Neural_Network_Charity_Analysis/blob/main/visuals/Screen%20Shot%202021-03-30%20at%207.21.06%20PM.png)

## Conclusion




