# Data-Science-Competition-for-Revenue-Maximization
Champions for a Data Science Competition under <b>SAS Institute</b> with a team of 4. <br><br>
The project challenged teams to gather novel insights and come up with innovative ways to increase the revenue of a Japanese e-commerce company (Ponpare) based on the existing data they have.  <br><br>
The key is to not only uncover new insights from the data, but also learn to communicate technical findings clearly via a business presentation. This helps in convincing stakeholders to buy-in and successfully implement the proposal, which is crucial in data projects. <br><br>
Full slides is in <b>Summarized(15min)_Group3_Presentation.pdf</b>. I will provide a comprehensive explaination of the project in this README and the link for the Kaggle datasets at the end.
<br><br>

## Customer Segmentation via k-means Clustering
From the datasets, we had the datetime of customers entering the page and purchasing the products, along with the product category and product prices. After some data cleaning, feature engineering and data aggregation for each customer, we identified two important features - (1) time spent on the e-commerce app/website and (2) amount spent per customer that helps the company to cluster the users into 4 different groups. These groups will have different browsing and spending habits which can then be targeted differently by the data models.
<br><br>
![Clustering](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Cluster01.PNG)
<br><br>
## Analysis of customer segments
The clustering identified 4 different types of user groups that are very relatable to our personal experiences as customers or friends that enjoy online shopping. <br> 
1. There are the loyal customers who have spent a lot of time and money on the app because they enjoyed it, aka the <b>"Cash Cows"</b>.
2. Many customers spend a lot of time browsing for deals/offers for cheap products, they are the <b>"Bargain Hunters"</b>.
3. Some customers are very savvy and are on the lookout for good discounts on expensive products on the app. They know what they want and do not spend a lot of time browsing, but go quickly to checkout the items once they confirmed it is a great deal. We call them the <b>"Decisive"</b>.
4. Finally, there are many customers that do not spend a lot of time or money on the app. They might have created an account just for a specific promotion they saw, or realized that they do not enjoy shopping on the app for various reasons and quit. They are the <b>"Uninterested"</b> users.
<br><br>
![Clustering](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Ponpare03_Clustering.jpg)
<br><br>
## Exploratory data analysis - Spending Habits
Within each user group, we compare the difference in the average amount of money spent and number of items bought per year. We can also understand which user group is the major contributor to revenue in the company and how to increase the revenue pie. <br><br>
The results show that Cash Cows and Decisives dominate the revenue pie (93.1%), spending the most money in buying many items from the app. The skewed results show that while the app has very good user loyalty amongst 46% of users, they might be struggling to diversify the revenue stream and attract more users onto the app. 
<br><br> 24% of users in the "Uninterested" group hardly use the app again, and 30% of users in "Bargain Hunters" are only looking for cheap deals that do not bring much revenue for the company. It will be good to investigate further on how to move these users to more profitable groups and encourage them to spend more money.
<br><br>
![EDA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Ponpare04_EDA.jpg)
<br><br>
## Differences in spending habits of users
Within each user group, they have different preferences for the products to buy. For instance, the Cash Cows and Decisives enjoy spending money on big ticket items like Hotels, and regularly on expensive food. On the other hand, the Bargain Hunters are just using the app for Delivery Deals, Gift Cards and cheaper Food. This hints that we should target each user group differently to promote items they will like more. A Market Basket Analysis (MBA) model can be run on each user group to see what set of items users enjoy buying during a shopping session on the app.
<br><br>
![EDA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Cluster03.PNG)
<br><br>
![MBA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/MBA01.PNG)
<br><br>
## Model: Market Basket Analysis (MBA)
After trying out MBA for individual products, we realized that it is too granular and there is no signficant two products that users like to buy together as their catalog of products are too diverse. On the other hand, doing MBA for products of different categories might be too general as there can be differences in products for a certain category. Hence, we decided to bin each product category into three - Low, Mid, High depending on the price range of the product before doing MBA.
<br><br> The result is that we were able to understand consumer spending habits and give targeted recommendations of cross-selling (selling a related product of different category) and up-selling (selling the same category of product at a higher price) to users that have previously purchased items from the app.
![MBA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Ponpare01_MBA.jpg)
<br><br>
## Solution: Changes to the application/website based on MBA
For each user group, their product recommendations will be different as the MBA gives different results. For example, users who are Cash Cows that just purchased an expensive food product will receive recommendations of more expensive food products and also offers to upgrade their food to something more expensive. The effectiveness of the recommendation bar will be monitored and adjusted accordingly based on the changing habits of the user.
![MBA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Upsell01.PNG)
<br><br>
## Exploratory data analysis - Browsing Habits
Users have different browsing and purchasing habits when looking at different categories of products. A graph of average number of views for a product category before purchase VS average price of a category of product was plotted. The log average price (x) is higher for expensive products, while the higher the log average view (y), the greater amount of times a user browses products of same categories before deciding to purchase a product (aka doing product comparison).
<br><br>
![EDA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Views_vs_Purchase.png)
<br><br>
For expensive products, users are more diligent and tend to browse for many options to compare the qualities and price of the product. A person buying a hotel will not rush to buy a hotel but slowly browse through the catalog of hotels before making a decision. Hence, the key is to provide greater varieties of hotel listings, good price range, and a reasonably long discount period.
![EDA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Views_vs_Purchase02.png)
<br><br>
There are also some expensive products like private Lessons and Beauty services (e.g. Salon) that users do not browse a lot before buying. This means that for these products, users might have a lot of brand loyalty to a certain product as long as the price and quality is reasonable. The key is to help users to find their favorite brands and improve customer loyalty.
![EDA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Views_vs_Purchase03.png)
<br><br>
Finally, there are inexpensive products that users will purchase quickly and not browse through other products. This might stem from the fact that consumers are willing to part with their cash if its highly affordable, and the flash deals by the company attract consumers to quickly buy a product before it is sold out. It will be difficult to increase revenue from these high volume, low profit margin products, and hence the key is to entice users to find other expensive products they would enjoy when the flash deals are on.
![EDA](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/bargainhunter.png)
<br><br>
Within each user group, we can analyse the time spent browsing a product using a histogram and Kernel density estimation (KDE) graph. For instance, the Bargain Hunters have a wide range of timings spent looking at a product. The KDE graph shows two peaks, as half of the product views tend to last an average of 7 minutes, while some products are very popular and users will revisit the product after a week (8 days). There are also varying time distributions for each user group. Hence, there is an inspiration to build a model based on the time spent viewing a product to get insights on how it changes the probability of purchase.
<br><br>
## Model: Decision Tree to understand browsing habits of users
![Decision_Tree](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Ponpare02_DecisionTree.jpg)
<br><br>
Initially, the datasets only had the datetime that each user was browsing a product and purchasing it. There was no significant findings on the month, day or hour of purchase. However, after feature engineering and converting the datetime into the amount of time a user looked at a coupon before purchasing it, it became the most significant variable for predicting the probability of purchase of a product for two branches of the decision tree with MSE of 0.05 (very low!). We had (by a stroke of luck) found a feature that heavily affects a response variable, and a decision tree is the perfect model for intepreting the results.
<br><br>
All the coupon/product views of users can be broken down into 4 nodes or types. 77% of product views are unfruitful as they stop looking at a product within 1 minute. On the other hand, 20.7% of product views are fruitful as they go back to revisit the product after a day or a week, and the probability of purchase goes up by more than 100 times (0.13% to 22%). This shows two trends - there are many users who are unable to find the products that they want, and there are some users who are considering a product but a need a further push before purchasing the product.
<br><br>
From our EDA and understanding of browsing habits, the two main aims are to improve user experience of the app to allow them to find the products that they want, and to remind them of products (or highly similar products) they were looking at for long periods of time to entice them to purchase the product. This is illustrated in the red arrow movements (1) and (2) where the probability of purchase will increase.
<br><br>
## Solution: Improve the browsing interface of the app/website
From the data, we realized that majority of product views (77%) do not lead to a purchase. For products that are more expensive (Hotels & Guesthouses), users also tend to browse through many products before making a decision. Hence, the key is to improve the user experience by allowing for easy product search and viewing. In this way, we move users from one leaf node to another in the decision tree (Red Arrow 1) as they are able to find the products that they want and not skip through it quickly.
<br><br>
The product images can be smaller but packed in a tile format with a small summary of the price and product description. Furthermore, horizontal scrolling can be implemented (like Instagram Stories or Snapchat) for users to quickly scroll through products. The next products to be shown in the scrolling process would be through recommendation algorithms such as our MBA model and what the users looked at previously to allow users to find products that they like more easily, leading to higher sales.
<br><br>
On the other hand, for users that are interested in a product and looked at it for over 2 minutes, we can send customized emails and application notification reminders every few days to remind them of the product. We can also target them with good deals of products similar to the one that they have viewed for over 2 minutes as they might be browsing for that particular genre of product. This is moving the customer base from one leaf node to another in the decision tree (Red Arrow 2).

![Decision_Tree](https://github.com/kohjiaxuan/Data-Science-Competition-for-Revenue-Maximization/blob/master/Browsing01.PNG)

## Credits
This project would not have been possible without my talented groupmates - Catherine, Orson and Rachel. This article is the brainchild of all of our ideas and is a summary of our discussions and final presentation. I learned a lot from not just the project, but also all of you and it has made me more excited for working in the data industry!
<br><br>
Dataset obtained from a Kaggle competition - https://www.kaggle.com/c/coupon-purchase-prediction
