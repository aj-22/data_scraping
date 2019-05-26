## Wikipedia Scraper - USA Cities

### Introduction
This web-scraper is my submission to Topos coding round for the Data Engineering Internship.  
It fetches the population data of top 314 U.S. Cities from Wikipedia.  
To be specific, from the below link:  
https://en.wikipedia.org/wiki/List_of_United_States_cities_by_population  

Additionally, it fetches the historical population trend from each of the top 314 cities by scraping the sub-links from the above url.

There are some cities (for example: Anaheim, California) where the historical population is not present in the Wikipedia webpage.  
In such cases, the program will notify the user.  

Ultimately, we get two tables:  
- cities_main which contains population of top 314 cities  
- cities_hist which contains historical population trend of top 314 cities  

### Files Uploaded

Three files have been uploaded as a part of my submission  
- scraper.ipynb : Python Notebook (jupyter)  
- cities_main.csv : Cleaned CSV file with data from the above mentioned link  
- cities_hist.csv : CLeaned CSV file with data from the city sub-links  

#### Scraper notebook
scraper.ipynb requires following libraries  
- requests
- bs4
- pandas
- urllib  
Other than that it has no dependencies. It can be run standalone in Jupyter without creating a specific folder structure.  
All the routines and functions are coded.

#### Output files
cities_main.csv and cities_hist.csv are two output files  
the first column is the city_name which can be used as a key to join these tables  
All the columns names are self explanatory and as such no further description may be required  
1. Schema of cities_main
   - City
   - 2018rank
   - State
   - 2018estimate
   - 2010Census
   - Change
   - 2016 land area (sq miles)
   - 2016 land area (sq km)
   - 2016 population density (sq miles)
   - 2016 population density (sq km)
   - Location
   - Link

2. Schema of cities_hist
   - city_name
   - Year
   - Pop.
   - ±% (Percentage change)
   

*Note: The CSV files can be loaded to BigTable by setting the following API Parameters:*
 - *--field_delimiter ','*
 - *--skip_leading_rows 1*
 - *--encoding 'UTF-8'*
