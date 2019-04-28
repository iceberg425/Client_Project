# Project 4: Tweet-Based Identification of Power Outages


## Problem Statement

The goal of this project is to improve upon current processes that identify power outages; by leveraging social media to decrease the amount of time it takes for emergency management officials to become aware of an outage, response times can be improved.
 

## Executive Summary
### Background:
Twitter is a widely used social-media platform that allows its users to publicly post 280-character messages (140-characters prior to November 2017) on virtually any topic one can imagine. Many of these messages are simply reports of users' reactions to current events, or user status updates during those events. Accordingly, there are a large number of messages, called tweets, generated when widely disruptive events, including power outages, occur. In theory, many of these messages will be sent out by users very quickly upon their becoming aware of an outage, and thus the tweets may be shared to social media before emergency management officials become aware of the outage.

### Notebooks:
- [01. Data Collection](https://git.generalassemb.ly/iceberg/DSI-Client-Project/blob/master/01_Data_Gathering.ipynb)
- [02. Twitter Data Cleaning, Preprocessing, and EDA](https://git.generalassemb.ly/iceberg/DSI-Client-Project/blob/master/02_Data_Cleaning_Tweets.ipynb)
- [03. Weather/Outage Data Cleaning, Preprocessing, and EDA]()
- [04. Modeling]()

### 1. Data Collection

#### Twitter Data
We collected tweets using [TweetScraper](https://github.com/jonbakerfish/TweetScraper), but it should be noted that we only arrived at this solution after spending about a week trying other techniques without successfully compiling a usable collection of historical tweets.

Here is a brief summary of the issues we encountered:
- *Twitter's free API only allowed access to the seven most recent days of historical tweets. Further access required a costly subscription.*
- *While using the [TwitterScraper](https://github.com/taspinar/twitterscraper) package, we quickly exceeded the maximum number of API requests allowed and were prevented from pulling additional tweets.*
- *Before out access was blocked, TwitterScraper appeared to return 400 tweets per request, but, once we set the tweets in a pandas dataframe, we discovered that each request pulled only 20 unique tweets (repeated 20 times).*

We ran TweetScraper using the query "power outage conedison" and retrieved 4,375 tweets ranging from 2007-07-20 to 2019-04-18. The inclusion of 'conedison' implicitly narrowed the results of our scrape to the New York City area, which proved important since the data did not specify geographical locations of the tweets.

#### Weather Data
Weather data was gathered from Kaggle's [Historic Hourly Weather](https://www.kaggle.com/selfishgene/historical-hourly-weather-data#weather_description.csv) dataset, which includes hourly weather data for New York City from 10/1/2012 to 10/27/2017.

#### Outage Data
Power outage data was gathered from NYC Open Data's [OEM Emergency Notification](https://data.cityofnewyork.us/Public-Safety/OEM-Emergency-Notifications/8vv7-7wx3/data) database, which includes data on official NYC Office of Emergency Management notifications dating back to 2009. Power outage notifications contained the term 'Power Outage' in the *Notification Title* column.

### 2. Twitter Data Cleaning, Preprocessing, and EDA

### 3. Weather and Outage Data Cleaning, Preprocessing, and EDA

### 4. Modeling

## Conclusions and Next Steps


