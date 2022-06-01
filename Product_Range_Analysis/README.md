# [Product Range Analysis - International Online Shop](https://nbviewer.org/github/cheziman/My_Projects/blob/main/Product_Range_Analysis/product_range_CheziM_p100.ipynb)
[Project's notebook - click here to open using nbviewer (recommended)](https://nbviewer.org/github/cheziman/My_Projects/blob/main/Product_Range_Analysis/product_range_CheziM_p100.ipynb)

[Tableau dashboard - click here to see the dashboard on Tableau public](https://public.tableau.com/app/profile/chezi6122/viz/Practicum100Productrangedashboard/Practicum100Productrangedashboard_CheziMana)

# Description
This project is a product range analysis of a large ECommerce service, it is the main part of the final project to the Practicum100 Data analysis program by Yandex.
The goal is to perform a freestyle prodocut range analysis on the data.

## Some of the methods used in the project
- Statistical testing (Mann Whitney in this case).
- Apriory (association rule for market basket analysis - finding combinations of same items in an invoice).
- Regex / string manipulation.
- Categorization of products based on keywords
- EDA and Preprocessing data, dealing with anomalies.
- Various visualizations.

And more and more

# Favorite graph taken from the project
- This graph shows the correlation between revenue and quantity sold of products. But not only.
- ARPU stands for average revenue per unit (avg price), the bigger the dot the larger the price.
- Category is resembled by color.

a short explanation and a couple more graphs can be seen in the [images folder](https://github.com/cheziman/My_Projects/tree/main/Product_Range_Analysis/images).

![prod_rev-quant_dist.jpeg](images/prod_rev-quant_dist.jpeg)


# Project summary and Conclusions
After cleaning and processing the data, there are 3,779 products spread in 9 categories, and 4,333 unique customer ids, whom together with the unregistered customers, purchased in 19,769 invoices, for total revenue of 9,984,772 in roughly one year (Nov-29 2018 to Dec-07 2019).

The analysis took focus on products that were sold during the year, as a full annual analysis, and not broken into seasons or any timestamps. 

### Categories:
- The 3 categories with highest revenue are:
    - **"Home and living"** (2,280,066).
    - **"Kitchen and dining"** (1,907,384).
    - **"Storage and containers"** (1,724,048).
    
- The first two; "home and living" and "kitchen and dining" are also the largest categories with most products.
- "storage and containers"  has the most revenue per product (6,246), almost double than the "kitchen and dining" category which has the second highest average revenue per product (3,406).

- "Arts and crafts" and "decorations" sold the highest amount of units, but their revenue was not as great as the previous categories (total of 1,435,159 and 1,068,673).
- The "jewlerry" category is not successful to say the least. 
    <br>yes, it is very small in it's product selection, but it is also very small in its average revenue per product - only 185 average revenue per product.
    <br>For comparison - "accessories" is the second worse in average revenue per product of 1,834, and "storage and containers" is the highest in average revenue per product of 6,246!.


### Hypotheses testing
- We tested if there is a statistically significant difference in revenue between:
    - Low priced items (0-1) - and - mid priced items (2-5). 
    - Mid priced items (2-5) - and - high priced items (8 and above).
- The "Mann Whitney U" test was selected as the revenue distribution was negatively skewed and had outliers.
- **The test proved that there is a statistically signifcant difference in revenue of products belonging to the different price ranges.**
    <br> In both hypotheses, The null hypothesis that claim the revenue is equal between the price range groups was rejected with a very low pvalue:
    - Testing **low priced** and **average priced** items revenue with alpha level of 0.05 produced a pvalue of 0.00004.
    - Testing **mid priced** and **high priced** items revenue with alpha level of 0.05 produced a pvalue of 0.0054.

### Price and revenue

#### What is the price range that makes the most revenue
Following the hypotheses testing. It was found that regardless of quantity sold, the higher the price range is, the higher the revenue:
- Low price products (0-1), has the least revenue of up to 2000 for most products. 
    - The average revenue is 599, and the median is 1,189. the highest revenue is 51,354.
- Mid price products (2-5), has medium revenue of up to 3000 for most products.
    - The average revenue is 684, and the median is 3,004. the highest revenue is 106,471.
- High price products (8 and above), has the most revenue of up to 4000 for most products.
    - The average revenue is 1,007, and the median is 3,446. the highest revenue is 174,484.
    
#### More on price and revenue
- Products with **VERY** high revenue has an average price of about 10 or lower. But there are only several such items.
- There are also products with great revenue and average price of 10 and even 30 or more.
- Products with high price sell in smaller quantities AND for high revenue.
- Products of a very low price has to sell at least 5000 pieces to make a good revenue.
- Home and living has some products with a very high prices and small quantity sold, these are mostly furnitures, they make good revenue because their price is high, and probably justified, or not too high to deter customers.
- Products with high average price sell in smaller quantities AND for higher revenue  than products with a low price range.

- It is important to remember that revenue is not profit, as there is no cost data available to calculate profit with, revenue is the next best metric.
- The combination of medium ranged price and a healthy amount of sold units is key for having a great overall revenue.

#### Top 3 products with highest revenue are:
1. Regency Cakestand 3 tier has sold 13,879 units, for **174,485 revenue**. Which is 12.57 a piece.
2. White hanging heart t-light holder has sold 37,952 units, for **106,471 revenue**. Which is 2.81 a piece.
3. Party Bunting has sold 18,295 units, for **99,504 revenue**. Which is 5.44 a piece.
- These products are not among the high priced items range, their average revenue per unit is between 2.81 to 12.57.
    - These products also sold a very high amount of units.

### Products purchased in the same cart: <br>A product of a certain style will often sell with the same product of a different style
By using association rules and Apriori algorithm, It was concluded that:
- Some of the common item combinations in invoices:
    - A herb marker of certain herb, and other herb markers.
    - Regency tea plate of a sort, with regency tea plates of other sort.
    - Tree decorations, with different tree decorations.
    - Poppy's playhouse set parts, with other playhouse parts.
    - Jam jars with colorful lid, with jam jars with lids in different colors.
    - Polkadot cup of a color, and other color polkadot cups.
- **Basically when a customer is purchasing an item that has certain style and theme, it is likely to to be purchased with another item of the same type but in different style.**

### Quantity and frequency
#### Most selling products are:
1. Popcorn holder has sold **56,921 units**, for 51,354 revenue. Which is 0.90 a piece.
2. World war 2 gliders assorted designs has sold **55,047 units**, for 13,842 revenue. Which is 0.25 a piece.
3. Jumbo bag retrospot has sold **48,474 units**, for 13,842 revenue. Which is 0.25 a piece.

- These items average revenue per unit ranges between 0.25 to 1.95, so while these sell many units, their total revenue is smaller than that of oter items that were sold in smaller quantity.
- Top customers who purchased these products purchased as much as 20% of the total units sold.<br>
- The average customer purchased from 10 to 50 units in total which is not even 1% of the total sold units.


#### The following items showed in more than 10% of all invoices
- White hanging heart t-light holder - 11.46% of invoices
- Jumbo bag red retrospot - 10.57%
- Regency cakestand 3 tier - 10.06%


Respectively, these items are also sold a very large quantity.

### Expanding the product selection <br>It's best to opt for products in the following direction:
- Match these categories: **Storage and containers, kitchen and dining, home and living**. Also **avoid Jewlerry.**
- Price of 7-12, though as long as it's not below 1, and the price is just. it is still ok.
- Estimate that it will sell at least a 1000 units a year.

#### Expanding conclusion is based on the following:
- Category wise:
    - Categoies that have great revenue per porduct:
        - **Storage and containers**. - This is the best category because it's small in product selection but has the highest revenue per product (average of 6,246 - double or triple than any other category!).
        - **kitchen and dining** (average of 3,406).
        - **home and living** (average of 2,908).
    - **Jewllery** was rediculously low on revenue per product - only 185 per product.
- Prices:
    - Good price range:
        - Products in the high price range (above 8) generate most revenue.
        - But also the price range of 2-5 was very common in a large list of 15% of the products with the highest revenue.
    - Price of 1 and below had very litle revenue comparing to the higher price range.
- Quantity:
    - Too small quantity may suggest difficulties to sell.
    - Products that sold in large quantities often had little revenue. A large quantity usually suggest low price, and who knows what's left after reducing the cost and shipping of items from the revenue?


### Products to exclude from the shop <br>It is recommended to exclude all these items that sold a revenue of less than 50
A list was created for these items and was named `items_to_remove`.<br>

This conclusion is based on the following:
- There are 331 products with less than 9 units sold each, from mixed categories.
    - These product prices range fro 0.42 to 29.95, while most product prices are between 1 and 3.
- As many as 545 products had a total revenue of less than 50.
    - First place in hall of shame is "Cushion pads" with total of 3 sold units for 0.001 each.




## [click here to open the full notebook using nbviewer (recommended)](https://nbviewer.org/github/cheziman/My_Projects/blob/main/Product_Range_Analysis/product_range_CheziM_p100.ipynb)
