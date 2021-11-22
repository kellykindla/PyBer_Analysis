# PyBer_Analysis Module5

## Project Overview
### Purpose of Module 5 
For this module, we expanded our knowledge of Python and the Pandas and NumPy libraries through the practice of summary statistics and by being introduced to the Matplotlib library to visualize our data. We were guided through the creation of quality visualizations that display trends by MATLAB’s plotting syntax and by using an object- oriented interface approach. After completing this module, I can confidently inspect multiple data sets and merge them in order to create DataFrames and Series on which to perform mathematical calculations and visualize the findings. 

### Overview of Assignment 
For this assignment, we were presented with data from a ride-share company and were challenged to perform an exploratory analysis on that data and visualize our findings through Matplotlib charts and a Ride-share Summary DataFrame. Our goal was to display information in such a way that gives insight on the accessibility and affordability of rides in accordance to the type of city one lives in— in essence, for this challenge, to displaying the total weekly fares for each city type (Urban, Suburban, and Rural). 

### Resources
The data for Module 4 was from the **_city_data.csv_** and **_ride_data.csv_** files. 
#### Software used:
	- Python 3.7.10
	- Anoconda 4.10.1
	- Jupyter Notebook 6.3.0
	- Matplotlib 3.3.4


## PyBer Analysis 
### Flow of Script
After importing our necessary dependencies and loading and reading our .csv files, we merged our two datasets on the city column, given that there were no null values in each data set. From the merged DataFrame, we have data regarding the city each ride took place along with the corresponding date, fare, ride ID, the driver count per city, and what type that city was— Urban, Suburban, or Rural. We then used the groupby function on the “type” column of the merged data frame to get the total number of rides, total number of drivers, and sum of fares for each city type. From those values we performed a simple mathematical calculation to find the average of each category for each city type. Then we collected and formatted the values to display them in the summary DataFrame below. 

<img width="554" alt="PyBerSummary" src="https://user-images.githubusercontent.com/92558842/142951114-116b0ddd-671c-4aa1-bfc4-bd35db7a1548.png">

We then switched our focus to the total fares for each week by the city type. To display this information, we used the groupby function to create a new DataFrame containing the sum of the fares for each date in accordance with the city type. We then used the pivot function to create a pivot table with the date of the ride as the index, the type of city as the column, and the fare as the associated value. A sample of the pivot table is shown below. 

<img width="273" alt="pivottable" src="https://user-images.githubusercontent.com/92558842/142951133-1d47118b-1e06-4864-9d26-ccaa7171395b.png">

The NaN values of this DataFrame represent the absence of a ride in that city type on that date-time. We then utilized this pivot table and the loc method to create a new DataFrame containing data from 2019-01-01 to 2019-04-28. We then converted the date index to a “datetime” data type so that the data could be displayed by weeks through the use of the resample function in a new DataFrame, displayed below. 

<img width="247" alt="ResampledDF" src="https://user-images.githubusercontent.com/92558842/142951158-06f10df7-cc85-46cb-95ce-ec32ca50ae1c.png">

Lastly, the total fare by city type data was displayed in the line graph below, using the object-oriented interface method, where each week is represented by a peak or dip in the line. 

<img width="907" alt="PyBer_LineGraph" src="https://user-images.githubusercontent.com/92558842/142951173-ad5c0f80-5f3e-491d-99d0-6f9d7faf9b3b.png">


### Results
Based on the PyBer data provided, we can assume that there is a disparity in fares by the city type. The line chart below shows a detailed summary of this disparity. For instance, we can see that the total fare for an urban city for a particular week is much greater than that of a rural city. This is due to there being a greater amount of rides in urban cities than rural and suburban cities, thus a greater total fare for a given week. From the PyBer Summary DataFrame displayed above, we find that specifically urban cities have 13 times more total rides than rural cities and the collected total fare for urban cities is about 9 times more than that of rural cities. Meanwhile, we see from the line chart and from the Summary DataFrame that the results from suburban cities hover in the middle of urban and rural results where the total rides and total fare prices are about 2 to 3 times less than urban cities and about 4 to 5 times greater than rural cities. We can also see from the summary DataFrame that the total driver count of an urban city is 19 times greater than that of rural cities and 5 times greater than rural cities. Based on the amount of drivers in each city, we see a inverse realtionship between average fare per driver and the total driver count, where in the rural city with far less drivers, the average fare per driver is much greater than that of an urban and suburban city with more total drivers. Despite there being a vast difference in total ride and total driver count for each city, the PyBer summary DataFrame shows that there is only about a $10 difference in the average fare price for a ride in an urban city versus a rural city. 
From the scatter plot shown below (completed in the module) we can see another disparity between fares of different city types. The scatterplot displays the average fare price and the total number of rides for each city type. We can gather that there are far more rides at lower average prices in urban cities while rural cities have fewer rides, of which, the average price can be nearly double that of a ride in an urban city. We see once again, that the data from a suburban city hovers in the middle of rural and urban cities. From the scatterplot we can also see by the size of the dot, that drivers in urban and suburban cities tend to service more rides than those drivers working in the rural cities.  

![Fig1](https://user-images.githubusercontent.com/92558842/142951244-fa4a9730-302c-474f-9b0b-018c241acb6a.png)
![PyBer_fare_summary](https://user-images.githubusercontent.com/92558842/142951257-536087da-5799-4b66-b960-2fde73788a37.png)

### Summary
Based on the results of the analysis, and given that the population of a rural city is less than that of an urban city, we can assume that there is a negative correlation between fare price and city population and a positive correlation between total number of rides, total fare price for a given week,  and city population. Meaning, a more populated, or urban city, will tend to have more rides, thus a larger sum of fares for a week at a lower cost while a rural city, with a lesser population, will have fewer rides at a higher cost and a suburban city with a population size between the two, will have results in the middle. However, we can not confuse correlation with causation as there may be external factors effecting the disparity of total rides and fares.  For instance, is the average fare price so high in rural cities because there are fewer rides or are there fewer rides because the fare prices are so high? 
From a business standpoint, I would recommend the following: 
  1. Utilize the revenue from the total fares of urban cities to equalize the average fare price across cities and repeat this analysis to see if there is an increase in rides in rural cities with a decrease in the cost of the ride. 
  2.  Focus the drivers and resources to where the revenue is coming in— which is urban and suburban cities. By creating readily accessible rides, the total number of rides will increase and thus the total income. 
  3. Try to increase fare prices in urban cities in aims to increase profit and see if the total number of rides sustains. 
  4. Consider phasing out the rural division and evaluate the impact on the company as rides may not be practical in rural cities and the drivers and the company can potentially make higher profit in more populated cities. 
