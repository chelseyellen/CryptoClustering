# CryptoClustering
## Inital effort
* To begin, I created the git repository for this effort
* I then downloaded the Module 11 Challenge starter code

## Prepare the Data
* I used the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
* Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Found the Best Value for k Using the Original Scaled DataFrame
* Used the elbow method to find the best value for k by completing the following steps:
   * Created a list with the number of k values from 1 to 11
   * Created an empty list to store the inertia values.
   * Created a for loop to compute the inertia with each possible value of k.
   * Created a dictionary with the data to plot the elbow curve.
   * Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
   * Answered the following question: What is the best value for k?
     * Based upon the line chart, I believe that the elbow point is 4

## Cluster Cryptocurrencies with K-Means Using the Original Scaled Data
* Used the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
  * Initialized the K-means model with the best value for k
  * Created an instance of K-means, defined the number of clusters based on the best value of k, and then fit the model using the original scaled DataFrame.
  * Predicted the clusters to group the cryptocurrencies using the original scaled DataFrame.
  * Created a copy of the original data and added a new column with the predicted clusters.
  * Created a scatterplot using pandas’ plot as follows:
    * Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".

## Optimized Clusters with Principal Component Analysis
* Using the original scaled DataFrame, performed a PCA and reduced the features to three principal components.
* Retrieved the explained variance to determine how much information can be attributed to each principal component and then answer the following question:
  * What is the total explained variance of the three principal components? 89.5%
* Created a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Found the Best Value for k Using the PCA Data
* Used the elbow method on the PCA data to find the best value for k using the following steps:
  * Created a list with the number of k-values from 1 to 11.
  * Created an empty list to store the inertia values.
  * Created a for loop to compute the inertia with each possible value of k.
  * Created a dictionary with the data to plot the elbow curve.
  * Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
  * Answer the following questions:
    * What is the best value for k when using the PCA data? 4
    * Does it differ from the best k-value found using the original data? No

## Clustered Cryptocurrencies with K-Means Using the PCA Data
* Used the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
  * Initialized the K-means model with the best value for k.
  * Created an instance of K-means, defined the number of clusters based on the best value of k, and then fit the model using the PCA data.
  * Predicted the clusters to group the cryptocurrencies using the PCA data.
  * Created a copy of the DataFrame with the PCA data and added a new column to store the predicted clusters.
  * Creatd a scatter plot using pandas’ plot as follows:
    * Set the x-axis as "PC1" and the y-axis as "PC2".
 
## Determined the Weights of Each Feature on Each Principal Component
* Created a DataFrame that shows the weights of each feature (column) for each principal component by using the columns from the original scaled DataFrame as the index.
* Answered the question: 
  * Which features have the strongest positive or negative influence on each component? PCA1 is most positively influenced by the price_change_percentage_200d feature and most negatively influenced by the price_change_percentage_22h; PCA2 is most positively influenced by the price_change_percentage_30d feature and most negatively influenced by the price_change_percentage_1y feature; PCA3 is most positively influenced by the price_change_percentage_7d feature and most negatively influenced by the price_change_percentage_60d feature.