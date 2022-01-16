# PyBer_Analysis

## Project Description

This analysis creates a summary data frame of ride sharing data by city type for PyBer to examine the metrics of disparity between Urban, Suburban, and Rural usage. The ultimate goal is to increase affordability and access across the spectrum of city types.  Specifically, we analyized ride share data for Urban, Suburban, and Rural PyBer routes and for each city type, we calculated the total rides, total drivers, total fares recieved, average fare, and average fare per driver. Finanly a line plot was created comparing total fares by week for all three city types from Jan 1, 2019 to April 28, 2019.  

## Resources

  **1. Software**
  
    - Python Pandas
    - Jupyter Notebook
    - matPlotLib

  **2. Data found in Resources folder**

    -  city_data.csv
    -  ride_data.csv

## Result Outputs

  **1. PyBer_Challenge.ipynb** - jupyter notebook file produced to import, merge, and perform calculations on city_data.csv and ride_data.csv
  **2. Analysis/PyBer_fare_summary.png** -line plot output

## Analysis Workflow

Using Pandas and matPlotlib in Jupyter Notebook the ***city_data.csv and ride_data.csv*** were imported and merged into a new pandas dataframe (pyber_data_df).  This data frame included city name, date, fare, ride_id, driver_count, and city type.  

![image](https://user-images.githubusercontent.com/91850824/149672546-9d3991f1-13ad-4c0e-81ed-4fc34d54386b.png)

Using Pandas *groupby* function, total rides, total drivers, and total fares recieved were calculated with regards to city type and series were created for each with city type as the index.  Average fare and average fare per driver were then calculated from groupby output and series for each were formed.  The series were then combined into a new dataframe (pyber_summary_df).

![image](https://user-images.githubusercontent.com/91850824/149672633-30dec300-c31d-4bc4-8c1d-a237d5215b2a.png)

The original pyber_data_df was then reused.  A new dataframe was made by groupby method using type and data as indexes.  The indexes then summed the fare's by type and date. Using the pivot plot function, the table was reorderd after resting the index, and the date was moved to the sole index.  Using the loc function, the date was narrowed to the specified dates: Jan  1, 2019 to April 28, 2019.  The data was then resummed by week using the resample function and a line chart for the dataframe was created using the df.plot() function in matPlotlib.

![PyBer_fare_summary](https://user-images.githubusercontent.com/91850824/149672869-bf6bdd43-df2c-46e8-9ead-aefb42e655ee.png)

## Analysis Results

The following analysis will refer to the pyber_summary_df that can be accessed from PyBer_Challenge.ipynb.

![image](https://user-images.githubusercontent.com/91850824/149672966-53af4f09-831d-4708-b858-761ea15db521.png)

  **1. Comparison of Total Rides.**
    
As intuitively expected the ***Rural*** cities (assumed to be due to lower populations) have the lowest number of ride counts at **125**.  The ***Rural*** count is 5 times smaller than the ***Suburban*** (**625 rides**) and 13 times less than ***Urban*** (**1,625 rides**)

![Fig6](https://user-images.githubusercontent.com/91850824/149674291-dacaa843-447a-4efb-9183-cd89fe1035c6.png)


  **2. Comparison of Total Drivers**
  
  Again, the ***Rural*** cities (assumed to be due to lower populations) have the lowest number of drivers at **78**.The ***Rural*** count is 6.3 times smaller than the ***Suburban*** (**490 drivers**) and 13 times less than ***Urban*** (**2,405 drivers**).
  
  ![Fig7](https://user-images.githubusercontent.com/91850824/149674299-e2124344-ffcf-47f6-991a-19a53123d6ef.png)

    
   **3. Comparison of Total Fares**
  
Again, the ***Rural*** cities (assumed to be due to lower populations) have the lowest total fares at **$4327.93**.The ***Rural*** fare total is 4.47 times smaller than the ***Suburban*** (**$19,356.33**) and 13 times less than ***Urban*** (**39,854.38 drivers**).

  ![Fig5](https://user-images.githubusercontent.com/91850824/149674316-e9e378a8-37d2-4e8f-8fc7-e080c7c22257.png)

   **4. Comparison of Average Fare per Ride and Average Fare per Driver**
   
The highest fare per ride and average fare per driver flips the trend seen in the last 3 comparisons.  ***Rural*** city types have the highest in each category (**Average Fares per Ride = $34.62; Average Fare per Driver = $55.49**) follwed by ***Suburban*** (**Average Fares per Ride = $30.97; Average Fare per Driver = $39.50**) and then ***Urban*** (**Average Fares per Ride = $24.53; Average Fare per Driver = $16.57**).  ***Rural*** drivers can expect fares 1.4 times larger than ***Suburban*** and 3.3 times larger than ***Urban***.  Breaking the data down further; due to the low number of rural drivers, ***Rural*** drivers get 1.6 rides on average compared to ***Suburban*** 1.3 and ***Urban*** 0.675.  Based on these averages, the ***Rural Driver*** made $88.93 for the period analyzed versus ***Suburban*** ($50.38) and ***Urban*** ($11.20).  

![Fig3](https://user-images.githubusercontent.com/91850824/149674340-0606928e-33ad-43b2-afcb-585f65ac0b5d.png)


  **5.  Comparison of Total Fares by Week Jan 1 to April 28, 2019**
  
The best way to view this data is with the attached PyBer_fare_suammry.png
  
  ![PyBer_fare_summary](https://user-images.githubusercontent.com/91850824/149674115-e2860928-8a12-4530-a8ef-59ee4da81369.png)

As can be seen by the chart, with the exception of a few peaks, the total fares between each city types seems to be consistant.   The vertical distances between the lines are fairly consistant indicating that the demand is likely consistent for each area.

## Summary and Recomendations

On the whole, the **Urban** cities are the largest source of fares, drivers, and rides.  However, the average fare per ride and average fare per driver are inversely proportionate.  We reccomend the following to address teh disparity between city types

![Fig1](https://user-images.githubusercontent.com/91850824/149675250-4e4cc7a8-4c75-48bc-a920-fe60761964ad.png)


1.  ***Rural Affordibility***

Rural drivers participating in PyBer have fares 3.3 times larger than ***Urban*** drivers and get an average 1.6 rides per driver versus ***Urban*** 0.675.  This indicates the the potential for new driver's in Rural areas.  We'd reccomend advertising the potential for rural drivers with the given data to encourage more drivers to apply and increasing access to this service area.  More data should be collected particularly on ride length and duration to assess why **Rural Areas** perform better that ***Suburban and Urban*** cities.  

To increase the attractiveness for rural riders, rates in "Rural Areas" could be decreased.

2.  ***Urban Driver Fares***

There does appear to be great participation in ***Urban Cities***; however, in comparison to ***Suburban and Rural***, ***Urban Drivers*** make $16.57 per ride versus $39.50 and $55.49 respctively.  It would appear that given the amount of rides taken in ***Urban*** areas that the driver market is over saturated.  It may be beneficial to limit the amount of drivers participating at a certain time to increase the rides to participating drivers and hence allowing for more potential for each driver to profit.  The downside potential is that you may decrease availabillity; however, if driver's feel like they have limitted abillity to profit PyBer, they may lose interest.  

Another option could be to raise rates in ***Urban Cities*** to support urban drivers.

3.  ***Analyize Peak demand and notify drivers of the potential***

Although the overall trend is consistent, there are times where all 3 areas see increase in fares (Last week of February).  Using fare data and further study as to whether the increase is due to ride count or ride length; PyBer could add notification functionality to its app to give drivers indications as to whether their area is in a peak demand time, or is about to be in a peak demand time.  This allows drivers to set their schedules to handle more rides.  Examples are for sporting events, fairs, other community activities.  
    

