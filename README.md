# Final Project

Team 5: Thomas Shane, Paola Escamilla, Takuma Koide, Habtamu Tikuye, Mair Manson, Derrick Amegashie

# FINAL PROJECT
## BIKESHARING SERVICES
An Analysis of Public Bike Sharing Services in Washington DC to uncover growing membership trends for potential business expansion
## Content

## REASONS FOR SELECTING TOPIC
We want to offer a deeper analysis to investors and the community on the growing membership trends of Public Bike Sharing Services in Washington DC in order to motivate investors to expand the availability of bike stations 
### Selected Topic
An analysis of Capital Bike Share service in Washington D.C.

{Mair will insert additional content}
### Reasons for Topic Selection
The bike sharing service has become increasingly popular in the main cities of the U.S. The possibility of mobilizing without schedule and traffic constraints appeals to the general public. This service also offers different payment tiers that adjust conveniently to the riders’ income. 

## VARIABLES TO CONSIDER
- Location of Bike Station (Latitude, Longitude, and Zip code)
- User types: Member and Casual
- Bike routes: Popular and Unpopular
- User number: Weekday and Weekend
- Time of day of the ride
The innovation focus that the service brings to the way we understand and see transportation became of interest to the team members. By engaging in conversations between ourselves we came to creative ideas, possibilities and hypotheses that caught our complete attention. We discussed income, gender, age and security however, as our analysis developed we uncovered that the riders of the bike sharing service, and the service as such, follows a strictly predictive behavior.

## DESCRIPTION OF THE SOURCE DATA
For our analysis, we are using secondary data which has already been collected by the capital bike share website (https://www.capitalbikeshare.com/system-data). The data was stored in CSV format and we were able to find data from 2010 to 2021. 
All the hypotheses that we came to, such as: (1) Is the service, through its cost, excluding low income riders from usage? (2) Is there a gender bias in the service? (3) Are bike stations less likely to be opened in neighbourhoods considered risky/insecure? and (4) Are the owners of the service disregarding the growth opportunities behind the “age” feature?, slowly faded from our analysis by uncovering, through the data retrieved, that the riders strongly behave as one would expect them to behave.

For the years 2010 and 2011 the daily bike ride information of the whole year was gathered in a unique CSV file. From 2012 to 2017, the daily bike ride information was gathered in quarterly arranged CSV files and from 2018 to 2021 the bike ride information was collected in monthly CSV files. Data for the month of april 2020 was not available and year 2021 cut in the month of may.
With this said, our analysis question transformed to **“Are Capital Bike Share riders rational actors?”**

In total, our final data was 66 CSV files with over 26,000,000 rows and 8 columns each.
A rational actor is that individual who uses rational calculations to make choices and achieve their own personal objectives. By using rational calculations and choices, the individual will satisfy its self-interest, receive the greatest benefit and satisfaction, given the limited option they have available.

### BikeSharing Data:
- Capital Bikshare (Washington D.C.) from 2010 - 05/2021. Retrieved from: https://s3.amazonaws.com/capitalbikeshare-data/index.html
With this introduction to the team’s context and thinking process, we present our analysis to uncover if our analysis questions is true (or not).

## QUESTIONS TO ANSWER
Q. How does time of day influences the member type of riders in Washington D.C.?
### Description of Source Data
Our work used secondary data already collected by the capital bike share service through their website: https://www.capitalbikeshare.com/system-data. 

Q. How does the weekday/weekend difference influence the membership type of riders in Washington D.C.?
The data was stored in CSV format files, from 2010 to 2021. 

Q. How does type of bike affect membership type?
For the years 2010 and 2011, the daily bike ride information was gathered in a unique CSV file. From 2012 to 2017, the daily bike ride information was gathered in quarterly arranged CSV files and, for the remaining years,  the bike ride information was collected in monthly arranged CSV files.

H0: The member type of riders is not related to the time of the day of the ride. 
It must be highlighted that some months had to be disregarded from the analysis due to a lack of data (e.g. year 2020 skipped the month of april and year 2021 ended in may).

## ETL Process
In total, our final dataset was created by taking a total of 66 CSV files with over 26,000,000 rows and 8 columns each.

### Analysis Question
As previously introduced, our analysis question is **“Are Capital Bike Share riders rational actors?”**.

To prove, or deny, our hypothesis the analysis dives into:
- Total bike rides per year
- Distribution of ‘member type’ per station
- Time of the day and day of the week of the ride
- Location of Bike stations (lat, long)

### Description of Data Exploration Phase
The data exploration phase started with a review of the websites of the known bike share services in different cities in the United States. We were able to find available data for the cities of New York, Chicago, Pittsburgh, Boston and Washington D.C. 

Even though all cities showed consistent data we decided to stay with Washington D.C. considering this is the city where all team members live and therefore, we could understand better. 

The data retrieved in the capital bike share website was consistent and showed quality.. The same data was collected throughout the years aside from 2020 and 2021 where we found a couple of new columns added. 

The size of the data collected for each year was considerably large. The amount increased our reliability to the data as we were able to draw some time series in our work.

## ETL PROCESS
The purpose of the ETL process was to create one big dataset from all the individual CSV files. 

The final dataset contained all 28M trips and was conformed by the following columns: 'Trip Number,' 'Starts station number,' 'End station number,' 'start date,' 'end date,' and 'member type'.
The final dataset contained all 28M trips and was conformed by the following columns: 'Trip Number,' 'Starts station number,' 'End station number,' 'start date', 'end date', and 'member type'.

### Table 1: all_bike_trips
1. For the first table, we created an index of the 66 csv files to allow python to call the files by each individual directory and file name. 
 @@ -51,7 +65,7 @@ The final dataset contained all 28M trips and was conformed by the following col
7. Then, both resulting CSV filees were merged (the `trips_2010to202003.csv` and `trips_202005to202105.csv`).
8. Lastly, from the merged file, unnecessary columns were dropped, NaN rows cleaned up, mixed data type columns removed and datatype converted to give us our `Table1_all_bike_trips.csv`.

## Visual representation of the output:
#### Visual representation of the output:
Table #1 all_bikes_trips

![image](https://user-images.githubusercontent.com/78698456/125867516-cb3773d8-bef6-4fa0-bc48-196176f0c837.png)
 @@ -62,7 +76,7 @@ Table #1 all_bikes_trips
3. From the `trips_202005to202105.csv` we extracted a third dataframe named: `Table3_rideable_type`


## Visual representation of the output:
#### Visual representation of the output:
Table #2 bike_number

![image](Image/2_bike_number_table.png)
 @@ -79,7 +93,7 @@ Table #3 Rideable_type
5. We used the `Table1_all_bike_trips.csv` and picked the first time and the last time that appears for each `startstationnumber`.
6. The output was a dataframe holding the columns of: `startstationnumber`, `first`, and `last`. This table was saved as a CSV file named: `Table5_station_active_dates.csv`.

## Visual representation of the output:
#### Visual representation of the output:
Table #4 Station List

![image](Image/4_station_list_table.png)
 @@ -93,15 +107,15 @@ Table #5 Station List with its active dates
2.  We used the `value_counts()` method to list how many times each station appears over the 28M trips recorded in our dataset.
3.  The output was a dataframe with `startstationnumber` and `occurence` columns which was saved as a CSV file named: `Table6_number_of_trips.csv`.

## Visual representation of the output:
#### Visual representation of the output:



### Table 7: member_trips and Table 8: casual_trips
1.  We created two separate datasets listing the trips done sorted by 'Member' and 'Casual' users separately.
2.  We used the `Table1_all_bike_trips.csv` and picked the `membertype` column to then separate them by `Member` and `Casual` separately and save them in two dataframes named: `Table7_member_trips.csv` and `Table8_casual_trips.csv` respectively.

## Visual representation of the output:
#### Visual representation of the output:



 @@ -120,10 +134,19 @@ Table #5 Station List with its active dates
9. We refered to the `Table7_member_trips.csv` and `Table8_casual_trips.csv` files to calculate the number of `Member` usages and `Casual` usages for each bike station on each day of week.
10. We utilized the calculated dataframes and had for an output a new dataframe with columns of `startsstationnumber`, `weekday`, and the `ratio` of `Member` usage. This CSV file was saved as `Table11_station_dayofweek_ratio.csv`.

## Visual representation of the output:
#### Visual representation of the output:



## DATABASE INTEGRATION

By looking into our multiple CSV files, after cleaning the same and organizing the raw data extracted from the capital bike share website, we established five tables to integratd our database: 

![Final_ERD](https://user-images.githubusercontent.com/78656720/126044898-bf43e200-e51a-45a5-83e4-865fc1d466df.png)

These five tables were loaded into a PostgerSQL database. While working on the data analysis we also extracted different tables using SQL join query. Looking at the image below we show an example of a table created by "Inner join" from our *station_list* and *station_list_active*.

![Inner_Join](https://user-images.githubusercontent.com/78656720/126045190-2021a9e1-b07f-40b8-9c1a-0a5cddf2b1ea.png)

## MACHINE LEARNING
In the machine learning part of our project, we try to predict future growth of bikesharing in DC. Using timeseries data and ARIMA model the project performs trend analysis and predict future prospect of the bike sharing.
 @@ -191,15 +214,8 @@ Part 4: Modeling/Forecasting

Part 5: Evaluate/Improve Forecasting/Predictions 

## Database Integration

By looking into our multiple CSV files, after cleaning the same and organizing the raw data extracted from the capital bike share website, we established five tables to integratd our database: 

![Final_ERD](https://user-images.githubusercontent.com/78656720/126044898-bf43e200-e51a-45a5-83e4-865fc1d466df.png)

These five tables were loaded into a PostgerSQL database. While working on the data analysis we also extracted different tables using SQL join query. Looking at the image below we show an example of a table created by "Inner join" from our *station_list* and *station_list_active*.

![Inner_Join](https://user-images.githubusercontent.com/78656720/126045190-2021a9e1-b07f-40b8-9c1a-0a5cddf2b1ea.png)
# RESULTS OF ANALYSIS

## DASHBOARD
The interactive Tableau Dashboard is available at the following link: <https://public.tableau.com/views/PublicBikeSharingProjectLoationvs_Membership/Loc_Station_ratio?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link>.
 @@ -235,3 +251,6 @@ Future visualization ideas:

1. Evaluate how number of trips changes by staion depends on Weekday or Weekend
2. Analyze how time of day may affect the overall trip occurence and the ratio of 'Member' user.


## RECOMMENDATIONS FOR FUTURE ANALYSIS
