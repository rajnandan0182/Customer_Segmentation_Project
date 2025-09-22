# Customer_Segmentation_Project

## 🎯 PS:
 
   Customer Personality Analysis is the process of deeply understanding a company’s target audience. It enables businesses to identify customer needs, behaviors, and preferences, making it easier to adapt products and services to fit different customer groups.

By segmenting customers based on their characteristics, businesses can design more focused strategies. Instead of promoting a new product to every customer in the database, the company can determine which segments are most likely to purchase and direct its marketing efforts toward those specific groups. This not only improves efficiency but also increases the chances of successful customer engagement.

## Data preprocessing & Feature Engineering

1) Handled Missing Values – Imputed null values using the median method.

2) Derived Age Feature – Calculated customer Age from the birth date.

3) Customer Tenure – Created Days_Since_Customer to represent the number of days since enrollment.

4) Family Features – Generated Num_Kids and Fam_Size to analyze household demographics.

5) Campaign Response – Built Num_Accepted, capturing total accepted offers from the last five campaigns.

6) Spending Behavior – Computed MntTotal, representing the total amount spent by a customer in the past two years.

## Exploratory Data Analysis
1)  **Box-plot **
    
)![image](https://github.com/user-attachments/assets/<img width="1147" height="562" alt="Boxplot1" src="https://github.com/user-attachments/assets/89c4cbd6-abbb-4b98-987a-0e4d63d09429" />
    
   
**We decided not to remove outliers, since the Response column is imbalanced.**

2) **Relation Between Education, Income & Response**

 
3) **Does Recency affect Responses?**
   (Recency is the Number of days since customer's last purchase)

  

4) **How have customers spent in the last two years?**
   
  


5) **Does Family Size affect purchases?**

  

6) Purchases made at stores/website/catalog/discount purchases


7) **Checking for patterns in purchases made through store, website and catalog**
 
8) **Older people have more complaints?/ How have people with complaints reacted towards last campaign?**

 

9) **Regular customers seem to be happy**



10) How do features correlate ?

  

**Correlation Coefficients for response:**<br>

# Conclusions after EDA:

1) Customers with basic education usually have lower incomes; higher-income customers are more likely to accept offers.

2) Customers who purchased recently show a higher probability of accepting new offers; inactive customers need re-engagement campaigns.

3) High spenders in the last two years are more likely to accept offers; they should be rewarded with loyalty programs and personalized incentives.

4) Smaller families respond better to campaigns and spend more; larger families may require bundled offers or family discounts.

5) Customers purchasing less via online/catalog channels are less likely to accept offers; improving these channels could increase engagement.

6) Older customers register more complaints, but this does not reduce their campaign participation; better service could strengthen loyalty.

7) Customers who accepted more past offers are more likely to accept current ones; they can be targeted with exclusive deals and early access.

## Dimensionality Reduction



We initially reduced the 22 features to 2 principal components using PCA to visualize the data.


Upon visualizing the data in 2D, we observed that it was challenging to differentiate between the entries with response 0 and 1. So we proceeded to 3 n_components.



We performed clustering, with 3 components using K-means clustering . Here is the Elbow curve:



We visualized the clusters in a 3D plot using the first three principal components."



The 3D visualization helped us understand the separation and distribution of the clusters better.

Realizing that 2 components only explained a small portion of the variance, we increased the number of components to 3, which improved the explained variance but was still not enough. Eventually, we increased it to 7 components, capturing 72% of the total variance



## Visualising the clusters:


# Summary
**Cluster 0 :**

*Comprises of 46% customers (Largest pool)<br>
*Least Income<br>
*Least money spent<br>
*Least Number of purchases<br>
*Large Family size<br>

**Cluster 0 is our largest customer segment, making up 46% of our customer base. These customers generally have the lowest income and spending, along with the least number of purchases. They also tend to have larger families. To better engage this segment, we should consider offering budget-friendly promotions and products that cater to larger families**

**Cluster 1:**

*Oldest Cluster<br>
*low income + low spending<br>
*Long time customer<br>
*Largest Family size<br>
*Highest number of purchases with discount<br>

**Cluster 1 consists of our oldest customers who have been with us for a long time. They have low income and spending but are very loyal and frequently use discounts. This cluster also has the largest family sizes. To retain their loyalty, we should continue providing targeted discounts and special offers, emphasizing our appreciation for their long-term support**

**Cluster 2:**

*High income<br>
*High number of purchases<br>
*Low family size<br>
*Doesnt utilise discounts much<br>

**Cluster 2 includes customers with high income who make frequent purchases. They generally have smaller families and don't utilize discounts much. This indicates that they value quality and exclusivity over discounts. To engage this segment, we should focus on offering premium products and services, possibly through a loyalty program that provides exclusive benefits**

**Cluster 3:**

*Smallest pool (only 9%)<br>
*Highest Income and spending<br>
*Most purchases<br>
*Low family size<br>
*Regular customers<br>

**Cluster 3 is our smallest segment, comprising only 9% of our customer base, but they are our most valuable customers. They have the highest income and spending levels and make the most purchases. These customers are regular shoppers with small family sizes. To retain and reward these high-value customers, we should implement personalized marketing strategies and VIP programs that offer exclusive benefits and experiences.**

