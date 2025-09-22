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
    
<img width="1147" height="562" alt="Boxplot1" src="https://github.com/user-attachments/assets/89c4cbd6-abbb-4b98-987a-0e4d63d09429" />
<img width="1127" height="562" alt="Boxplot2" src="https://github.com/user-attachments/assets/7f4165d8-ac28-445e-8b5b-db3800fdeca2" />

    
**We decided not to remove outliers, since the Response column is imbalanced.**

2) **Relation Between Education, Income & Response**
   <img width="847" height="536" alt="responses2" src="https://github.com/user-attachments/assets/52895d51-5d74-4745-9ff2-ea166232794c" />
   <img width="828" height="542" alt="Responses" src="https://github.com/user-attachments/assets/53963caa-6d47-4361-a433-153d744742e8" />
   <img width="822" height="537" alt="responses1" src="https://github.com/user-attachments/assets/16db157e-0e58-4eac-b660-fbd500cf67c4" />




 
4) **Does Recency affect Responses?**
   (Recency is the Number of days since customer's last purchase)
   <img width="770" height="532" alt="responses3" src="https://github.com/user-attachments/assets/de81d85e-1631-4123-9d4f-6e14f676c4d9" />


  

6) **How have customers spent in the last two years?**
   <img width="732" height="661" alt="Screenshot 2025-09-23 002733" src="https://github.com/user-attachments/assets/aebe2ed6-a79c-4d40-9b00-bae2483b51cd" />
   <img width="810" height="547" alt="Screenshot 2025-09-22 235516" src="https://github.com/user-attachments/assets/bf752530-669a-4cd4-9335-e7c97e643878" />


  


7) **Does Family Size affect purchases?**
    <img width="772" height="533" alt="Screenshot 2025-09-22 235538" src="https://github.com/user-attachments/assets/2c93349f-c9b4-43e1-beaf-a0b8c68bf73b" />
    <img width="808" height="536" alt="Screenshot 2025-09-22 235609" src="https://github.com/user-attachments/assets/91ad68bc-9d60-4256-bf2c-3ff844b2dadb" />



  

9) Purchases made at stores/website/catalog/discount purchases
    <img width="1177" height="295" alt="Screenshot 2025-09-22 235628" src="https://github.com/user-attachments/assets/826af556-a7f5-4bb8-acb0-3ffff64a3b38" />



11) **Checking for patterns in purchases made through store, website and catalog**
  <img width="1227" height="762" alt="Screenshot 2025-09-22 235653" src="https://github.com/user-attachments/assets/0d298f2f-36c4-4bb2-b1ee-f51589c21bb5" />

 
13) **Older people have more complaints?/ How have people with complaints reacted towards last campaign?**
 <img width="772" height="540" alt="Screenshot 2025-09-22 235745" src="https://github.com/user-attachments/assets/370ddc90-4f4f-4c40-bc58-3cae5f8e014c" />


 

15) **Regular customers seem to be happy**
    <img width="773" height="533" alt="Screenshot 2025-09-22 235803" src="https://github.com/user-attachments/assets/06eebefd-bd1e-4090-9c2c-b6d6138edecd" />




17) How do features correlate ?
  <img width="950" height="766" alt="Screenshot 2025-09-23 001100" src="https://github.com/user-attachments/assets/0798a696-adba-46e0-8244-456a84f197bc" />


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

<img width="787" height="537" alt="Screenshot 2025-09-23 000148" src="https://github.com/user-attachments/assets/76bf5b02-bc26-4a08-9393-8831ca9a0def" />


We initially reduced the 22 features to 2 principal components using PCA to visualize the data.
<img width="747" height="692" alt="Screenshot 2025-09-23 001159" src="https://github.com/user-attachments/assets/9cda064a-c6db-4007-b286-47eac2573907" />



Upon visualizing the data in 2D, we observed that it was challenging to differentiate between the entries with response 0 and 1. So we proceeded to 3 n_components.
<img width="941" height="812" alt="Screenshot 2025-09-23 001256" src="https://github.com/user-attachments/assets/369e6557-2071-4e9a-83b0-1805aa8f947f" />




We performed clustering, with 3 components using K-means clustering . Here is the Elbow curve:
<img width="685" height="411" alt="Screenshot 2025-09-23 001320" src="https://github.com/user-attachments/assets/c2768b32-81b2-4d6f-bec6-4ac55dcade5c" />




We visualized the clusters in a 3D plot using the first three principal components."
<img width="1536" height="476" alt="Screenshot 2025-09-23 001355" src="https://github.com/user-attachments/assets/a90f81b4-c66c-4ec9-ae44-94c68b90dfe6" />




The 3D visualization helped us understand the separation and distribution of the clusters better.

Realizing that 2 components only explained a small portion of the variance, we increased the number of components to 3, which improved the explained variance but was still not enough. Eventually, we increased it to 7 components, capturing 72% of the total variance
<img width="685" height="411" alt="Screenshot 2025-09-23 001320" src="https://github.com/user-attachments/assets/62732eaa-0ec3-4aa5-8ede-65fb27d88bee" />
<img width="1127" height="442" alt="Screenshot 2025-09-23 001451" src="https://github.com/user-attachments/assets/76e8f5f5-655d-4aa6-9530-e38b1f9b28d0" />





## Visualising the clusters:
<img width="796" height="491" alt="Screenshot 2025-09-23 001513" src="https://github.com/user-attachments/assets/a45ea3f0-2324-4df0-be0e-559efdaa6487" />
<img width="1100" height="681" alt="Screenshot 2025-09-23 001705" src="https://github.com/user-attachments/assets/7dcb1adf-57c1-4c8c-868a-45dd0f64bc95" />
<img width="757" height="503" alt="Screenshot 2025-09-23 001642" src="https://github.com/user-attachments/assets/77758c94-c60a-4aca-aa77-1051983b7c6a" />
<img width="703" height="482" alt="Screenshot 2025-09-23 001625" src="https://github.com/user-attachments/assets/7c6068cb-df48-4495-9602-e329e02e3442" />
<img width="707" height="487" alt="Screenshot 2025-09-23 001610" src="https://github.com/user-attachments/assets/d3bbda83-826b-4d45-8af3-9993aaf33918" />
<img width="757" height="485" alt="Screenshot 2025-09-23 001553" src="https://github.com/user-attachments/assets/e6df32cd-995e-4d19-a0de-2769ca5c4c3f" />
<img width="987" height="622" alt="Screenshot 2025-09-23 001537" src="https://github.com/user-attachments/assets/f1dff356-81d5-4666-9fa4-aa1000c4d91a" />










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

