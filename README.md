# CryptoClustering
 
CryptoClustering is a Python project that uses unsupervised learning and K-means clustering to predict if cryptocurrencies are affected by 24-hour or 7-day price changes. This project aims to provide insights into the clustering patterns of cryptocurrencies based on their price change percentages.

## Dataset

The project uses the **crypto_market_data.csv** file located in the data directory. This dataset contains information about various cryptocurrencies and their price change percentages over 24 hours and 7 days.

## Notebook Content
The Jupyter notebook **Crypto_Clustering.ipynb** contains the following sections:

#### Preparing the Data

1. I use the `StandardScaler()` module from `scikit-learn` to normalize the data from the CSV file.
2. I the create a DataFrame with the scaled data and set the `coin_id` index from the original DataFrame as the index for the new DataFrame.

#### Finding the Best Value for k Using the Original Scaled DataFrame

I Use the elbow method to find the best value for `k` using the following steps:
 1. Creating a list with the number of `k` values from *1* to *11*.
 2. Creating an empty list to store the inertia values.
 3. Creating a *for-loop* to compute the inertia with each possible value of `k`.
 4. Creating a dictionary with the data to plot the elbow curve.
 5. Plotting a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.

The following question was answered in the notebook: 
 **- What is the best value for k?**


#### Clustering Cryptocurrencies with K-means Using the Original Scaled Data

I use the following steps to cluster the cryptocurrencies for the best value for `k` on the original scaled data:
 1. Initializing the K-means model with the best value for `k`.
 2. Fitting the K-means model using the original scaled DataFrame.
 3. Predicting the clusters to group the cryptocurrencies using the original scaled DataFrame.
 4. Creating a copy of the original data and add a new column with the predicted clusters.
 5. Creating a scatter plot using hvPlot as follows:
 6. Setting the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
 7. Coloring the graph points with the labels found using K-means.
 8. Adding the "coin_id" column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.


#### Optimizing Clusters with Principal Component Analysis (PCA)

1. Using the original scaled DataFrame, I perform a PCA and reduce the features to three principal components.
2. I retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in the notebook:
  **- What is the total explained variance of the three principal components?**

3. I then create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.


#### Finding the Best Value for k Using the PCA Data

Using the elbow method on the PCA data I find the best value for k using the following steps:
 1. Creating a list with the number of k-values from 1 to 11.
 2. Creating an empty list to store the inertia values.
 3. Creating a *for-loop* to compute the inertia with each possible value of k.
 4. Creating a dictionary with the data to plot the Elbow curve.
 5. Plotting a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

The following questions are answered in the notebook:
 **- What is the best value for k when using the PCA data?**
 **- Does it differ from the best k value found using the original data?**


#### Clustering Cryptocurrencies with K-means Using the PCA Data

Using the following steps I cluster the cryptocurrencies for the best value for k on the PCA data:
1. Initialize the K-means model with the best value for k.
2. Fitting the K-means model using the PCA data.
3. Predicting the clusters to group the cryptocurrencies using the PCA data.
4. Creating a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
5. Creating a scatter plot using hvPlot as follows:
6. Setting the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
7. Coloring the graph points with the labels found using K-means.
8. Adding the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.


The following questions are answered in the notebook:
 **- What is the impact of using fewer features to cluster the data using K-Means?**


## Technologies Used

The `CryptoClustering` project utilizes the following technologies:

 - Python
 - Jupyter Notebook
 - Pandas
 - NumPy
 - Scikit-learn
 - Plotly
 - Hvplot
