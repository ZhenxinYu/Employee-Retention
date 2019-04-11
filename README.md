<center> Employee Retension </center>


## 1. Objective
* Scrape weather data from NOAA
* Fetch FIPS and county information from Area and Census Clock API
* Use Google Map API to match the station with county
* Merge the weather data and geographical data
* Analyze weather data with gun-crime data

## 2.Prerequisite
1. [Python3](https://www.python.org/downloads/)
2. [Pandas](https://pypi.org/project/pandas/)
3. [Google Map API](https://github.com/googlemaps/google-maps-services-python)  
**Optional**
4. [tqdm](https://github.com/tqdm/tqdm)
5. [Rstudio](https://www.rstudio.com/)


## 3. Data Source

### 3.1. Weather Data
**National Oceanic and Atmospheric Administration (NOAA)** provides current and history climate data via web request.  
[NCDC Web Services Documentation](https://www.ncdc.noaa.gov/cdo-web/webservices/v2)  
![NOAA Icon](https://nsd.rdc.noaa.gov/images/NOAA_emblem.png)  

### 3.2. Geograpchical Data
**Federal Communications Commission (FCC)** provides FIPS code and county information.  
[Area and Census Block API](https://geo.fcc.gov/api/census/)  
![FCC Icon](https://www.duluthnewstribune.com/sites/default/files/styles/16x9_620/public/fieldimages/1/1024/fcclogo.jpg?itok=G_A0TSxp)  

**Google Maps** provide python library for user to query geographical data through Internet.  
[Google Map API Documentation](https://developers.google.com/maps/documentation)  
![Google Map API Icon](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQEVZ6BvNVnDepmtqdBRr3kqMN6nGZ4sgEPm6KX7kvN7u81YXjt)


## 4. Method
### 4.1. Weather_Scraper.ipynb
1. Use [NCDC Web Services](https://www.ncdc.noaa.gov/cdo-web/webservices/v2) to get all the [station](https://www.ncdc.noaa.gov/cdo-web/webservices/v2#stations) and [county](https://www.ncdc.noaa.gov/cdo-web/webservices/v2#locations) information.
2. Query the weather data within given time range (2006-2018 in my case) given location id (county id).
3. Store all the result into correspond county subdirectory. 

### 4.2. weather gather & process.ipynb
4. Other way to get NCDC weather data is download through ftp server. (ftp://ftp.ncdc.noaa.gov/pub/data/ghcn/daily/by_year/)
5. Merge the weather data with station infromation
6. Use FCC API to get the FIPS code and county name
7. Use Google Map API to get the zipcode
