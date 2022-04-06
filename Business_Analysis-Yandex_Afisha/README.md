# [Business Analysis — Yandex.Afisha](https://nbviewer.org/github/cheziman/My_Projects/blob/main/Business_Analysis-Yandex_Afisha/Business_analysis-Yandex_Afisha.ipynb)

[click here to open the notebook using nbviewer (recommended)](https://nbviewer.org/github/cheziman/My_Projects/blob/main/Business_Analysis-Yandex_Afisha/Business_analysis-Yandex_Afisha.ipynb)




### Introduction
Yandex is a big search engine. Afisha is a russian website about movies and television programs.

[Yandex.Afisha (link is in russian)](https://afisha.yandex.ru/moscow) — the two teamed up in 2014 to present Russians with the option to search showtimes and pre-purchase tickets online. from home or on android and ios supported phones.

### Project goal
The goal is to help optimize marketing expenses of different ad source campaigns, and of course analysing user behaviour.
### Methods
- **Cohort analysis** - users are split into monthly cohorts
- **Metrics** — LTV, CAC, ROI/ROMI D/W/MAU, Retention rate, and more
- **Graphs** — matplotlib and seaborn, including a monthly cohort ROI heatmap and others

This project may make you shout a big "WAU"

---

## Favorite graph taken from the project
This is a heatmap showing the retention rate of monthly cohorts.

a short explanation and a couple more graphs can be seen in the [images folder](https://github.com/cheziman/My_Projects/tree/main/Business_Analysis-Yandex_Afisha/images).

![cohort_reten_rate.JPG](images/cohort_reten_rate.JPG)

---

## Summary, conclusions and recommendations
#### After reading and preprocessing the 3 files(visits, orders, and costs), there were not find too many anomallies was a relief, some points to remember:
- The revenue column in the orders table, had 0 values. maybe free goods, compensation, prepaid, or data error. They were regarded as valid values.
- There are Very high values in the orders table for revenue. maybe a group purchase,  a company, maybe an error, maybe even a person/bot trying to buy and resell?, either way it should be examined.
- Ad source 5 from the costs table had an extra day of cost. It is just a little bit suspicious. The same users entered the service a handful of times and did not purchase anything.
- In the vists table, for rows: 4181, and 177972, the start_ts timestamp is later than the end_ts timestamp.
- In march 31, there was only 1 user active, is this a bug? or just a very bad day?
- The start_ts is rounded by minutes, and the end ts is mostly too, but there are some end_ts values that are rounded to 19 seconds (HH:MM:19). to see it, use:  visits['end_ts'].dt.second.unique()  .

### Miscelleneous points:
- The strongest months for are October to March. With more visits and orders than the rest of the year. 
- There was a huge spike in november 24 with 3319 sessions that day, it could be a good marketing move, something that happened that day or due to happen, or maybe just an error. 
- The June and September user cohorts were very successful in all terms. For example the September cohort reached top of 62.5 average revenue at December. perhaps it's because of seasonal events? perhaps these cohorts have some exceptional users?<br>
    The June cohort has the biggest jumps of purchase average, that keeps scaling high every month.

### User behaviour:
- Users times:
    - Most sessions last a minute.
    - Some sessions last from to 10 to 13 minutes (this raises the average session time to 10 minutes), maybe these are the sessions where orders were made?.
        It's a good idea to consider having a timer to end the session after inactivity.
- 73% of users are visiting from a desktop pc. it could be a more comfortable interface.
- Daily average of users who access the service is 908
- Most users use the service only once in a day with 1.08 average daily sessions per user.
- Only 16% of users have actually purchased something.
- 50% of buyers have made their first order on the same day they registered. and most of the other 50% took no longer than 2 months. few users took a year to make their first order.
- 87% of the users make only 1 purchase. and a few made as many as 250 purchases!.
- Retention rate is not great, but it is still positive. it means a portion of the initial users do come back even after a year.
- Within a year, returning purchases can make 3 times the initial purchase.
#### Recommendations:
1. **As only few users make a first purchase, and out of them only a few make repeat purchases, it is a good idea to encourage users to make a first purchase.**
2. **Also Repeat purchases should be encouraged.**<br>
     **maybe a benefit membership club? discount or special seats reserved?. make it something exciting!**
3. **With 73% of sessions coming from desktop. Maybe it's good to focus on desktop users. But also the mobile interface or usage must be checked or improved, maybe it's inconvinient.**
4. **Perhaps it's good to focus on desktop. And just to be sure, check how good is the touch interface.**
    
### Sources of advertising:
- Overall, ad costs reach 329,131.
- In terms of ROMI, all sources are positive.
- Source 3:
    - Has total cost of 141,322. This is 43% of the sources total cost.
    - Has the highest CAC with average of 13.8, and reached 18 in August with source 2 right behind it.
    - Has 10,473 buyers in total, ad source 4 for example has almost the same amount of buyers(10,295) for half the CAC (6.4 in total, and 8.5 in Aug).
    - Has a VERY low ROMI of 0.38
- Source 1: Has ROMI of 1.4, a CAC of 7.2 and total cost of 20,000.
#### Recommendations:
1. **It seems right to invest more on source 1.**
2. **It also seems right to cut on source 3 as it is too expensive and not bringing as much as other sources.**

