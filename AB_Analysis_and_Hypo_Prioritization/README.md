# [A/B Analysis — Hypothesis testing and prioritization](https://nbviewer.org/github/cheziman/My_Projects/blob/d4b8fb10645e030a4cf8f6e69ec4853a1c259b6e/AB_Analysis_and_Hypo_Prioritization/AB_Analysis_and_Hypo_Prioritization.ipynb)
[click here to open the notebook using nbviewer (recommended)](https://nbviewer.org/github/cheziman/My_Projects/blob/d4b8fb10645e030a4cf8f6e69ec4853a1c259b6e/AB_Analysis_and_Hypo_Prioritization/AB_Analysis_and_Hypo_Prioritization.ipynb)


## Introduction
A marketing team of a large online store has compiled a list of hypotheses that may help boost revenue.

## Project goal
1. Prioritize the list of hypotheses
2. Test the most urgent hypothesis
3. Analyze results

## Methods used in this project
- Prioritization using and comparing the ICE / RICE scoring system
- A/B testing evaluation and analysis

## Favorite graph from this project
This graph is a comparison of RICE and ICE scores for different hypotheses (represented by numbers) 
- For an easy comparison, the RICE score is divided by 10 to match the scale of the ICE score (ICE = Impact * Confidence / Effort - MAX score of 100, and RICE = Reach * Impact * Confidence / Effort - MAX score of 1000)


a short explanation and a couple more graphs can be seen in the [images folder](https://github.com/cheziman/My_Projects/tree/main/User_behaviour_AAB_test/images).

![Scaled_R-ICE_comparison.JPG](images/Scaled_R-ICE_comparison.JPG)

## Summary and conclusions
- As we read and prepared the data we found and removed the following anomallies:
    - 58 users who has made transactions both in group A and group B.
    - Outliers in revenue size: as much as 20,000!
    - 0.72% of the users who made 3 purchases.
    
- Drawing various graphs we found that:
    - 96% of users made only one purchase. 2.98% made 2 purchases, and 0.72% made 3 purchases. No one made 4 or more purchases.<br>
        **It is recommended to encourage custumers to place more orders, maybe a with discount or points system.**<br>
        **It is also recommened to try and raise purchase size, maybe with a small percentage off the second item or recommending items similar to what costumers added to cart**
    - In August-19, there was a huge purchase of 20,000. **It's worth checking it as the median purchase size is 50**.

- Testing significant difference we found that:
    - Conversion rate was in favor of group B with 18.19%.
    - The average order size is similar between the groups, group B is slightly lower with -4.74%. Perhaps it's just bad luck as it is hard to imagine adding subscription form to main pages would reduce order size.
