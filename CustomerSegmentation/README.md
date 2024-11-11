## Customer Segmentation (Practice Project)

### Goal of the project:
1. To understand if there is a relationship between different groups of customers based on information we have about them.
2. Moreover, this analysis will group all existing members and give us insights into trends, such as overall groups from different sources. This can inform the marketing team and         provide insights into where to invest more resources during marketing campaigns.

### Process:
#### Exploratory Data Analysis:
What we know about the dataset?

It’s a CSV based on 365's database, where we’ve combined information from an onboarding survey, student engagement data, and the customer lifetime value.

The dataset consists of student information of over 3,800 individuals from the 365 program. The data has been preprocessed and in addition, the volume of the dataset has been restricted and anonymised to protect the privacy of the customers. 										
										
| **Variable**      | **Data type** | **Range**                | **Description**                                                                                                                                                           |
|-------------------|---------------|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| minutes   watched | numerical     | Integer                  | The number of minutes a student has watched since joining the program                                                                                                     |
| CLV               | numerical     | Integer                  | The Customer Lifetime Value, or CLV, shows the total amount of revenue generated by that customer                                                                         |
| Region            | categorical   | {0,1, 2}                 | This is the geographical region where the student comes from. 1. USA, Canada, United Kingdom, Australia 2. Western Europe 3. Rest of the World                            |
| Channel           | categorical   | {1, 2, 3, 4, 5, 6, 7, 8} | This is the channel through which the customer has learned about the 365 program 1. Google  2. Facebook 3. Youtube 4. LinkedIn 5. Twitter 6. Instagram 7. Friend 8. Other |	

Steps Performed during EDA:
1. Data Loading and Exploration
2. Data Cleaning and Preprocessing
3. Feature Engineering
4. Data Viz and Correlation Analysis

#### Model Implementation
Implemented two clustering techniques: K-means and Hierarchical Clustering.

Opted for the results of hierarchical clustering.

Possible reasons why the results of the two algorithms might differ:
Different methodologies: Hierarchical clustering builds a tree (or dendrogram) of clusters by successively splitting or merging them. The decision to split or merge can be based on various algorithms and criteria. On the other hand, k-means tries to find a predetermined number of clusters (k) that minimizes the within-cluster variance.

Initial setup sensitivity: K-means is highly sensitive to initial starting conditions—i.e., the initial placement of the centroid of each cluster. Different runs give different results. Hierarchical clustering is deterministic and will always provide the same result with the same data.

Cluster shape: K-means works best with spherical and evenly sized clusters. It might not do a good job if the clusters have irregular shapes, varying sizes, or densities. Hierarchical clustering does not have these assumptions.

#### Model Evaluation and results:
Created a summary table to analyze the algorithm's results and the resulting clustering to group the data by segments. Additionally, added the number of observations it contains and the proportion of these observations for each segment.

Anglo-Saxon - USA, Canada, United Kingdom, Australia
WE - Western Europe
World - Rest of the world

CLV/ Expenditure: 
1. High : >=140
2. Moderate : >=100 and <140
3. Low : <100

minutes_watched/ Engagement: 
1. High : >=1900
2. Moderate : >=1200 and <1900
3. Low : <1200

Clusters/ segments were named accordingly after analysing the summary table as:
| **Cluster**      | **No of Observations** | **Description** 														  |
|------------------|------------------------|-----------------------------------------------------------------------------------------------------------------------------|
|Instagram Users   |289			    | discovered the channel through Instagram, are from all over the world, moderate level of engagement and expenditure         |
|World Multi-channels   |798			    | discovered the channel through a mix of Facebook, Youtube and Other platforms, are from all over the world, highest level of engagement and moderate expenditure         |
|Googlers in Europe and Anglo-Saxon   |343			    | discovered the channel through Google, are from Western Europe, US, UK, Cananda, Australia, high level of engagement and highest expenditure         |
|Friend's influence   |478			    | discovered the channel through their friends, are from all over the world, high level of engagement and moderate expenditure         |
|LinkedIn Connectors   |461			    | discovered the channel through LinkedIn, are mostly from rest of the world with some from Western Europe, moderate level of engagement and expenditure         |
|Google explorers   |328			    | discovered the channel through Google, are from all over the world, moderate level of engagement and low expenditure         |
|Anglo-Saxon Mix   |1079		    | discovered the channel through Facebook, Youtube, LinkedIn and Other platforms, are mostly from US,UK, Canada and Australia with some proportions from Western Europe, moderate level of engagement and high expenditure         |
|Twitter followers   |58			    | discovered the channel through Twitter, are from all around the world, lowest level of engagement and lowest expenditure         |


#### Data Interpretation
Clusters: 
1. Around 48% of the users are from the US, Canada, United Kingdom, Australia and Western Europe ,and over 52% from the rest of the world.
   
2. Focusing on the smallest segment/cluster, Twitter followers, with only 58 observations. Based on the characteristics of the cluster, concluded that the efforts on Twitter bore 
   little fruit. 
   Suggestion would be to reduce spending there to a minimum. And invest little resources to upload content to the platform because the results are unsatisfactory, perhaps due to 
   the turmoil of the platform in recent months. Marketing could become an early adopter of a new competitor platform, such as Threads.

3. Examining those who frequent LinkedIn. A significant segment—close to 12% of all customers, with average spending. Their average watch time is around 1763. minutes. While 
   around 9% frequent Google and have average watch time over 1800 minutes.

4. World Multi-channels cluster with an impressive average watch time of 2889 minutes, with over 80% of users from rest of the world. It would be worth exploring how these 
   students interact with the platform and why their group was more motivated to study. But this would be the focus of a different analysis on engagement.

Performance by region: 
1. Overall, the Anglo-Saxon channel had the best performance and the highest CLV. Customers from the USA, Canada, The UK, and Australia make up the largest customer segment from 
   that region. And the Anglo-Saxon Mix has the largest segment, with over 1079 customers from that region. The second largest segment is the rest of the world.

2. The fewest customers are from Western Europe. Considering the initial hypothesis of exact spending for all three regions, it is concluded that Western Europe’s marketing 
   efforts are insufficient.
   
CLV: 
1. The two highest-paying clusters are the "Googlers in Europe and Anglo-Saxon" and "Anglo-Saxon Mix". The Anglo-Saxon countries top the list of spending. When looked at the channels— through which these two segments come to the platform—we see a mix between Google and YouTube.

Based on that information, we advise marketing to focus on these acquisition channels for these regions and increase spending. This would be worthwhile because the CLV of these customers is the highest across our customer segments—meaning they are worth pursuing.

And what about the remaining regions and their channel of acquisition?

For the rest of the world, Google is the most successful channel in terms of conversion, followed by Youtube, which is why it should be the primary source for attracting customers from these regions. LinkedIn is a platform that provides excellent organic reach; many students share their certificates and spread the word organically.







