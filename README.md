# python-api-challenge
Module 6 Challenge
===========================


**Background**

Data's true power is its ability to definitively answer questions.  As earth’s weather cannot be controlled, we can use historical data on weather to predict weather patterns and make better data-driven decisions.

In this challenge, Python requests, APIs, and JSON traversals were used to answer a fundamental question: "What is the weather like as we approach the equator ?"

The following two websites were used to obtain API keys:
1.	VacationPY - https://www.geoapify.com/
2.	WeatherPY - https://openweathermap.org/api
   
![image](https://github.com/Mago281/python-api-challenge/assets/131424690/b0c78842-4e74-415f-b76f-f07737979836)


---

**VacationPy**

For this part of the challenge, I used Jupyter notebook, the geoViews Python library, and the Geoapify API to plan future vacations.  The code provided for this challenge was used to import the required libraries and load the CSV file with the weather and coordinates data for each city.
I mainly used the Geoapify API and the geoViews Python library to create map visualisations.

*Step 1:	Created a map that displayed a point for every city in the `city_data_df` DataFrame.  The size of the point was the humidity in each city.*

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/4179f49e-ab1d-4b74-a1bc-ae930987d124)


*Step 2:	Narrowed down the `city_data_df` DataFrame to find the ideal weather condition*

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/cc063221-3dd4-4f37-9eda-4f386e3a0937)


*Step 3:	Created a new DataFrame called `hotel_df`.*

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/35037d1c-aefa-46ac-b92a-a429574c91d9)

 
*Step 4:	For each city, used the Geoapify API to find the first hotel located within 10,000 metres of my coordinates.*

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/d25944bf-5e2c-4c60-81ac-792fa43c5505)

 
*Step 5:	Added the hotel name and the country as additional information in the hover message for each city in the map.*

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/7a5751e7-e8c0-4a52-94a8-0a4c95dd4862)

---

**WeatherPY**

A Starter Code was provided so as to be able to generate random geographic coordinates and a list of cities by using the `citipy` library.

*Created Plots to Showcase the Relationship Between Weather Variables and Latitude*
To fulfill the first part of my analysis, I used the OpenWeatherMap API to retrieve the weather data from the cities list generated in the starter code.  The cities weather data was then converted into a Pandas DataFrame and a sample of the data was displayed:

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/efb3c9ea-322f-4afa-8593-2ef1522917b9)


I then created a series of scatter plots to showcase the following relationships:

•	Latitude vs. Temperature

 ![image](https://github.com/Mago281/python-api-challenge/assets/131424690/7f6e296b-f08e-456d-a14b-0537a3ef3bff)
 

•	Latitude vs. Humidity

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/e1a30c9d-2a1b-41c1-8f6c-a7f461ae7330)

 
•	Latitude vs. Cloudiness

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/1c8df13d-0056-4cd3-b1c6-e41edaace0eb)

 
•	Latitude vs. Wind Speed

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/f8ef1453-b210-4cbf-8530-0ff233315c79)

 
---

***Computed Linear Regression for Each Relationship***

For the second part of my analysis, I ran a linear regression on each relationship listed above after separating the plots by Northern (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude).

Next, I created a DataFrame with the Northern Hemisphere data (Latitude >= 0) 

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/a671b65a-5f76-41ed-af5d-b8242c24f4d3)

 
and a DataFrame with the Southern Hemisphere data (Latitude < 0):

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/193a6bb4-6cec-4359-99b3-2814c5cf040c)

 
Next, I plotted a series of scatter plots with linear regression lines, the models’ formulas, and the R values on the Northern and Southern Hemispheres.  I also provided analyses of what relationships the plots indicated.

NOTE:	An R-value of 1 indicates a perfect positive linear relationship, while an R-value of -1 indicates a perfect negative linear relationship.  An R-value of 0 suggests no linear relationship.

---

•	Northern Hemisphere: Temperature (C) vs. Latitude
The R-value is: 0.7418385760864274

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/839478a4-367c-44b7-9a5c-2babd7c56a34)

 
•	Southern Hemisphere: Temperature (C) vs. Latitude
The R-value is: 0.5181619771464621

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/db2efd09-20c3-4f37-a055-ecbb701ee0a4)

 
OBSERVATION:
---------------
There is an inverse correlation between the latitudes and the temperatures.

In Temperature vs. Latitude Linear Regression Plots on the Northern Hemisphere and the Southern Hemisphere, the two R-values of 0.7418385760864274 & 0.5181619771464621 respectively indicate a moderately strong positive linear relationship between the "x" and "y" variables i.e. between the Latitude and the Temperature.

The two linear regression equations describe how "y" (Temperature) changes with changes in "x" (Latitude).  This means that the lines are reasonably good fits for the data, and can be used to make predictions about "y" (Temperature) based on the values of "x" (Latitude).

---

•	Northern Hemisphere: Humidity (%) vs. Latitude Linear Regression Plot
The R-value is: 0.02825154105884831

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/c239e154-52e5-45ec-b5e9-b287fceb1d9e)

 
•	Southern Hemisphere: Humidity (%) vs. Latitude Linear Regression Plot
The R-value is: 0.057362528661052216

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/4e7ff3ae-8db7-4325-841e-6f8caec4ee32)

 
OBSERVATION:
---------------
There is in Humidity vs. Latitude Linear Regression Plots on the Northern Hemisphere and the Southern Hemisphere, the two R-values of 0.02825154105884831 & 0.057362528661052216 respectively indicate very weak linear relationships between the "x" and "y" variables i.e. between the Latitude and the Humidity.

The two low R-values suggest that the data points are not well explained by the linear models.  This suggests that these two  linear models are not good fits for the data, and may not be very useful for making predictions about Humidity based on the values of the Temperatures.

---

•	Northern Hemisphere: Cloudiness (%) vs. Latitude Linear Regression Plot
The R-value is: 0.02596306246371301

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/de69454e-1370-49f6-b49d-6c4a8e91c557)


•	Southern Hemisphere: Cloudiness (%) vs. Latitude Linear Regression Plot
The R-value is: 0.014027567648827993

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/75e0eb0f-cd62-45cf-a7b6-a091051c84bb)

 
OBSERVATION:
---------------
From the plots on the two graphs above, we can determine that there is no correlation between cloudiness levels and the latitudes.

In the two Cloudiness vs. Latitude Linear Regression Plots, the two linear regression equations of y = 0.33x + 51.59 & y = 0.32x + 66.11 describe how "y" (Cloudiness) changes with changes in "x" (Latitude) but the r-values of 0.02596306246371301 and 0.014027567648827993 indicate very weak linear relationships between the two variables. 

This suggests that the linear model is not a good fit for the data, and it may not be very useful for making predictions about "y"(Cloudiness) based on the values of "x" (Latitude).

---

•	Northern Hemisphere: Wind Speed (m/s) vs. Latitude Linear Regression Plot
The R-value is: 0.03947205138213818

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/3038c700-521b-450f-9116-1d3a598502a3)

 
•	Southern Hemisphere: Wind Speed (m/s) vs. Latitude Linear Regression Plot
The R-value is: 0.07706443649353777

![image](https://github.com/Mago281/python-api-challenge/assets/131424690/d63d168f-2b13-4e7e-a77b-62227185de9c)

 
OBSERVATION:
---------------
The two scatter plots above for Wind Speed vs. Latitude show that there is no correlation between Wind Speeds and Latitudes.

R-values of 0.03947205138213818 and 0.07706443649353777 indicate very weak linear relationships between "x" (Latitude) and "y" (Wind Speed).

The coefficients of "0.03" and "-0.05" (the slopes) are very small rates of changes in "y" (Wind Speed) with respect to changes in "x" (Latitude).

---





















