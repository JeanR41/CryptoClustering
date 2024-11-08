# CryptoClustering

## Overview

The CryptoClustering project utilizes machine learning to cluster cryptocurrencies based on their price changes over different time periods. By applying K-means clustering and Principal Component Analysis (PCA), the project explores how these techniques can help group cryptocurrencies with similar price behaviors. The analysis shows how clustering can be optimized using PCA for dimensionality reduction and how to visualize these clusters in different ways.

## Ethical Considerations

While this project uses cryptocurrency market data to perform unsupervised clustering, it is important to note that the purpose of this analysis is not to provide financial advice, market predictions, or recommendations. The primary goal is to explore patterns and relationships in cryptocurrency price changes, not to predict the future behavior of the market. 

Cryptocurrencies are volatile and speculative investments, and their market behavior is influenced by a wide range of factors that this analysis does not account for. Any insights drawn from this project should be viewed as a means to better understand the data, not as an indicator for making investment decisions.

## Requirements

To run this project, you will need the following Python libraries:

- `pandas`
- `hvplot`
- `scikit-learn`

## Dataset
The crypto_market_data.csv file contains 41 rows of cryptocurrency data with the following features:

 - **coin_id:** Unique identifier for each cryptocurrency.
 - **price_change_percentage_24h, 7d, 14d, 30d, 60d, 200d, 1y:** Price change percentages over different time periods.

## Analysis Overview
### 1. Data Preprocessing
The data is loaded into a pandas DataFrame, and summary statistics are calculated. The price change percentages are then normalized using StandardScaler to bring all features to a comparable scale.

### 2. Finding the Optimal k for Clustering
The Elbow Method is applied to determine the optimal number of clusters (`k`) for K-means clustering of the original scaled data. The plot of inertia values helps identify the point where adding more clusters provides diminishing returns. The optimal k value found is 4.

### 3. Clustering Original Scaled Date with K-means
Using K-means clustering, the cryptocurrencies are grouped into 4 clusters based on their price change behavior. The clusters are visualized in scatter plots to show how the cryptocurrencies are distributed in terms of their price changes.

### 4. Dimensionality Reduction with PCA
To reduce the complexity of the data, Principal Component Analysis (PCA) is applied, reducing the data to 3 principal components. This helps optimize clustering by focusing on the most important features, improving both performance and interpretability.

### 5. Optimal `k` with PCA Data
The Elbow Method is again applied on the PCA-reduced data to confirm the optimal k. The same value of 4 is found, showing that the dimensionality reduction does not affect the clustering outcome.

### 6. Clustering PCA data with K-means
Using K-means clustering, the cryptocurrencies are again grouped into 4 clusters based on their price change behavior, this time grouped the clusters based on the PCA data. The clusters are visualized in scatter plots to show how the cryptocurrencies are distributed in terms of their price changes.

### 7. Comparing Results
The clustering results from both the original scaled data and the PCA-reduced data are compared visually. Using fewer features (through PCA) makes the clusters easier to visualize, with clearer separation between clusters and potential outliers.

## Key Insights
 - The optimal number of clusters (k=4) was consistent across both the original data and the PCA-reduced data.
 - PCA improved the interpretability of the clustering results by reducing the dimensionality of the data, making the elbow curve and scatter plots more distinct and easier to analyze.
 - By visualizing the clusters, we can better identify outliers, such as "celsius-degree-token" and "ethlend," which are more viaually isolated in the PCA-based clusters.

## Running the Analysis

1. **Install the required dependencies.**

2. **Run the `Crypto_Clustering.ipynb` notebook** to:
   - Load the dataset
   - Preprocess  and scale the data
   - Apply K-means clustering to the original scaled data
   - Perform PCA optimization
   - Apply K-means clustering to the PCA data
   - Visualize the results

## Conclusion
This project demonstrates the power of clustering techniques for analyzing cryptocurrency price changes. By leveraging K-means and PCA, we can group cryptocurrencies based on similar behavior and reduce the complexity of the data for easier analysis. The results reveal patterns in cryptocurrency price movements and help identify which cryptocurrencies are behaving similarly over time.
