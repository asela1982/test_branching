# Overview

**Project** :  
How socio-economic factors are influencing on how people socialize

**Team Name** :   
Data Analytics Meetup News(D.A.M.N)

**Team** :   
* Subhashini Chodavarapu
* James Briley
* Antonio Kufoy
* Asela Dassanayake

**Outline** :   
1. Research question
2. Data sources used
3. Notebooks used for the analysis 
4. Conclusion

## 1. Research question

A social atmosphere provides a relaxed, informal environment where people can connect, share ideas, and form collaborations. This project attempts to synthesize as to how social economic factors are influencing how people socialize. Socio-economic factors are lifestyle components and measurements of both financial viability and social standing. Factors such as health status, income, environment and education are studied by sociologists in terms of how they each affect human behaviors and circumstances.

## 2. Data sources used

Socializing : https://www.meetup.com/meetup_api/  
Cenus : https://factfinder.census.gov/  
Tempreature : https://openweathermap.org/api  

## 3. Notebooks used for the analysis

1. 1_census_table.ipynb  
This notebook constructs the summary table using census data collected. we have used ZCTAs(ZIP Code Tabulation Areas) to gather certain socio-economic indicators (Household income, Median age, Race, Education)
Readme.md in the data_input folder contains a description of the the data files acquired from factfinder on census. 

2. 2a_meetup_cities.ipynb  
This notebook simply uses the Meetup API's cities end-point to gather 200 cities per each state and the member count for each city.

3. 2b_viz_meetup members.ipynb  
This notebook visualizes the meetup cities that we obtained from the 2a_meetup_cities.ipynb.

4. 3a_meetup_groups.ipynb  
This notebook uses a sample of ZCTAs(1000) from the summary census data, and extracts the most active 50 meetup groups per each ZCTA based on lat and long within a 50 miles radius. 

5. 3b_viz_popular_categories.ipynb  
This notebook uses the extracted information on meetup groups from 3a_meetup_groups.ipynb to visualize on a map the most popular meetup category for the selected sample of 1000 ZCTAs.

6. 4_statistical_tests.ipynb  
This notebook visualizes and statisically test the association between the type of socializing and the socio-economic factor. Each marker on the box plot represents a ZCTA from the sample of 1000. 

7. 5_meetup_events.ipynb  
This notebook uses the open events end-point to gather event data for each of the ZCTA in the sample of ZCTAs(using lat and long of the ZCTA) . It takes only a sample of 1000 events and uses the group end-point to gather the meetup category for each event using the group-id of the events. Then a factor plot is drawn to visualize the distribution of events by day of the week for each category.

9. 7_Events_Comments_Requests.ipynb
   This notebook uses the events-comment end point to gather the comments made on each event. The comments about each event was then        analyzed using Vader Sentiment Analysis. The overall sentiments seems to be varying from neutral to positive for the events.

10. 6d_data_enrichment_and_final_plots.ipynb
    This notebook started off with the census data and added meetup data for venues. Then used the OpenWeatherAPI to add temperature         data for each location. Lastly, this data was used to plot venue rating and temperature against number of MeetUp members.
   
## 4. Conclusion

Based on the statistical tests, we can see there is an association between socio economic factors and socialzing. Further, we also gathered location based preference on socializing aswell as time based preference(by looking at the most popular days for certain types of socializing). Based on the insights found, We would evenutally want to build a web application to recommend ways in which individuals could socialize based on their current certain social economic status. 

