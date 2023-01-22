# Customer Segmentation Analysis and Product Recommender System

## Dataset
The source of the [here](data)

There are two parts of the analysis
1. Customer segmentation using RFM
2. Recommendation system using user-based implicit collaborative filtering


### Part 1: RFM Analysis
 - I am using RFM (Recency, Frequency, Monetary) analysis with 5x5x5 dimensions.
 - Customers who have similar RFM scores tend to exhibit similar behaviors. 
 - To make it more efficient for marketing campaigns, I group customers with similar R-F scores together to form marketing groups.

**Results:**

Working on each of the 125 RFM groups individually may not be a feasible option as some groups are too small, making it difficult for marketers to focus on too many groups. To address this, we combine some of the groups based on their RFM characteristics, and also assign customer segmentation for marketing purposes to provide marketers with a clear objective


#### Segment Description
- VIPs: For those whose recent purchases are within 180 days and have bought more than 5 times in a year.
- Potential loyalists: For those whose recent purchases are within 180 days and have bought 3-4 times in a year.
- Need to focus: For those who have bought only 2 times in the past year.
- Good old friends: For those who have bought more than 3 times didn't purchase within 180 days.
- New customers: For those who have only purchased once and their recent purchase is less than 30 days.
- Hibernating: For those who have only purchased once, and their recent purchase has been more than 30 days.


#### Actions
- VIPs: Keep them happy (at any cost).
- Potential loyalists: Should give incentives to increase their tendency to buy more times on the website.
- Need to focus: They have moderate monetary contributions, but the marketer should turn them in the potential groups ASAP; otherwise, they may turn to hibernate.
- Good old friends: They were loyal, but it seems we are losing them. Give them incentives to recall their good memories (recommendation comes in because we have their purchase history) and make them have a recent purchase.
- New customers: Make them want to purchase the second time; otherwise, they'll go hibernating.
- Hibernating: We don't know them much, and they didn't purchase within a month. We need to guess to motivate them to buy another time.


![image](img/RFM.PNG)


#### Short Summary
1. High-frequency buyers (especially F-score = 5, frequency > 6/year) contribute the most to the company.
2. High frequency and most recent buyers (high F and R scores) are the ones we should definitely keep.
3. Medium Frequency (F-score = 3) are the groups we want to save (give incentives), especially for those ones who have R-score > 2.
4. The number of new customers is quite low, so the company should lunch some customer acquisition campaigns.
5. There are quite some low frequency and low recency score buyers, which means the customers may lose interest in the website or products. The company should dive deep to investigate and save this group because new customer acquisitions are expensive.


### K-Means:
By using the RFM feature, we use the K-Means algorithm to perform *customer segmentation*

#### Results from K-Means:
![K-Means](Img/kmeans.PNG)

### Gaussian:
This model uses the Gaussian method to form a cluster.

#### Results of the Gaussians:
![Gaussians](Img/Gaussians.PNG)



### Part 2: Recommender Systems

This recommendation system can be used by the company to **promote the recommended product** after the user **purchase or interested** with the **currently viewed product**. By conduct this kind of promotion, your company does not randomly promote product. On the other hand, the product promoted has high correlation. Therefore, the customer **may purchased more** since interest product appeared frequently.


### Note

Step-by-step python anlaysis and discussions can be found [here](Customer Segmentation and Product Recommender .ipynb) 
