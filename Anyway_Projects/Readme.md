# Tel Aviv accidents analysis 
### Categorization, And creating tables of accidents by street, and by intersection.
### This is the first project done for Anyway, using data from Halamas on accidents in tel aviv, from 2018 to 2023 (july).
The project is done before the municipal elections, in order to present the candidates with interesting accident statistics, and had 4 main goals:
1. To create a first prototype code to be used later on data of different cities.
2. Categorizing the involved categories into a cleaner format, such as joining 100cc, 250cc, and 500cc motorcycles into one category.
3. Creating a table of accidents bt street (all involved injured bodies per street).
4. Creating a table of accidents by intersections of two streets (all involved injured bodies per intersection).


As mentioned, the data was taken from the "Data for change" redash - Halamas data
using the following code:

```
SELECT 

-- involved data
injury_severity_hebrew,
involved_type_hebrew,
age_group_hebrew,
sex_hebrew,
injured_type_hebrew,
involve_vehicle_type_hebrew,
vehicle_vehicle_type_hebrew,
injured_position_hebrew,

-- modified fields on top
 CASE
     WHEN injured_type_hebrew = 'הולך רגל' THEN 'הולך רגל' 
     ELSE involve_vehicle_type_hebrew
 END injured_type_modified_by_anyway,
 
 -- location data
location_accuracy_hebrew,
road_type_hebrew,
street1_hebrew,
street2_hebrew,

-- date and time
accident_day,
accident_month,
accident_year,
accident_hour_raw_hebrew,
day_in_week_hebrew,
                                                                      
--accident_data
provider_and_id,
accident_severity_hebrew,
 accident_type_hebrew
FROM involved_markers_hebrew
WHERE accident_year >= 2018
       AND accident_yishuv_symbol = 5000
  AND injury_severity > 0
ORDER BY accident_year DESC, accident_month_hebrew DESC, accident_day DESC
```
