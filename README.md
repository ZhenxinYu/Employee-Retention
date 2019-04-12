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
### 4.1. Reviews Crawler
1. Setup selenium to open the browser. Here I used [chrome](http://chromedriver.chromium.org/) as my browser. For glassdor, they require user to login before viewing the reviews, so remeber create your own account and login before start crwaling.
2. There are several ways to locate the elements that contain target information. For glassdoor, I used function in selenium and find the elements by looking xpath. For Indeed, I used beautifulsoup to process the html content I got from request library. Then, find the element by tag name and other attributes.
3. To iterated through all the pages, I implement two different ways to achieve. For Indeed, By looking at the last page number, I can save url for all the reviews and go through them one by one. For glassdoor, I try to find the next button and keep crwaling unitl the next button is disabled and break the loop.

### 4.2. Reviews Analysis
To analyze the reviews, I tried to cut in the problems from different perspective. Here, I am not only interesed in how all the employee in google think but also how engineer in google think. Therefore, I compare all the result for the entire dataset I collected and the subset of engineers' reviews.
1. Looking into the histogram of the ratings, we can see how employee rate Google generally.  
2. Utilizing the features glassdoor collected, we are able to see most people recommends other to work at Google and whats the most common advantages they recognized.
3. Next, I tried to visualized every one's reviews into wordcloud. To fully reflect the reviews, the wordcloud not only account on the words in the reviews but also the bigram and trigram. Also, I tried to used inverse document frequency to normalize their importance.
4. I build a predictive model using the word in the reviews to predict the rating. Then, by looking the weight for each word, I tried to find out the most impactful words in the reviews to see which thing is causing the most positive effect to the employee and which has the most negative effect. However, the model may not always relect the stable result due to randomized initialization.
5. Last but not least, I tried to inspect how the rating for google changed over time and how are the structure of the company is changing.

## 5. Result
![result1](img/0001.jpg)
![result2](img/0002.jpg)
