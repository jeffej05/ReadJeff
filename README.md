# ReadJeff



A Readme for Jeff's Github repositories. This is intended to supplement my resume.

Last Updated August 2019

# I see you have a GitHub account, Jeff. What are all these projects?



## <font color= green>IBM Coursera Capstone Project</font> 


This project utilizes clustering algorithms, venue data from the Foursquare API, and weather data from the OpenWeatherMap API in order to help restaurant owners decide which New York or Toronto neighborhoods they should consider opening up a restaurant in. Web scrapping was used to obtain neighborhood postal codes from Wikipedia and Geopy was used to determine the corresponding latitudes and longitude values for these neighborhood postal codes. I've broken up the thought process behind the project below and listed any limitations or improvements that can be made to the project. 

1.) Industrial Organization, a field of economics that focuses on the theory of the firm, suggests that firms in similar industries will start to aggregate around a pareto optimal focal point in any geospatial plane in order to reduce transportation costs for customers and thus maximize customer acquisition. For this reason, we are interested in neighborhoods that showcase relatively high frequencies of restaurant venues as this will serve as an indicator of a prime location to open up shop.

2.) Many studies indicate that the weather has a tremendous effect on the restaurant business by ultimately influencing customer behavior. Temperature, humidity, and outside weather conditions (rain, clear sky, etc.) can all have an effect on overall restaurant revenues, so it is important that we incorporate weather data. Since different restaurants have different sensitives to the weather (i.e. ice cream shops would favor higher temperatures; hot-pot restaurants would favor lower temperatures), we will let the restaurant owner decide what temperature and humidity ranges are most suitable for them. Rain and snow, however, seems to always have a negative impact on the restaurant business so we will favor locations that show the highest frequency for "clear skies" weather condition.

3.) Standard clustering algorithms based off the calculation of Euclidean distance were used to group similar neighborhoods together. This gave us more insight into what type of restaurants aggregated together at which particular neighborhoods. This would give the restaurant owner more detailed information and would dramatically cut down the list of potential locations he/she would need to consider. In the future, we can consider implementing more advanced algorithms such as DBSCAN (Density-Based Spatial Clustering of Applications with Noise).

4.) There are many other factors that should be considered when opening up a restaurant such as the area's demographics, per-capita income, rent per square footage, market saturation, the type of restaurant being opened, local supplier costs, differences in inspection standards, currency fluctuations and current business cycle positions between countries. Moreover, the 5-day weather forecast API option was the most extensive forecast coverage that was cost-free, so I utilized this for the project. It definitely would've been better to use a year's worth of weather data, but this type of API access was expensive.





## <font color= green>Revenue-at-Risk Automated Report</font>


This was my first big automation project with python. The Revenue-at-Risk Report tracks all of IBM Watson Advertising's current campaign performances in terms of delivery and percentage pacing towards our overall booked revenue goal. I've broken down the features of this report below and any thoughts on how it can be improved for the future as the automation process is still ongoing for this report. Please note that all confidential company and personal information has been taken out of the script.

1.) Data Import- We are currently manually downloading the raw data CSV file from Qlik Sense but for the future, the plan is to either set up a direct connection to the database using pyodbc or utilize Selenium to automatically log into Qlik Sense to retrieve the csv data file for us. This way, we will have an automated report pulling process for this report.

2.) Data Manipulation- The program will automatically clean up the datasets used for the report.

3.) Calculations- The report tracks week-over-week improvements so the program will automatically import the previous report from our report directory and calculate week-over-week changes in revenue and delivery risk. 

4.) Excel Export- The weekly report features pivot tables and raw data sets that is sent as an excel file to account managers and senior leadership. The program will automatically create these excel files for us. In the future I would love to include more graphs to visualize under-delivery via matplotlib or seaborn. 

5.) Word Export- The weekly report features an email that lists all the current accounts that show under-delivery risk as well as updated notes sent by account executive on what is being done to mitigate this risk and if things have improved. The program will automatically write out this email into a word doc so it can be reviewed by the report owner just in case the owner wants to add any additional comments.

6.) Google Sheets Export- The program will push the "late creative" pivot in Google Sheets via gspread so Account Executives can add in their weekly notes and comments regarding the status of their accounts.

6.) Email Automation- The program will log into the users' email account, create an email subject and body, and attach the excel and word documents that were previously created, and will send it to all relevant recipients.

6.) Cron Job- The report is sent out every Monday and Thursday at around 11am. A cron job was set up in the terminal to mimic this execution schedule.
