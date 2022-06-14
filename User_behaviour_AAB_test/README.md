# [User Behaviour analysis and A/A/B testing](https://nbviewer.org/github/cheziman/My_Projects/blob/173ec1d66d3c13bf1d45a9f172db0097385b5db4/User_behaviour_AAB_test/AB_Analysis_and_Hypo_Prioritization.ipynb)
[click here to open the notebook using nbviewer (recommended)](https://nbviewer.org/github/cheziman/My_Projects/blob/173ec1d66d3c13bf1d45a9f172db0097385b5db4/User_behaviour_AAB_test/AB_Analysis_and_Hypo_Prioritization.ipynb)

## Description
This project is about running and analyzing the results of an A/A/B testing of a new font in the app of a startup company in the food product market.

## project goal :
Investigate user behavior for the company's app, and decide wether the experiment was successful


## Some of the methods used in this project are:
- Evaluating how solid the A/A/B test was done.
- Hypothesis testing.
- Event funnel anlysis.

## Favorite graph
This graph is an event funnel of how many users interacted with each of the event screens, split into the different test and control groups
- It shows the different group numbers in each screen are very similar.
- Almost 50% reached the `purchase complete` screen!
- It's both interesting and disturbing to find that there's a huge drop of users from the main screen to the other screens.

a short explanation and a couple more graphs can be seen in the [images folder](https://github.com/cheziman/My_Projects/tree/main/User_behaviour_AAB_test/images).

![Group_event_funnel.PNG](images/Group_event_funnel.PNG)





## Summary and conclusions
- The data was examined and the following problems were found and processed:
    - A period of a week prior to the experiment week with very few values, was removed.
    - 413 duplicated rows, were removed.
    - The tutorial screen event, with no significance over the experiment as it is an optional step and was barely used by anypme (a couple of users even left the app only after seeing it). and it was removed as well.
        - In total, 4,244 rows removed. This is 1.74% of the data.
        
        
- Then the data was studied and we have found:
    - The groups were examined and found to be fairly split, with between 2,483 to 2,535 users (33%) in each group.
    - The biggest loss of users happens between the Main screen to the Offers screen with -38.09% users.
    - The share of users who made the entire journey from Main screen to the Payment successful is 47.70%.

- The groups were studied and a z-test (16 of them) was carried on every group's event screen usage proportion, to find if there is a significant difference in user behaviour between the two control groups and the experimental group:
    - We have considered using a statistical correction (the Bonferroni correction), which corrects and lowers the significance level (alpha) to 0.003125. And then rerun the tests using it,<br>
        Eventually it was found to be of no use since the test results (p-values) were all above the already high significance level of 0.05)
    - **No statistically significant difference was found between any of the groups.**

##  Recommendations:
- The new fonts do not change user behaviour in term of sales.  Lets find a better way to improve the app.
- Find what's wrong with the main screen of the app and fix it;
  - It is losing almost 40% of the users. Perhaps it requires too much effort from the user, maybe it's not designed well, maybe there's some error preventing users to proceed.
