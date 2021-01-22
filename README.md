# SQLAlchemy_Challenge

This project consists of two main steps: 

STEP 1: Climate Analysis and Exploration

This step was completed using Python and SQLAlchemy to conduct climate analysis and data exploration of a climate database.
- Used SQLALchemy to connect to a sqlite database
- Used SQLAlchemy to reflect tables into classes and save a reference to those classes
- Linked Python to the database by creating an SQLAlchemy session

Precipitation Analysis
- Found the most recent data in the data
- Retreived the previous year's worth of precipitation data by querying the data
- Loaded the query results into a Pandas DataFrame and set the index to the date column
- Sorted the Data Frame values by date
- Plotted the results using the DataFrame plot method
- Used Pandas to print the summary statistics for the precipitation data

Station Analysis
- Designed a query to calculate the total number of stations in the dataset
- Designed another query to find the most active stations
	- Listed the stations and observation counts in descending order
	- Found which station is has the highest number of observations
	- Used the most active station id and calculated the lowest, highest, and average temperature
- Designed a query to retrieve the last twelve months of temperature observation data
	- Filtered by the station with the highest number of obervations
	- Queried the last twelve months of temperature observation data for the given station
	- Plotted the results as a histogram

STEP 2: Climate App

After completing the initial analysis, a Flask API was designed based on the queries developed
- Used Flask to create routes

Routes

- /
	- Home page
	- Listed all available routes
- /api/v1.0/precipitation
	- Coverted the query results to a dictionary useing date as the key and prcp as the value
	- Returned the JSON representation of the dictionary
- /api/v1.0/stations
	- Returned a JSON list of stations from the dataset
- /api/v1.0/tobs
	- Queried the dates and temperature observations of the most active station for the last year of data
	- Returned a JSON list of temperature observations (TOBS) for the previous year
- /api/v1.0/<start> and - /api/v1.0/<start>/<end>
	- Returned a JSON list of the minimum, average, and maximum temperatures for a given start of start-end range
	- When given the start only, calculated the TMIN, TAVG, and TMAX for all dates greater than and equal to the start date
	- When given the start and end dates, calculated the TMIN, TAVG, and TMAX for dates between the start and end states. 
