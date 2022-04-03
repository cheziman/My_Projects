
# [Market Analysis — Cafe Botz](https://nbviewer.org/github/cheziman/My_Projects/blob/c77d0153e71b7e25c903ff0d3d2fcd596b8c593b/Cafe_Botz_Market_Analysis/Cafe_Botz_Market_Analysis.ipynb)

[click here to open the notebook using nbviewer (recommended)](https://nbviewer.org/github/cheziman/My_Projects/blob/c77d0153e71b7e25c903ff0d3d2fcd596b8c593b/Cafe_Botz_Market_Analysis/Cafe_Botz_Market_Analysis.ipynb)

# Description
With the intention to open a small robot-run cafe in Los Angeles and attracting investors who are interested. It is necessary to conduct a research of the restaurant market of LA.

### Project goal
To study the market and determine if the robot-run cafe will have a long lasting success.

# Favorite graph taken from the project
This graph shows the amount of restaurant seats in each of the busiest streets.
- The color represents different restaurant types.
- It's interesting that there are no restaurants with 50-60 seats.


a short explanation and a couple more graphs can be seen in the [images folder](https://github.com/cheziman/My_Projects/tree/main/Cafe_Botz_Market_Analysis/images).

![Seats_dist_top5_streets.JPG](images/Seats_dist_top5_streets.JPG)

## Short summary
The data needed some preprocessing and serious cleaning (big city streets are always dirty).
- Street names were "fixed" using regex to clean out everything that was not raw street name and saving the result in a new column.
- Adress number digits were also extracted into a new column.
- Upper case: values with upper case letters were lowered.
- Missing values were not much of a problem: only 3 rows with missing values in chain column. This was easily restored.
- Duplicated names: there were 102 duplicated restaurant names, these were confirmed to have the same address and removed from the data.
    - There were more "hidden" duplicates that had to be ignored since it would be too tedious and long to process them right, such as establishments with slightly different names at the same address.
#### That issue with street names was really enjoyable to work on;
A street can be named with various typos or different variations (such as AVE. , north, N etc.)
Overcoming this was a very enjoyable experience for me (although only once it was completed!), and was done by manually by using regex string replacement, and extracting the street number.
```
example:
rest['street'].replace({'ave of stars':'avenue of the stars','avenue of the stars ':'avenue of the stars'})
rest['address'].str.extract(r'([1-9]+[0-9]*)')
```

# Analysis conclusions and recommendations:
Let us refer to our future cafe as **"Cafe Botz"**

- The majority (75%) of establishments type is a restaurant, but this resemnles a very large definition of many sub types like pizza, grill, etc. Fast food takes 11% of the types share, and cafe 4.5% slmost similar to the other types.<br>
    - **We should open Cafe Botz in a fast food type format.**
    
- 70% of the establishments do not belong to a chain. and 30% do belong to a chain, a chain of course will be more profitable for us as a company, but an individual business is easier to manage.
- There are slightly more chain businesses in the cafe and fast food type of restaurants (about 40%/60%).
    - **We should start Cafe Botz as an independent cafe, keeping in mind that when it is well established, we will create a chain of Cafe Botz, maybe even outside of LA!.**
- Only a few establishments have more than 60 seats, (and non has 50-60), But it seems that vast majority of establishments host up to 50 seats. The more seats the more space you need, and if most seats are occupied it's most profitable.
- Averagely, cafes have 29 seats, and fast food has 32.
    - **Cafe Botz should best aim to have no more than 30 seats. Even if all seats are constantly occupied we can expand when we are ready.**
- The three most business crowded streets are:
    - Willshire with 380 establishments.
    - West Sunset street with 367.
    - West Pico street with 342 establishments.
    - Any other street has below 269 establishments. (out of 50,000 streets in LA, only 243 streets have at least one restaurant.)
    - **Cafe Botz should be safe to open in either Willshire, west sunset, or west pico boulevards.***
