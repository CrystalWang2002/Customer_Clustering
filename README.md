# Customer Segmentation: Clustering
Using clustering model to identify different customer groups for marketing strategy customization.

## 1. Introduction

**Definition:**

Customer clustering is the grouping of customers based on their similarities to better understand and meet the needs of different groups.

**Significance:**
- Personalized Marketing and Service
- Enhanced Customer Satisfaction and Loyalty
- Increased Sales and Profits
- Predictive Insights and Planning

**About Dataset:**

This dataset comes from Kaggle. It contains 1000+ data items and 27 variables. The main dimensions are people, products, promotions and channels.

## 2. Data Preprocessing

**Data cleaning:** 

Delete NULL value, change the data types, drop outliers, do feature engineering and Scale the feature using the standard scaler.

**Principal Component Analysis:**

<img src="images/0.png" style="width:500px;height:300px;">

I picked eight principal component while maintaining 80% explanatory power for the variance of the variables.

## 3. Clustering Model

**Model introuction:**

<img src="images/1.jpg" style="width:1000px;height:300px;">

**Four different models:**

**K-means**
- Choose cluster number: Calculate distortion score and use Elbow rule to select clusters = 4.

<img src="images/2.png" style="width:500px;height:300px;">

- Calculate average silhouette score = 0.1911.

<img src="images/3.png" style="width:500px;height:300px;">

**Agglomerative Clustering**
- Choose cluster number: use Dendrogram to find clusters with the longest merge distance, and finally set clusters = 3.
<img src="images/4.png" style="width:500px;height:300px;">

- Calculate average silhouette score = 0.2507
<img src="images/5.png" style="width:500px;height:300px;">

**Spectral Clustering**
- Choose cluster number: calculate eigen gaps and select cluster number with highest gap size, and finally set clusters = 3.
<img src="images/6.png" style="width:800px;height:300px;">

- Calculate average silhouette score = 0.1999
<img src="images/7.png" style="width:500px;height:300px;">

**DBSCAN**
- No need to set cluster number in advance, calculate average silhouette score = 0.2487.
<img src="images/8.png" style="width:500px;height:300px;">

- “d_cluster” is the cluster label through DBSCAN
- “-1” label means noisy point
- Distribution of cluster is markedly uneven, and many data points are clustered as noisy point --> Not a suitable model
<img src="images/9.png" style="width:500px;height:300px;">

**Final selection and Cluster distribution:**
- Select Agglomerative Clustering finally
<img src="images/10.jpg" style="width:500px;height:300px;">

- The clusters seem to be fairly distributed
<img src="images/11.png" style="width:500px;height:300px;">

## 4. Exploratory Data Analysis

**Customer Features**
- Kernel Density Estimate plot
- Final analysis shown in profile part
<img src="images/12.png" style="width:500px;height:300px;">

- high income customers have higher total spent.
- Total spent: Cluster2 > Cluster 1 > Cluster 0
<img src="images/13.png" style="width:500px;height:300px;">

- High-income customers do not necessarily make more frequent purchases,may because they prefer high-value goods
<img src="images/14.png" style="width:500px;height:300px;">

**Product Preference**
- Total purchase number: Cluster2 > Cluster 1> Cluster 0
- Cluster 2 spends more than the other two groups on most product categories, especially on “Meat” and “Wine” products.
<img src="images/15.png" style="width:500px;height:300px;">

**Purchase Channel**
- Cluster 1 and Cluster2 is active across all channel. 
- Web shopping: Cluster 1 > Cluster 2, Catalog shopping: Cluster 2 > Cluster1.
- Cluster 0 makes relatively few purchases across all channels, which may indicate that they buy less frequently overall.
<div style="display:flex;">
    <img src="images/16.png" alt="图片1" style="width:50%;">
    <img src="images/17.png" alt="图片2" style="width:50%;">
    <img src="images/18.png" alt="图片2" style="width:50%;">
</div>

**Customer Activation**
- The majority of customers tended not to take up any promotions, cluster2 participated in a relatively high number of promotions
<img src="images/19.png" style="width:500px;height:300px;">

- Cluster2 has the lowest website activity, the other two clusters are similar
<img src="images/20.png" style="width:500px;height:300px;">

## 5. Customer Profile
- Different characteristics
<img src="images/21.jpg" >

- Common characteristics
<img src="images/22.jpg" style="width:500px;height:400px;" >

## 6.Market strategy for different clusters
<img src="images/23.jpg">
<img src="images/24.jpg">
<img src="images/25.jpg">







