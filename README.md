# Cryptocurrency Clusters

Here is a hypothetical problem set that allows an analyst to dig into unsupervised learning while showing some skills in pre-processing data in pandas.  

## Background

* You are on the Advisory Services Team of a financial consultancy. One of your clients, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. They’ve asked you to create a report that includes what cryptocurrencies are on the trading market and determine whether they can be grouped to create a classification system for this new investment.

* You have been handed raw data, so you will first need to process it to fit the machine learning models. Since there is no known classification system, you will need to use unsupervised learning. 

### Data Preparation

* The dataset for this project was obtained from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist).

* Once I loaded in the data, I took the following pre-processing steps to have the dataset make sense for an unsupervised learning model.

  * Removed all rows that have at least one null value.

  * Filtered for cryptocurrencies that have been mined. That is, the total coins mined should be greater than zero.

  * Deleted the `CoinName` from the original dataframe to make all data numeric.

  * Converted the remaining features with text values, `Algorithm` and `ProofType`, into numerical data. 

  * Standardized the dataset using scaling so that columns that contained larger values did not unduly influence the outcome.

### Dimensionality Reduction

* Creating dummy variables dramatically increased the number of features in the dataset. Performing dimensionality reduction with PCA can bring the number of features back down, reducing the complexity of the model. Rather than specify the number of principal components, I defined the level of variance I wanted described by the model, .90, when setting the parameters for the PCA. 

* Next, further reduce the dataset dimensions with t-SNE and visually inspect the results. In order to accomplish this task, run t-SNE on the principal components: the output of the PCA transformation. Then create a scatter plot of the t-SNE output. Observe whether there are distinct clusters or not.

### Cluster Analysis with k-Means

* Create an elbow plot to identify the best number of clusters. Use a for-loop to determine the inertia for each `k` between 1 through 10. Determine, if possible, where the elbow of the plot is, and at which value of `k` it appears.

### Recommendation

* Based on your findings, make a brief (1-2 sentences) recommendation to your clients. Can the cryptocurrencies be clustered together? If so, into how many clusters? 

## Rubric

[Unit 20 - Unsupervised Machine Learning Homework Rubric - Cryptocurrency Clusters](https://docs.google.com/document/d/1zhiC8-PtfMknDxYHagsTukryQAJSdXFRWa-aK3W28Vg/edit?usp=sharing)

- - -

## References

Crypto Coin Comparison Ltd. (2020) Coin market capitalization lists of crypto currencies and prices. Retrieved from [https://www.cryptocompare.com/coins/list/all/USD/1](https://www.cryptocompare.com/coins/list/all/USD/1)

- - -

© 2021 Trilogy Education Services, LLC, a 2U, Inc. brand. Confidential and Proprietary. All Rights Reserved.
