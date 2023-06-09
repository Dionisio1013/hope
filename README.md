# Yelp KPI Web Application & Sentiment Analysis

Here is a link to my [web application!](https://dionisio1013-hope-test-bdpevq.streamlit.app/)
This project is part of the [Yelp Dataset](https://www.yelp.com/dataset).

#### -- Project Status: [Active/In Progress]

## Project Intro/Objective
Yelp is a crowd-sourced app that allows users to critique restaurants by providing a star rating from 1-5 and a message arguing their reasons. It acts as a platform for restaurants to market their popularity, facilitate business-customer interaction, set standard expectations, and learn from customer criticism.

Goals of project
1) Using NLP analyze the text of certain ratings from Yelp reviews.
2) Gain business sense of using yelp data to drive data driven decision making.
3) Develop a web application for stakeholders to visualize KPI of their restaurants.

## Business Applications of project
**Market Segmentaiton** - By analyzing the data and keywords it's important for restaurant owners to focus on these characteristics when segmenting towards a specific audience.
Main focuses of restaurants:

1) Food (Specialities)
2) Service (Customer oriented)
3) Culture Identity - Korean, Mexican, Italian, etc
4) Time of day - Breakfast, Lunch, Dinner

Number 1) and 2) serves as a baseline/foundation for a successful restaurant. Number 3) and 4) serves as more of the restaurant's brand image, identity, and distinct characteristics that sets apart from other restaurants

**Self awareness of a company** - KPI allows for restaurant owners to manage their restaurant(s) and to benchmark performances thorugh customer reviews KPI metrics and Sentiment Analysis.
Eg. Owner of a Korean Barbaque chain has 5 restaurants scattered around California.
* Owner can easly access each of the five restaurants from different cities.
* Can identify which restaurant has the best rating and most reviews.
* Similarities & Differences of reviews from each restaurant.
* Based on reading reviews and sentiment analysis, owner can deduce issues within the restaurant whether it be personel, food, service issue. 

### Methods Used
* Machine Learning
* Data Visualization
* NLP
* etc.

### Technologies
* Python
* MongoDB
* Packages: Pandas, Numpy, Nltk, Textblob, Matplot, Plotly, WordCloud
* Jupyter
* Streamlit
* etc. 

# Project Description

## 1) Getting the Data - from collections.py
Started off by downloading the data from the Yelps open database.

yelp_academic_dataset_business.json
- Business_id
- name
- address
- city
- state
- latitude
- longitude
- stars
- review_count
- attributes
- categories

yelp_academic_dataset_review.json
- business_id
- text
- review_rating

Goal
1) Connect to MongoDB client
2) Extract data from Yelp JSON scripts and append into two 2-D arrays, Business & Reviews
3) Create empty two collections and apply schema validation 
4) Insert Business and Review documents into their collections
5) Convert from Collection to DataFrame
6) Join both DataFrames via business_id
7) return Dataframe to CSV for Data Exploration

For the sake of runtime and size of the Yelp dataset (Over 6,990,280 million records and 150,346 businesses), I've extracted only 100 businesses from the JSON script and joined it's customer reviews to them.

The total shape of the dataframe is (12137,12)
There are twleve columns and 12,137 observations


## 2) Analyzing the Data & Key Findings (In Progress)

**Key Features:**
The main feature that we are mainly looking into is Text which consists of an entire passage of the customer's review. and its relationship with our featured engineered variable: Sentiment
* Text
* Customer_rating
* Emotion/Sentiment (Featured Engineered)

**Preprocessing data**
To use NLP techniques we generally want to work with data that is tokenized, cleaned and standardized.
* Lowercased entire text
* Removed stop words
* Removed all punctuations
* Tokenizing (splitting each word of a sentence to it's own token)

**Feature Engineering**
Added a new feature where customer reviews that is rated 3,4,5 is "Positive" sentiment and 1,2 is "Negative" sentiment.

Analysis

No Sentiment reviews:
Most frequent keywords (top 5) of restaurants is the name of the food served, culture.

Positive reviews:
The most popular adjectives used for positive ratings is: "Good" and "Great". The words largely assosiated with these adjectives are:
* Place 
* Food
* Service
* Time

Negative reviews:

## 3) Building the web application
Built using streamlit. I was able to create a web application that showcases KPIs of restaurants. It contains information regarding 
a description of the business, sentiment analytics of words from customers and a place to access customer reviews of.

Description of restaurant
- Name and common hashtags
- Opening hours
- Address and Visual Location of Restaurant
- Total Reviews and Count of Positive and Negative Ratings

Sentiment Analytics
- Reviews most common keywords of customer ratings
- Most common adjectives from positive ratings
- Most common adjectives from negative ratings
- Word web to see which adjective links to what noun

Customer Reviews
- Slider that filters customer review ratings from 1-5
- Displays the customer's review ratings where you can double click to expand. 

## Getting Started

1. Web Application is [here](https://dionisio1013-hope-test-bdpevq.streamlit.app/).
2. Raw Data that has been used is called yelp20Revampedbusiness.csv & yelp40Revampedbusiness.csv.
3. Data processing/transformation scripts are being kept [here](Repo folder containing data processing scripts/notebooks)
4. Represents the pipeline from JSON to CSV with data of business,
5. yelpanalytics.py represents analytical findings from the yelp Data
6. test.py represents webapplication
