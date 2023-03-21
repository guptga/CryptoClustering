# Crypto Market Analysis : Machine Learning (Unsupervised)
![image](https://resize.indiatvnews.com/en/resize/newbucket/730_-/2021/11/crypto-1637913891.jpg)

Cryptocurrencies are experiencing their worst crisis since the arrival of the first crypto assets and virtual currencies in the 1990s and their democratization in the 2010s.

Bitcoin had an unprecedented tumble in late 2020 and has yet to recover. In addition to this sharp decline, there is much discussion about the worrisome collapse of some so-called stablecoins, which are supposed to be less volatile.

This is compounded by the fall of cryptocurrency giants, particularly due to allegations of fraud in cases like the FTX scandal. At its peak, FTX had one million users and was the third-largest cryptocurrency exchange in terms of volume.

Experts agree that the aftershocks of its collapse have hit investors hard and will likely slow the pace of crypto asset adoption for the next few years.

###### (Source: https://theconversation.com/cryptocurrencies-are-in-crisis-but-they-are-not-going-to-disappear-197777) 

### Machine Learning

Machine learning uses data and algorithms to simulate human learning, enabling machines to improve their accuracy over time. It powers various applications such as chatbots, autonomous vehicles, and medical diagnosis systems. In unsupervised machine learning, programs identify patterns in unlabeled data to find trends that humans may not have been explicitly searching for. However, it is important to be aware of the limitations and potential biases of machine learning, and to ensure proper validation of the output to mitigate any negative impacts.


### Unsupervised Machine Learning

Unsupervised machine learning is a type of machine learning in which a computer program identifies patterns in unlabeled data without explicit guidance or supervision from humans. Unlike supervised learning, in which the program is trained on labeled data with known outcomes to predict future outcomes, unsupervised learning discovers patterns or relationships in data that may not be easily identified by humans. Clustering and association rule mining are common techniques used in unsupervised learning. The goal of unsupervised learning is to uncover hidden structures in data and discover useful insights that can be used for decision-making.

#### To further explain by examples

For example, an e-commerce company might use unsupervised learning to group customers into different segments based on their purchasing behavior, such as how frequently they buy, what types of products they buy, or how much money they spend. By clustering customers into different groups, the company can then create targeted marketing campaigns for each segment, tailored to their specific preferences and needs.

Another example is anomaly detection, where the program identifies unusual patterns or outliers in data. For instance, a cybersecurity company might use unsupervised learning to detect anomalies in network traffic, indicating potential security breaches or threats that need to be investigated. By using unsupervised learning, the program can identify new and unexpected patterns of behavior that might not be detected using traditional rule-based approaches.



### Goal

The aim of this case study is to assess the effectiveness of unsupervised machine learning in analyzing a dataset to identify the potential of various models to extract insights and enhance the predictability of diverse cryptocurrencies.


### Methodology

In essence, once the data is prepared, which involves normalizing the dataset using the StandardScaler module from SciKit-Learn, the next step involves testing the data using a specific methodology to identify the most effective way of measuring its predictive capability.

Firstly, step involves using the elbow method to identify the optimal value for k (the ideal number of clusters) and applying the K-means clustering algorithm to the original scaled DataFrame to cluster the cryptocurrency dataset accordingly.

Secondly, we optimize our clusters by utilizing Principal Component Analysis (PCA), which involves reducing the dimensionality of the data while retaining its important features. Then, we rerun the K-means clustering algorithm using the PCA data to further refine our model.

#### Defining Clustering, K-means, Principal Component Analysis (PCA) & Elbow Method

Clustering is a technique used in unsupervised learning that involves grouping similar objects together into clusters or segments based on their features or attributes. In clustering, the algorithm automatically identifies similarities and differences between data points and groups them accordingly without being explicitly told what the clusters should look like.

The objective of clustering is to maximize the similarity of the objects within a cluster while also maximizing the differences between clusters. Clustering is useful in identifying natural groupings within data, such as identifying customer segments based on purchasing behavior or grouping social media users based on their interests. The most common clustering algorithms are K-means clustering, hierarchical clustering, and density-based clustering.  

###### K-means clustering is a popular algorithm used in unsupervised machine learning to cluster data points into k number of clusters based on similarity of features. The algorithm works by randomly initializing k number of centroids (cluster centers) and assigning each data point to the nearest centroid. Then, the centroids are updated by taking the mean of all the data points assigned to it, and the assignment of data points to clusters is updated based on the new centroids. This process is repeated until the centroids no longer change or a set number of iterations is reached.

The K-means algorithm is sensitive to the initial placement of centroids, so multiple runs with different initializations may be necessary to obtain the best clustering results. The elbow method is commonly used to determine the optimal number of clusters k by plotting the within-cluster sum of squares (WCSS) against k, and choosing the k value at which the decrease in WCSS starts to level off, forming an elbow shape in the plot.

K-means clustering is widely used in applications such as image segmentation, customer segmentation, and anomaly detection. However, it has limitations, such as being sensitive to outliers and the requirement of specifying the number of clusters in advance.

###### Principal Component Analysis (PCA) is a technique used to reduce the dimensionality of a dataset while retaining most of the important information. PCA is commonly used in unsupervised learning and data preprocessing to simplify the data and speed up machine learning algorithms.

PCA works by identifying the directions of maximum variance in the data and projecting the data onto a lower-dimensional subspace that captures most of the information. The directions of maximum variance are called principal components, and the number of principal components retained corresponds to the amount of variance in the data that we want to retain.

PCA is useful in many applications such as image processing, finance, and genetics. It can be used to visualize high-dimensional data in two or three dimensions, to remove noise or redundancy in data, and to identify patterns or clusters within the data.

One limitation of PCA is that the principal components may not be easily interpretable, meaning that it may be difficult to understand the relationship between the original features and the reduced components.

######  The Elbow Method is a graphical approach to determine the optimal number of clusters in a dataset. It works by plotting the percentage of variance explained by the clusters against the number of clusters, and looking for the "elbow" point where the percentage of variance explained starts to level off. The idea is to choose the number of clusters where adding another cluster doesn't result in a significant gain in variance explained.

###### The Elbow Method is called so because the resulting plot typically looks like an arm bending at the elbow. The "elbow" of the curve is the point of inflection where the gain in explained variance starts to diminish rapidly.

The Elbow Method is widely used in unsupervised learning applications such as clustering, where the goal is to group similar data points together in clusters. The optimal number of clusters obtained from the Elbow Method can then be used to train a clustering algorithm, such as K-means, on the dataset.. 

### Results and Observations

Once the data was imported and stored in a DataFrame, I computed summary statistics and created visualizations to better understand the structure of the data.


![image](https://user-images.githubusercontent.com/116124534/226521857-acf976c9-2785-44ff-946c-97e52de83464.png)

Due to the high variability present in the raw data, I applied a normalization step using StandardScaler before conducting the analysis.

![image](https://user-images.githubusercontent.com/116124534/226522677-dfa050c8-b2e9-4914-9004-ccba04ae5898.png)

Using the Elbow method involves testing different values of K, which represents the number of clusters, and calculating the WCSS, which measures the sum of the squared distance between each point and the centroid in a cluster. Plotting the WCSS against K produces a graph with an elbow shape, where the optimal value of K is where the graph changes rapidly before becoming almost parallel to the X-axis. The goal of clustering is to create meaningful clusters where data points within a cluster are close together and far from other clusters. Inertia, which is the sum of squared distances of samples to their closest cluster center, is used to measure how far away the points within a cluster are, with smaller inertia indicating better clustering results.

After iterating through 10 K-values, it was found that four clusters provided a turning point in the inertia and resulted in the ideal choice for clustering. When using PCA, the Elbow curve still pointed towards four clusters as the best value for K. However, the inertia at this point varied between the original data and PCA, with the latter resulting in a significantly lower inertia value of 50%. Comparing the elbow plots at K=4, the PCA method yielded stronger clustering results than the original model, as indicated by the lower inertia value.

![image](https://user-images.githubusercontent.com/116124534/226523039-e089dd9e-7436-4118-b052-ed32ce658a40.png)

The scatterplot generated by the original Cryptocurrencies K-Mean Clusters with 4 clusters was not clearly defined.es (K-Mean Clusters=4)

![image](https://user-images.githubusercontent.com/116124534/226523163-8cfcf83f-f1a5-4011-9c96-1b44ef914e46.png)

When applied PCA with 3 features and found that the combined components explained 90% of the total variance. Explained variance is useful in assessing the importance of each component and can be used to assess the quality of a machine learning model. When the overall sum of the two variance ratios is low and the plot is not informative, using a 3rd principal component can be beneficial. The scatterplot generated with the PCA results showed a more defined clustering with clear boundaries.

![image](https://user-images.githubusercontent.com/116124534/226523489-b8b0df9b-fb94-4461-98fb-ba7cbc7acafe.png)

### Conclusion
The cluster analysis results showed that using fewer features with PCA led to a clearer and stronger clustering effect, as seen in the elbow plot and scatter plots. Using PCA resulted in a higher reduction rate of initial inertia compared to standardized data. The reduction of dimensionality with PCA correlates to a reduction in variance of the clustered data, leading to a stronger clustering effect.
