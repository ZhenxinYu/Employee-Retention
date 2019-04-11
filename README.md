# Employee Retension


## 1. Objective
* Using python library (selenium and beautiful soup) to craw the review from different websites.
* Organize data collected and preprocess the data
* Perform analytic on the data collected and visualize the result
* Train model to predict feature and find vital pattern the is the most impactful.

## 2.Prerequisite
**Crawler**  
1. [Python3](https://www.python.org/downloads/)
2. [Pandas](https://pypi.org/project/pandas/)
3. [Selenium](https://selenium-python.readthedocs.io/)  
4. [BeautifulSoup (bs4)](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)  
**Analysis**  
5. [numpy](http://www.numpy.org/)
6. [matplotlib](https://matplotlib.org/)
7. [nltk](https://www.nltk.org/)
8. [wordcloud](https://github.com/amueller/word_cloud)  
9. [Pillow](https://pillow.readthedocs.io/en/stable/)   
**Optional**   
10. [tqdm](https://github.com/tqdm/tqdm)


## 3. Data Source

### 3.1. Glassdoor
**Glassdoor** provides reviews of current and former employee for many company.   
<img src="https://hiretulane.tulane.edu/sites/hiretulane.tulane.edu/files/logo-glassdoor-color.087f3470.png" alt="Glassdoor Icon" width="500"/>

### 3.2. Indeed
**Indeed** provides reviews of current and former employee for many company as well.  
<img src="https://www.lifewire.com/thmb/PLDQoVGvvEeic5VObpOg7DvwTEA=/768x0/filters:no_upscale():max_bytes(150000):strip_icc()/indeed-logo-RGB-tagline-598f6af7396e5a00105fd927.jpg" alt="Indeed Icon" width="500"/>


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
