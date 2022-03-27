# [A-B_Testing Analysys — Online_Shop](https://nbviewer.org/github/cheziman/Product_range_analysis/blob/main/product_range_CheziM_p100.ipynb)
[click here to open the notebook using nbviewer (recommended)](https://nbviewer.org/github/cheziman/Data_Analysis_projects/blob/main/AB_Testing_analysis/Notebook/CheziM_P100_AB_Testing.ipynb)
# Description:

This project is continuing and exmanining the work of a previous analyst who has launched an A/B test of a new recommendation system for an international online store. But then one clear day - in the middle of everything, he decided to quit and start a watermelon farm in brazil (!). 
They left only the technical specifications and the test results

## Data structure
The data consists of four csv files:
1. **`ab_project_marketing_events.csv`** — the calendar of marketing events for 2020
- Columns:
  - **`name`** — the name of the marketing event. | **`regions`** — regions where the ad campaign will be held.
  - **`start_dt`** — campaign start date. | **`finish_dt`** — campaign end date.

2. `**final_ab_new_users_upd.csv**` — all users who signed up in the online store from December 7 to 21, 2020
- Columns:
  - **`user_id`** | **`first_date`** — sign-up date. | **`region`** | **`device`** — device used to sign up.

3. **`final_ab_events_us.csv`** — all events of the new users within the period from December 7, 2020 through January 1, 2021
- Columns:
  - **`user_id`** | **`event_dt`** — event date and time | **`event_name`** — event type name.
  - **`details`** — additional data on the event (for instance, the order total in USD for purchase events).

4. **`final_ab_participants_upd.csv`** — table containing test participants
- Columns:
  - **`user_id`** | **`ab_test`** — test name | **`group`** — the test group the user belonged to.

# Project summary and conclusions:

## **Data description and processing**
- The data was a big soup of 4 different tables containing 2 different tests.
- It was cleaned of 547 users who were assigned to more than one group (A + A users were spared- they have not seen changes either way).
- Then a new table was merged from the data to form a table only with the users and the information we need for the recommendation system test.
- Since the test is intended to be tested on EU users, 194 more users were removed from the data since they were not from EU.
- Then the region column was removed since all users were of the same value - EU.
- Lastly, on Dec30, only one user has logged in twice. his 2 logs were removed to get a cleaner daily analysis.
- This left us with 2934 users in total, group A with 2279, and group B with 655 users.
    - In expectation, the test needed 6000 users.

## **User recruitment**
- On the first day of recruitment (Dec-07), group B had 20% users sign ups (group A had 5%).
- Group A had 15% and 14% signups on Dec21st, and Dec14th.
- The ratio of daily signups between the groups is very different. Which may distort the user behaviour analysis, daily recruiting to the groups should be similar in ratio if not in quantities to ensure they are exposed equally to different factors during the test. In our case it wasn't so.
- Most of the users signed up on the second week of the recruitment period.
- There are very few users in group B to test upon - especially at the last couple of days.

## **User activity and behaviour**
- In the first week of the test, the traffic was low, 122 and 119 users for group A and B, it was gradually growing until Dec21st.
- Dec 21st was the last day of recruiting users. This day also had the highest amount of traffic: in group A 747 users, and in B 141.
- After Dec21st, the traffic was gradually falling again: on Dec29, group B had 26 users actvie and group A had 172
- Android device is used by 44% and 47% of the users of groups A and B. Iphone and PC are about half of it (20% and 26%) and Mac has the smallest share of 9%.

## **Purchasing**
- A total of 925 out of 2934 users (31.53%) made a purchase at least once.
- Overall, 2633 purchases were made by all users. 
    - In group A: 734 users made a purchase with a 32.21% purchase rate within the group.
    - In group B: 191 users made a purchase with a 29.16% purchase rate within the group.
- Almost ALL users (99.35%) who made a purchase made it on the first day.
    - And then continued purchasing for up to 18 days later.
- It is important to consider that maybe some users stopped purchasing because the test period was over.

## **Recommendation system test**
The test was planned as such: (comments bellow)
- Test name: recommender_system_test
- Groups: А (control), B (new payment funnel)
- Launch date: 2020-12-07
- The date when they stopped taking up new users: 2020-12-21
- End date: 2021-01-01
    - ***Disregarding the 2 events by 1 user on 30th, Dec29 was the last test day.***
- Audience: 15% of the new users from the EU region
- Purpose of the test: testing changes related to the introduction of an improved recommendation system
- Expected result: within 14 days of signing up, users will show better conversion into product page views (the product_page event), product cart views (product_card) and purchases (purchase). At each of the stage of the funnel product_page → product_card → purchase, there will be at least a 10% increase.
    - ***There was actually a decrease, and group B had lower conversion than A in all steps of the funnel.***
- Expected number of test participants: 6000
    - ***We didn't even reach the 3000 correctly chosen users.***

## **Statistical significance in difference between the test groups**
- A z-test was used to check whether the difference.
- With alpha level of 0.05, it was found safe to assume there is no statistical significant difference between the groups for the following events:
    - **login:** with pvalue of 0.062, a little higher than the alpha level.
    - **product cart:** with pvalue of 0.321, MUCH higher than the alpha level.
    - **purchase:** with pvalue of 0.139, much higher than the alpha level.
- For the **product page** the null hypothesis was rejected with pvalue of 0.00004. Therefore we can accept the fact that there is a statistical significant difference between the groups.
