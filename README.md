# Cryptocurrencies

UT Bootcamp Module 18 Challenge

## Project Overview
Use unsupervised machine learning methodology to investigate a dataset of different cryptocurrencies and develop trends to deliver an investment portfolio to Martha's firm, Accountability Accounting.  During this process, we learned how to cluster, transform and process data by reducing data dimensions and principal companents using PCA.

## Resources
Data Sources provided to analyze and minipulate included:
- crypto_data.csv

Software utilized for this study included: 
- Python 3.7.6 
- Pandas
- Personal GitHub account

## Analysis/Workflow/Results

### Deliverable 1: Preprocessing the Data for PCA

Specifically for this deliverable we did the following:
1. Read in the crypto_data.csv to the Pandas DataFrame named crypto_df.
2. Keep all the cryptocurrencies that are being traded.
3. Drop the IsTrading column.
4. Remove rows that have at least one null value.
5. Filter the crypto_df DataFrame so it only has rows where coins have been mined.
6. Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
7. Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm (see below).

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_2a.PNG)

9. Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.
10. Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.

Code:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_2a.PNG)

### Deliverable 2: Reducing Data Dimensions Using PCA 

Specifically for this deliverable we did the following:
1. Continue using the crypto_clustering.ipynb file from Deliverable 1 where you’ve already performed the preprocessing steps.
2. Using the information we’ve provided, apply PCA to reduce the dimensions to three principal components.
3. Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index (see below).

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli2_1a.PNG)

Code:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli2_1.PNG)

### Deliverable 3: Clustering Cryptocurrencies Using K-means

Specifically for this deliverable we did the following:
1. Continue using the crypto_clustering.ipynb file that you used in Deliverable 2 to reduce the dataset to three dimensions.
2. Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K (see below).

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli2_1.PNG)

3. Use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.
4. Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the crypto_df DataFrame.
5. Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Deliverable 1, to the clustered_df.
6. Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3 (see below).

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_1a.PNG)

Code:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_1.PNG)

### Deliverable 4: Visualizing Cryptocurrencies Results

Specifically for this deliverable we did the following:
1. Continue using the crypto_clustering.ipynb file from Deliverable 3 where you have predicted the K clusters for the cryptocurrencies’ data.
2. Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.
3. Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.
4. Create a table with tradable cryptocurrencies using the hvplot.table() function (see below).

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_1a.PNG)

6. Print the total number of tradable cryptocurrencies in the clustered_df DataFrame.
7. Use the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.
8. Create a new DataFrame using the clustered_df DataFrame index that contains the scaled data you created in Step 5.
9. Add the CoinName column from the clustered_df DataFrame to the new DataFrame.
10. Add the Class column from the clustered_df DataFrame to the new DataFrame (see below).

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_1a.PNG)

12. Create an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", showing the CoinName when you hover over the the data point (see below).

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_1a.PNG)
