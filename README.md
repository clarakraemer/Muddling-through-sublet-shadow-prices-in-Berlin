# Muddling-through-Berlins-sublet-shadow-prices

This project maps room prices in Berlin from WG-Gesucht and compares them with the BAföG housing rate: Since the fall semester 2019/2020, students in Berlin with full BAföG entitlement receive 861€ per month from the government. In addition to the 427€ for basic needs and 109€ for the statutory health insurance, students receive 325€ for housing costs. Comparing room prices on WG-Gesucht to this amount highlights how high housing costs for students have become in contrast to what the government deems reasonable, partly because flatshare rooms posted on WG-Gesucht find ways to circumvent housing price regulations from the city, such as the recently passed rent price cap. 
To this end, we scrape room postings from the beginning of the Fall Semester 2020 (October-November) in Berlin, match their addresses with polygons and map the resulting dataframe as a Berlin heatmap in relation to how much higher/lower room prices are comapred to the BAföG housing rate.


## Step 1: Building a web scraper for the website WG-Gesucht 

As a first step for the project, we scraped the room price, number of roommates, district, street and house numer of room postings in Berlin. In order to avoid needing to click on each posting with the Selenium package, we only scraped the available information from the overview pages using the BeautifulSoup package. In total, we scraped ~2400 room postings between October and November. 


## Step 2: Data cleaning

After scraping the room posting information, we cleaned the data as much of the scraped information still had undesired html content or was not given in a standardized way. 

## Step 3: Geocoding 

Then we created an account for the Google Maps Platform to use the free credit on the generated API-key to geocode (convert addresses into earth coordinates) our data. We did this by building a function that creates the fitting url for each of our addresses to request the geo-information on an address from the API and extracts only the longitude and latitude data points. Then, we used this function on our dataset. 

## Step 4: Visualisation (MAIN FILE TO RUN)

