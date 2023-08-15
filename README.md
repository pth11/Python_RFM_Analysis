# Python_RFM_Analysis: Customer segmentation

## I. Introduction
### 1. Business question
- SuperStore is a global retail company. The Marketing Department wants to run marketing campaigns during the Christmas and New Year holidays to thank customers for their past support of the company. In addition, potential customers can be exploited to become loyal customers.
- The Marketing Director also proposed a plan to use the RFM model in Python to segment customers, and then launch appropriate marketing campaigns. Analyze the current situation of the company and give suggestions to the Marketing team
- With the retail model of Superstore company, which indicator should be most focused in in the 3 indicators R, F, and M?
### 2. Dataset
Dataset includes 4 different related tables including: transaction information, products information, returned orders of customers purchasing products from 2014 to 2017 and RFM classification
- **Transaction information dataframe** 
- **Returned orders dataframe**: We have to filter orders that were not returned before RFM anaalysis.
- **Segmentation dataframe**: 'Product ID' is not unique because some products have same Product ID but have different Product Name => drop 'Product Name' then remove duplicate records so that 'Product ID' will be unique.
- **Products dataframe**: We have to split each RFM score into single rows
### 3. RFM model
- RFM is a method used for analyzing customer value. It is commonly used in database marketing and direct marketing and has received particular attention in retail and professional services industries
- RFM stands for the three dimensions:
    1. Recency – How recently did the customer purchase?
    2. Frequency – How often do they purchase?
    3. Monetary Value – How much do they spend?
- RFM analysis numerically ranks a customer in each of these three categories, generally on a scale of 1 to 5 (the higher the number, the better the result). The “best” customer would receive a top score in every category.

## II. Data Visualization with Python
![image](https://github.com/thuhuongphan11/Python_RFM_analysis/assets/141643891/90f6a2e2-61b5-4782-aee4-af3e2578bfd8)
![image](https://github.com/thuhuongphan11/Python_RFM_analysis/assets/141643891/4f68b658-6eba-4675-925a-c92c0fda52e2)
![image](https://github.com/thuhuongphan11/Python_RFM_analysis/assets/141643891/ca09e622-6d12-4c39-91e2-975b0fc6f88b)
![image](https://github.com/thuhuongphan11/Python_RFM_analysis/assets/141643891/5ead6a42-d14a-4556-84aa-ff0d146b0808)
![image](https://github.com/thuhuongphan11/Python_RFM_analysis/assets/141643891/c60e2614-4cb0-4e9c-8e59-1bcf44b85c9e)
![image](https://github.com/thuhuongphan11/Python_RFM_analysis/assets/141643891/f1ef3731-e6a2-4422-a5ed-c5e238f5915d)

## III. Insights
### 1. Recency, Frequency and Monetory value of Superstore:
- As a retailer, Superstore should prioritize Recency and Frequency over their Monetary since their most loyal shoppers may make many purchases throughout the year at lower Average Transaction Sizes. However, Superstore's Recency and Frequency do not have many positive signs
- Mean of Frequency is 6 times, which is low for a retail company. This means customer loyalty is not high
- Mean of Recency ~ 166 days, while the median is 83 days, this represents a lot of high Recency values. The larger this index, the higher the customer's tendency to leave.
### 2. 11 segments of Superstore:
- 2 segments with the highest proportion of customers are Potential Loyalist (14.29%) and At Risk (12.14%)
- Negative segments such as Hibernating and Lost accounted for a high proportion of customers, 11.38% and 10.49%, respectively. However, these two groups account for less than 8% of revenue
- The two most positive segments account for less than 17% of the proportion of customers (Champions, 8.98%, and Loyal, 7.84%).
- Potential Loyalist (the ideal segment) has the highest proportion of customers (14.29%), but its revenue proportion is only 9.02%. Meanwhile, the negative segment, At Risk, accounts for 18.24% of revenue
=> In this Christmas - New Year marketing campaign, SuperStore needs to prioritize their efforts to promote the Potential Loyalist group to become Loyal and Champions, and find ways to reconnect with customers in the At Risk group
### 3. Potential Loyalist and At Risk segments
#### 3a. Potential Loyalist
The cart_value decreased in 2 categories Furniture and Technology in 2017 despite the increase in the number of orders and the increase in revenue, specifically:
- Furniture group in 2017 increased the number of orders by 53% (from 62 to 95 orders) but the cart_value decreased by 18% (from 326 USD to 226 USD)
- Technology group in 2017 increased the number of orders 38% (from 40 to 74 orders) but the cart_value decreased by 31% (from 383 USD to 266 USD)
There is a change in the buying behavior of 2 channels Consumer and Home Office in 2017. They tend to place more orders but the value of each order is lower, specifically:
- Consumer group in 2017 increased orders by 40% (from 112 to 186 orders) but cart_value decreased by 26% (from 292 USD to 214 USD).
- Home Office in 2017 increased orders by 76% (from 30 to 53 orders) but cart_value decreased by 22% (from 276 USD to 225 USD
#### 3b. At Risk
In 2017, all 3 Categories showed a decrease in orders and revenue, 2 Categories Office Supplies and Technology experienced a decrease in cart value:
- Cart value of Office Supplies group in 2017 decreased by 23% (from 263 USD to 203 USD)
- Cart value of Technology group in 2017 decreased by 22% (from 836 USD to 651 USD)
- Meanwhile, the Furniture group has an increase in the cart value from 350 USD to 476 USD
In 2017, while the Consumer and Corporate channels experienced a decrease in the number of orders, revenue and cart value, the Home Office channel, despite a decrease in the number of orders, still recorded an increase in revenue and cart value:
- Consumer group reduced the number of orders by 17% and cart value by 38%
- Corporate group reduced the number of orders by 26% and cart value by 5%
- Office group  reduced the number of orders by 25% but cart value increased by 73%

## IV. Recommendations
Superstore should focus more on enhancing Recency and Frequency performance.
In this Christmas - New Year marketing campaign, SuperStore needs to prioritize their efforts to promote the Potential Loyalist group to become Loyal and Champions, and find ways to reconnect with customers in the At Risk group
Reccomendations for Potential Loyalist segment
- Special promotions are needed for customers that buy products in the same category and reach a cart_value above 238.68 USD (current average cart_value of this segment) to motivate customers to buy related products and increase the cart value.
- Offer membership/loyalty program, focusing on 2 channels Consumer and Home Office and 2 categories Furniture and Technology.
- Recommend to customers the best-selling Sub-category such as Paper, Binders, Furnishings, Storage and Art
Recommendations for At Risk segment:
- Channels and Categories with a high number of return orders all have a decrease in the number of orders, revenue and cart value => Need to do a deeper analysis of the correlation between these factors
- Start a new program (exchange points/gifts/vouchers) for customers in these groups to get them to do a survey to find out the main reason why these customers have not come back for a long time.
- Since nearly 60% of orders use Ship mode Standard Class, the free upgrade to Second Class policy can be included in the new campaign
- Send personalized emails to provide useful information and recommend to customers about best-selling Sub-category such as Binders, Paper, Furnishings, Phones and Storage
