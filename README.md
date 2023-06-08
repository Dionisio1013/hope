# Yelp KPI Web Application & Sentiment Analysis

Here is a link to my [web application!](https://dionisio1013-hope-test-bdpevq.streamlit.app/)
This project is a part of the [Yelp Dataset](https://www.yelp.com/dataset).

#### -- Project Status: [Active/In Progress]

## Project Intro/Objective
Yelp is a crowd-source app that allows users to critique restaurants by providing
a star rating from 1-5 and a message argumenting their reasons. It acts as a way for 
restaurants to market their popularity, have business-customer interaction, set standards expectations
and to be able to learn from customer criticism. 

Goals of project
1) Using NLP analyze the text of certain ratings from Yelp reviews.
2) Gain business sense of using yelp data to drive data driven decision making.
3) Develop a web application for stakeholders to visualize KPI of their restaurants.

## Business Applications of project
**Market Segmentaiton** - By analyzing the data and keywords it's important for restaurant owners to focus on these characteristics when segmenting towards an audience
Main focuses of restaurants
1) Food (Specialities)
2) Service (customer oriented)
3) Culture Identity - Korean, Mexican, Italian, etc
4) Time of day - Breakfast, Lunch, Dinner

**Self awareness of a company** - KPI allows for restaurants owners to manage their restaurants and to benchmark performances from Web Application KPI.
Eg. Owner of a Korean Barbaque chain has 5 restaurants scattered around California

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

develop a schema validation, and then transfer the data from collection to csv for analytics and for web application. 

## 2) Analyzing the Data & Key Findings (In Progress)
No Sentiment reviews:
Most frequent keywords (top 5) of restaurants is the name of the food served, culture.

Positive reviews:
Key findings is the most popular word for positive ratings is: Good and Great

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
