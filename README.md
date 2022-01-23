# World_Weather_Analysis
Module 6 prep work and module completed by Hannah Wikum in January 2022
___

# Overview of Project
This project involved generating random coordinates, using citipy to find nearest cities, and creating API keys for both weather and maps to find city and hotel vacation recommendations by simply specifying your ideal min and max temperatures.

## Part 1
The first part of the project was to create a weather database starting with 2000 random lat/long pairs. Here is a summary of the steps:

 * generated a random list of latitude and longitude coordinate pairs using np.random.uniform
 * used citipy to find the nearest city for each random coordinate pair
 * used an API key to get weather data for each city in a JSON format from openweathermap.org
 * added information to a DataFrame that listed city, country code, latitude, longitude, max temp, humidity, cloudiness, wind speed, and a current weather description
 * exported the final DataFrame to a CSV

## Part 2
Using the list of cities and related country, latitude, longitude, and weather data from the CSV in part 1, I narrowed down possible trip destinations based on the user's preferred min and maximum temperatures. For this analysis, I used 70-85 degrees Fahrenheit. Here is a summary of the steps:
 
 * imported the CSV from part 1
 * prompted the user to enter a preferred minimum and maximum temperature value to help narrow down destinations
 * filtered the DataFrame based on the min/max temperature inputs
 * checked for and then dropped rows with empty values
 * copied some of the info to a new DataFrame with an additonal, blank Hotel Name column
 * searched for hotels within 5,000m using JSON data from Google Directions API
 * filled in empty hotel cells with NaN before using a df.dropna() to remove the bad rows and create a clean hotel DataFrame
 * exported the resulting clean DataFrame to a CSV
 * added markers for each city to a map, as well as informational boxes that shows hotel, city, country, current weather description, and max temperature when you click on it

## Part 3
After creating the list of all vacation destinations within my preferred temperature, I narrowed it down to a trip with four nearby cities in the same country for the final exercise. Here is a summary of the steps:

 * imported the CSV from part 2
 * added the info box and markers to the world map to see all the options before selecting four nearby cities for the remaining trip analysis
 * create five DataFrames for the start, end, and stops 1, 2, and 3 using the loc method to filter on the four cities I selected
 * extracted the latitude/longitude pairs for each city on the intinerary using to_numpy and then the index of each column
 * added a direction layer to the map showing a driving route between the four cities and back to the start
 * combined the DataFrames for all four cities into one using pd.concat()
 * added a info box marker layer for the four cities to the map to show hotel, city, country, weather, and max temp 
