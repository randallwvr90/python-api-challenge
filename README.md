# python-api-challenge

## Table of Contents
* [Background](#background)
* [Analysis](#analysis)

## Background
Using Python requests, API's and JSON transversals to answer the question" "What's the weather like as we approach the equator?"
* WeatherPy
  * WeatherPy.ipynb is a jupyter notebook that will visualize the weather of 500+ cities across the world of varying distance from the equator. Uses the python library citypy and the OpenWeatherMap API. 
  * The WeatherPy notebook will be used to create scatter plots that display the following relationships:
    * Temperature vs. Latitude
    * Humidity vs. Latitude
    * Cloudiness vs. Latitude
    * Wind Speed vs. Latitude
  * A linear regression will be run on each of these relationships. Each of the above relationships will be displayed along with a linear regression on a pair of plots: one for the Northern Hemisphere and one for the Southern Hemisphere. 
  * The analysis and data will be saved in a CSV file and PNG images of each scatter plot. These will be saved in the output_data directory. 
* VacationPy
  *  The goal is to create a heat map using the humidity data from all the cities in WeatherPy. 
  *  Next, the balmiest cities will be picked - filtering by heat, humidity, wind, and cloudiness. 
  *  From this short list of cities with the best weather, the google maps API will be used to find hotels within .5 km from the city centers. The first hotel on the list will be displayed as pins on the heat map. 

## Analysis
This analysis can be found here or at the end of the WeatherPy jupyter notebook. Here are some trends I saw in the data:
* There is a relatively strong (r = 0.869) inverse correlation between latitude and temperature in the northern hemisphere. This makes sense since it should be colder further from the equator. However, the correlation between latitude and temperature in the southern hemisphere is much less strong (r = 0.371). The data points are not clustered very closely around the trend line. This could be because there are not as many large continents south of the equator. The temp vs latitude graphs show no cities south of 60 degrees south latitude, while there are cities north of 80 degrees north latitude. If there were more land between 60 and 80 degrees south, the trend might be stronger. 
* There is a positive correlation between latitude and humidity. This is especially apparent in the northern hemisphere. Because it is currently winter in the northern hemisphere, the temperatures are much lower farther north. The humidity information shows relative humidity, which is dependent on temperature. It is a percentage of the maximum amount of water dissolved in the air. Because cold air can hold much less water, any moisture in the air will have a greater impact on the relative humidity than it would for warm air. Even though there is probably much less moisture in the air in an absolute sense, the relative humidity can be quite high. 
* The windspeed graph shows local minima and maxima. Winds are stronger between 0 and 20 degrees north, and there are weaker winds north and south - from about 20 to 40 degrees and 0 to -15 degrees. Farther north than 40 and farther south than -15, the winds are much stronger. This is likely due to global wind patterns - the weaker winds on either side of the center peak are probably the "doldrums" - certain latitudes with much less wind. 
