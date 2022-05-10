# Bikesharing

A data visualization project consisting of data analysis of bikesharing services in New York City so that a similar business can be setup in Des Moines, IOWA.

## Background : 

Last summer my friend Kate and I took a trip of a lifetime to New York City for 2 weeks. It was a magical trip as we explored historical landmarks like Central Park, Statue of Liberty and the Empire State Building. While going through the pictures, I realized that one of the major reasons for us having a great experience throughout our trip was 'citibike'. We had biked everywhere that allowed us to commute all over the city and interact with the local people who were using bikes for their local commute. A gem of an idea emerges out of our realization, making us think if we can start a similar bike sharing business in our hometown of Des Moines, Iowa. We start brainstorming and a few weeks later we come across an angel investor that might be interested in investing by providing seed funding in our business idea. As exciting as it can be, but we need to think realistically since the mechanics of the service in NYC can be different from how it can work in our hometown. We take the first step of figuring out how the setup works in NYC. From there I am going to create the business proposal as to how it might work in Des Moines. Kate will take the proposal forward. I will be using data analytic skills to figure out how this idea can be implemented in Des Moines. 


![citibike](https://user-images.githubusercontent.com/23488019/152426144-a628e789-1e54-4e98-89eb-34dcaff1a51e.PNG)


## What I will create :

This project consists of two technical analysis deliverables and a written report to present the results. It has the following components:

- Deliverable 1: Change Trip Duration to a Datetime Format
- Deliverable 2: Create Visualizations for the Trip Analysis
- Deliverable 3: Create a Story and Report for the Final Presentation

## Tools Used :

1. Tableau - Tableau is an excellent tool for data visualization. It has a very specific purpose: to provide data visualization that is easy to use and understand. Also, while other data visualization tools may require you to write code, with Tableau you don't have to write much, if any, code, which is just one of the reasons it's such a popular visualization tool.
  -  Tableau Public -  Tableau Public allows you to create visualizations that are easy to read and understand. Everything you do with Tableau Public occurs on your computer.
  -  Tableau Desktop - I am currently using Tableau Desktop to work on the deliverables, however later will upload the story on Tableau Public.
  -  Tableau Server - Tableau Server allows to privately share your visualizations with others. One can create visualizations locally in Tableau Public and then can upload the       visualizations to Tableau Server.

2. Pandas - Jupyter notebook was used to write code Deliverable 1 using Pandas library.
3. Data used - For this project, we'll use data from the Citi Bike program in New York City. This data includes a variety of fieldsand the data downloaded will be contained in a flat file, a CSV. To get access to the data, one can follow the steps described below-

Go to the Citi Bike System Data page (Links to an external site.). In the "Citi Bike Trip Histories" section, click the link that says "downloadable files of Citi Bike trip data". This link will take you to an index of trip data. Scroll down the list to '201908-citibike-tripdata.csv.zip'. This zip file contains all the August 2019 data. We'll use data from August because there is likely more traffic during the summer months. 

### Import Citi Bike Data
In Tableau, there are a variety of different options when it comes to data sources. You can have flat files such as CSV, PDF, and TXT files, as well as other data sources like databases and data streams. (These will mostly be SQL databases). There are two primary ways that Tableau connects to the data you provide: through live data or extract data. Both have their benefits and uses.

Live data is primarily databases such as MySQL and Microsoft SQL Server. Live data is just what it sounds like: live data. This type of data is updated every time you view the dashboard, since it's possible that the data has changed in your database.

Extract data is primarily when you use files such as CSV, TXT, or PDF. These files remain unchanged unless you pull a new extract of the data. For example, if you update the file, you would have to update it in Tableau as well.

For our analysis, we'll import the CSV file, which contains all the data we'll need this project. Therefore, we'll technically be working with extract data for our project.

## Overview of the Analysis : 

### Purpose:

There is still some more work to be done to convince investors that a bike-sharing program in Des Moines is a solid business proposal. To solidify the proposal, one of the key stakeholders would like to see a bike trip analysis. For this analysis, we will use Pandas to change the "tripduration" column from an integer to a datetime datatype. Then, using the converted datatype, we will create a set of visualizations to:

- Show the length of time that bikes are checked out for all riders and genders
- Show the number of bike trips for all riders and genders for each hour of each day of the week
- Show the number of bike trips for each type of user and gender for each day of the week.
- Finally, will add these new visualizations to the two created before for the final presentation and analysis to pitch to investors.



## Results :

### 1. Deliverable 1 - 

In Deliverable 1, you’ll use Pandas to change the datatype of the "tripduration" column from an integer to a datetime datatype to get the time in hours and minutes. Using Tableau instead of Pandas to change the datatype of the "tripduration" column to a "Date and Time" will not produce the same visualizations in Deliverable 2. Trying to change the datatype by creating a calculated field may take more time for the less experienced Tableau user than the steps in Deliverable 1.

Using Python and Pandas functions, we will convert the "tripduration" column from an integer to a datetime datatype to get the time in hours, minutes, and seconds (00:00:00). After converting the "tripduration" column to a datetime dataytpe, we will then export the DataFrame as a CSV file to use for the trip analysis in Deliverable 2. 
- In Step 1, create a DataFrame from the 201908-citibike-tripdata.csv file.
- In Step 2, check the datatypes of each column in the DataFrame.
- In Step 3, convert the "tripduration" column to a datetime datatype by passing the DataFrame column and the units inside the to_datetime() function.
- In Step 4, check the datatypes of the DataFrame.
- In Step 5, export the DataFrame as a new CSV file without the index column. Use this new CSV file for Deliverable 2.
The code for the above steps is displayed below - 

![code1](https://user-images.githubusercontent.com/23488019/152094685-383f9077-36c2-467b-9b2e-733d06718553.PNG)
![code2](https://user-images.githubusercontent.com/23488019/152094691-9169fb77-b769-4614-9420-b884291d4f00.PNG)
![code3](https://user-images.githubusercontent.com/23488019/152094694-d9130fdb-db04-4289-8b01-bead590a75ab.PNG)


### 2. Deliverable 2 - 

Once we change the datatype, we will export the DataFrame as a CSV file to use for the visualizations in Deliverable 2. We will be creating a new Tableau workbook to create the visualizations in Deliverable 2.

Using Tableau, we will create visualizations that show - 
- How long bikes are checked out for all riders and genders.
- How many trips are taken by the hour for each day of the week, for all riders and genders.
- A breakdown of what days of the week a user might be more likely to check out a bike, by type of user and gender.

#### 1. Create the Checkout Times for Users Viz - 
In this visualization, we will graph the length of time that bikes are checked out for all riders.

- Add the number of records or the generated field that counts the number of records in the CSV file to the Rows.
- Add the "tripduration" column you converted to the Columns, and filter the "More" option by "Hour".
- Add the "tripduration" column again to the Columns, and filter the "More" option by "Minute", and then change the values from "discrete" to "continuous".
- Add the "tripduration" column that shows the "Hour" to the Filters field, and select "Show Filter".
- Edit the X and Y axis labels by right-clicking on the axis label and selecting "Edit Axis".


![Checkout times for users](https://user-images.githubusercontent.com/23488019/152095227-4c2ae3dd-2314-4eaf-9abc-f310213b0327.PNG)


From the visualization it can be noted that, the checkout time for users was 5 minute and the count of such biking trips was 146,752.

![extra5](https://user-images.githubusercontent.com/23488019/152417473-0b4c247a-a171-40e3-a0eb-e2ea15a4cff3.png)

Also, Bikes are checked out for an average of 1 hour (60 minutes) at a time.

#### 2. Create the Checkout Times by Gender Viz - 
In this visualization, we will graph the length of time that bikes are checked out for each gender. Just so that the gender is visible in the string format, we need to convert the type of gender column in our Datasource to String format. We can the use the 'Create Calculated Field' to convert '0','1' and 2 to 'Female', 'Male' and 'Unknown'.

![gtostring](https://user-images.githubusercontent.com/23488019/152095961-e5fc5927-813a-4442-a28e-8436d8ad5c5c.PNG)

In this way we will get the converted Gender column named as 'Number to String'. Then we can do the following steps -
- Add the number of records or the generated field that counts the number of records in the CSV file to the Rows.
- Add the "tripduration" column you converted to the Columns, and filter the "More" option by "Hour".
- Add the "tripduration" column again to the Columns, and filter the "More" option by "Minute", and then change the values from "discrete" to "continuous".
- Add the "tripduration" column that shows the "Hour" to the Filters field, and select "Show Filter".
- Add the converted column for gender as a color to the Marks field, add it to the Filters field, and select "Show Filter".
- Edit the X and Y axis labels by right-clicking on the axis label and selecting "Edit Axis".

![Checkout times by gender](https://user-images.githubusercontent.com/23488019/152095410-c0225aaa-7af3-446f-b7b8-10defa92bd27.PNG)

From the visualization it can be noted that, the checkout time for male was faster at 5 minutes as compared to females at 6 minutes.

![extra4](https://user-images.githubusercontent.com/23488019/152417242-9da4b607-e3d4-4655-b0b6-4b8583554be5.png)

ALso, the majority of Bike Share users are Male.

#### 3. Create the Trips by Weekday for Each Hour Viz - 
In this visualization, we will graph the number of bike trips by weekday for each hour of the day as a heatmap.

- Add the "Starttime" column to the Rows, and filter the "More" option by "Hour".
- Add the "Stoptime" column to the Columns, and filter the “More” option by "Weekday".
- Add the number of records or the generated field that counts the number of records in the CSV file to the Marks field as a color. Select "Automatic" for the type of graph to create the heatmap.
- Format the Y axis of the Starttime by Hour to show the 12-hour format.
- Format the X axis of Stoptime by Weekday as "Abbreviation".


![Trips by Weekday for Each hour](https://user-images.githubusercontent.com/23488019/152096437-3d2857bc-4ae1-4ba8-94aa-f32993471064.PNG)

From the visualization it can be noted that, the maximum trips were made on Thursday and the busiest hour was 6 pm with 44,905 bikerider trips.

![extra3](https://user-images.githubusercontent.com/23488019/152416709-72d6817f-a4a3-4df3-a57c-97f1706838e2.png)

The most popular time frame for the usage of bikes is on weekdays from 7am-9am & 5pm-7pm. we can also see that on weekends, the bike usage is spread out throughout the day between 10am and 7pm.

#### 4. Create the Trips by Gender (Weekday per Hour) Viz - 
In this visualization, we will graph the number of bike trips by gender for each hour of each day of the week as a heatmap.
- Add the "Starttime" column to the Rows, and filter the "More" option by "Hour".
- Add the "Stoptime" column to the Columns, and filter the “More” option by "Weekday".
- Add the number of records or the generated field that counts the number of records in the CSV file to the Marks field as a color. Select "Automatic" for the type of graph to create the heatmap.
- Add the converted column for "Gender" to the Columns and to the Filters field, and select "Show Filter".
- Format the Y axis of the Starttime by Hour to show the 12-hour format.
- Format the X axis of Stoptime by Weekday as "Abbreviation".


![Trips by Gender(Weekday per Hour)](https://user-images.githubusercontent.com/23488019/152096460-f020aa36-00f5-421a-9b9e-0be3a71945e7.PNG)

From the visualization it can be noted that,on Thursdays 6pm, the count of Male bikers is the maximum at 30,749. Also, the maximum frequency of Bike usage is contributed by Male users on the weekdays, especially Thursdays, between the hours of 7am-9am & 5pm-7pm.

![extra1](https://user-images.githubusercontent.com/23488019/152416026-3822afd5-ccb3-470b-8c85-a2766c48e34e.png)

#### 5. Create the User Trips by Gender by Weekday Viz - 
In this visualization, you'll create a heatmap that shows the number of bike trips broken down by gender for each day of the week by each Usertype.

- Add the converted column for "Gender" to the Columns and to the Filters field, and select "Show Filter".
- Add the "Usertype" to the Rows and to the Filters field, and select "Show Filter".
- Add the "Starttime" column to the Rows, and filter the "More" option by "Weekday".
- Add the number of records or the generated field that counts the number of records in the CSV file to the Marks field as a color. Select "Automatic" for the type of graph to create the heatmap.

![Trips by Gender by Weekday](https://user-images.githubusercontent.com/23488019/152095496-32c1d1cd-30fc-408b-8246-932f8b6dca70.PNG)

From the visualization it can be noted that, there are maximum male subscribers for Thursday and the total count of such subscribers is 259,316.

![extra2](https://user-images.githubusercontent.com/23488019/152416419-456b2760-1da4-46f1-83cb-e8b20b9a11f2.png)

 We can also conclude that the majority of Bike Share users are Male & Subscribers of the Bike Share service provided.

#### 6. Extra Visualization - August Peak Hours -
This visualization was created since August can be a good month to visit New York City. We hence figured out the peak hours for bike trips during the month of August. This will help our investors get a ballpark estimate of how many bikes we might need in Des Moines. A key piece of data we need is the peak usage hours for the month of August. This will help us get a better idea of how many bikes we might need in Des Moines, as well as figure out during which parts of the day we'll need the most bikes. For example, if we need to do maintenance on a bike, knowing the peak usage hours will help us plan for the best time to do that.

![extra_August Peak hours](https://user-images.githubusercontent.com/23488019/152418566-95470280-c694-40fe-90b0-10dcce4e9955.PNG)

From the visualization it can be noted that, in the month oof August, the starttime of 17hrs or 5:00 pm is the peak hour for all the bikeriders. The least popular hour for biking was 3:00 am in the morning. The time frame for the least bike activity is from 2am to 4am in the morning.


#### 7. Extra Visualization - Average Trip Duration -
 In this visualization we created the graph for the average duration of a bike ride, by age. This will help us set expectations for trip duration in Des Moines.

![extra average trip duration](https://user-images.githubusercontent.com/23488019/152419981-e52fdd0a-8e35-4e0a-b4e6-cc692f0c9066.PNG)

From the visualization it can be noted that, for the birth year 1890, the average trip duration is over 2600. In general, the later the birth year the longer is the ride duration. It means that the youngest riders tend to use the bikes for longer periods of time. 

#### 8. Extra Visualization - Bike Utilization - 
Our investors are curious about the bike utilization during the month of August. For that we need to show the utilization of each Citi Bike in New York City. This will continue to help us understand the needs of a bike-sharing business in Des Moines. For this task I will use the bike ID as a metric for determining which bikes have the highest utilization.

![extra 6](https://user-images.githubusercontent.com/23488019/152421204-9649ef53-bd77-4b43-a196-c7912d1ec317.png)

In this visualization, we created the bubble plot for bike utilization levels. If a bike has a higher utilization level, it will be a larger bubble. Hence it can be noted that the Bike iD 39570 has the highest bike utilization since its trip duration is 3,838,467.


### 3. Deliverable 3 -  

I will be creating a new Tableau workbook to create the visualizations in Deliverable 2, and then will create additional visualizations as shown above, that will be used for the Story in Deliverable 3. 


#### Creation of Story -

The investors were impressed with our work on the NYC Citi Bike Analysis. The data was readable and digestible. Now they want something that tells a story about the data we presented. Stories allow us to view different data simultaneously, but their main purpose is to tell a story, share a point of view, or convince an audience to take a particular stance. Stories do this by sequencing visualizations to help the audience understand the bigger picture. In our case, we want to create a story that explains why you think, given the data, that starting a bike sharing company in Des Moines is a good idea. For this we'll use data from our worksheets with additional elements that provide more context. Click below to access the complete data visualization story for Bikesharing:

[Link to NYC BikeSharing Story](https://public.tableau.com/app/profile/aakriti8624/viz/Bikesharing_16439273815370/BikesharingStoryforNYC?publish=yes)




## Summary : 

The data visualizations performed in this project have been extremely helpful in answering a number of questions arising in the minds of the stakeholders and organizaers. It can be concluded that the bike share service provide a number of facilities for the bikers as subscribers and customers. For performing bike maintenance, the least active timeframe during the day, that is, 2am to 4am is most suitable sinec that time frame is going to be least used by a user. Also, the evening time on weekdays is most popular among bikers especially male members and the best time for their use is in the evenings between 5pm and 7pm. This may also suggest that in the month of August 2019 in New York City, most of the users might be biking to and fro work, since the major usage is between the office hours. Hence it seems like biking is a well liked activity in NYC and in summer, it can be a popular transportation service in the city.

The two additional visualizations suggested for future analysis are as follows - 

  1. Although it seems like biking is popular in summer months in NYC, further analysis will be needed to be done for the winter months. Just an   analysis for a favorable month is not enough to gauge in the pros and cons of operating the Bike services. I would definitely perform data visualizations for the winter months especially December, January and February.
  
  2. More details can be added for the bike users such as their address is of a residential place or a hotel or temporary accomodation so that it can be determined if the bike usage is more for the local people or more for tourists like us. It should be also noted that even if a lot of tourists visit the city, not every tourist will be interested in renting a bike. Hence a detailed study need to be done on this aspect as well. This data generated can then be used to compare the usage for Des Moines since it does not get as many visitors as NYC.

 
### References:
1. https://courses.bootcampspot.com/courses/791/pages/14-dot-0-4-citi-bike-cruisin?module_item_id=302505
2. https://ride.citibikenyc.com/system-data


### Link to the BikeSharing Data Visualization Story
[Link to NYC BikeSharing Story](https://public.tableau.com/app/profile/aakriti8624/viz/Bikesharing_16439273815370/BikesharingStoryforNYC?publish=yes)
