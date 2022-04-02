# [Forecasts and predictions project — Model Fitness Gym](https://nbviewer.org/github/cheziman/My_Projects/blob/main/Forecasts_and_predictions/Forecast_and_prediction_Model_Fitness_proj.ipynb)

[click here to open the notebook using nbviewer (recommended)](https://nbviewer.org/github/cheziman/My_Projects/blob/main/Forecasts_and_predictions/Forecast_and_prediction_Model_Fitness_proj.ipynb)

# Introduction
In this project machine learning algorithm is used to predict churn rate for the gym's customers.
both linear regression and random forest are employed to determine which is the best algorithm to do the job.

# Project Summary
This project is pretty straight forward - the data is already prepared to be used to predict churn rate, not much preprocessning needed.
- 2 models were emplyed — **Linear Regression** and **Random Forest**, LR proved to be the better option, and in both LR and RF feature importance was more or less the same order.
- **Clusters** were created using **Kmeans**, a **dendrogram** was created to help deciding how many clusters.
- **Clusters** were analysed using the following methods:
  - Feature means
  - Feature distribution
  - Calculating churn rate

# Favorite graph
![heatmap_cluster_feat_mean_normalized.JPG](heatmap_cluster_feat_mean_normalized.JPG)


# Conclusions

## EDA:
- Most of the users did not churn!
- The data was ready to be analysed, no fixes or preprocessing were needed, with a minor exception of turning one of the features from float to int data type.
- Most costumers have a month left in their contract, many of them also signed up for a monnth long plan.

## Features:

- These features seem to have a significant effect on whether users will churn:
    - **Partner:** It seems that it's a good idea to partner with companies, as the subscribers tend to churn less often. perhaps this is due to the discount they get. in this case special discount should be considered for other subscribers as well.
    - **Promo_friends**: Subscribers who are under the "bring a friend" program also tend to churn less often. This is probably because: **A.** Discount. **B.** A friend serves as a motivator to keep exercising.
    - **Group_visits**, **Avg_class_frequency_total**, and **Avg_class_frequency_current_month**: Subscribers who participate in group sessions and classes are less likely to churn, similarly to the promo friend feature, socializing and having company in the gym must be motivating to stay.
    - **Avg_additional_charges_total**: Big spenders who used additional services are likely to stay. Maybe if the service is one that is being used slowly over time (such as a 10 time pool entry, 30 protein shakes, etc.), then no one who purchased it will churn as long as it's active. Another reason could be great services!.
    - **Age**: Customers who are around 27 year old churned the most. The older the age the less the churn rate. Probably because in later life people are more stabilized and serious in their choices, and of course more financially established.
    
- **Contact period** and **Lifetime** are especially important, those who have long contracts (6 months and above), and those who already have gone through a few months of subscription are more likely to stay. It makes great sense, to wait until subscription ends, in order to end it.


- These features seem to have little or no effect on whether users will churn:<br>
    **Gender, Near_Location**, and **Phone**.
    
## Observations:
- Customers are less likely to churn if they:
    - Are a part of a partner program.
    - Signed up with the "bring a friend program".
    - Take part in group sessions.
    - Spent money on additional services.
    - Take classes frequently.
    - Have contract for longer than 2 months.
    - Are already customers for a couple of months (2 is good, 7 and up is great)
    - Older.
    
# Recommendations:
- As many costumers churn when their subscription ends, it is a good strategy to try and renew their subscription as early as possible, and before their subscription has less than two months left:
    - It is a good idea to consider to cancel the month-long plan.
    - Maybe offer a special discount or a free month to long subscribers. We know customers love discounts be looking at the churn rate of the promo friends and the partner features (those who use these subcscriptions churn less).
- Keep additional services doing what they do, it seems to have a good effect on churn.
- Try marketing the gym to age 30 and above a little more.
- Phone might not affect the churn rate, but it is very important to have a way to reach your costumers!. Consider making it mandatory to leave a phone number, or at least make a great effort in getting contact info.
    
- Join the gym, it's good for you!
