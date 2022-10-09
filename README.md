# Data Science Salary Estimator/Predictor(2019)
Created a model that estimates data science salaries in US.
Scraped over 1000 job descriptions from glassdoor using python and selenium
Engineered features from the text of each job description to quantify the value companies put on python, excel, aws, and spark.
Used Linear, Lasso, and Random Forest Regressors, optimized the models using GridsearchCV to find the best model.
Built a client facing API using flask
# Tools and Resources Used
Packages: pandas, numpy, sklearn, matplotlib, seaborn, selenium, flask, json, pickle
Scraper Article: https://towardsdatascience.com/selenium-tutorial-scraping-glassdoor-com-in-10-minutes-3d0915c6d905
Flask Productionization: https://towardsdatascience.com/productionize-a-machine-learning-model-with-flask-and-heroku-8201260503d2
# Web Scraping
Scraped the Glassdoor website to get 1000 job postings details. With each job, we got the following:

Job title
Salary Estimate
Job Description
Rating
Company
Location
Company Headquarters
Company Size
Company Founded Date
Type of Ownership
Industry
Sector
Revenue
Competitors
# Data Cleaning
The data was cleaned so that it can be usable for our model. The following changes and variables were made:

Parsed numeric data out of salary
Made columns for employer provided salary and hourly wages
Removed rows without salary
Parsed rating out of company text
Made a new column for company state
Added a column for if the job was at the company’s headquarters
Transformed founded date into age of company
Made columns for if different skills were listed in the job description:
Python
R
Excel
Spark
Column for simplified job title and Seniority
Column for description length
# EDA
The data was plotted and analysed for the distribution, pattern and insights
# Model Building
Firstly, categorical variables were converted into dummy variables.
Three diffeent models were tested
1. Multiple Linear Regression
2. Lasso Regression
3. Random Forest Regression
# Model Performance
Random Forest Regression model performed best with MAE of 11.499015659955258
# Productionization
Flask API endpoint was built was hosted on a local webserver. The API endpoint takes in a request with a list of values from a job listing and returns an estimated salary
