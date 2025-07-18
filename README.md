# Amazon Product Review Analysis
## Introduction
In this project, being my first project as a beginner data analyst, I analyzed Amazon product reviews, leveraging Excel to identify key trends in pricing, ratings, and customer behavior. The analysis showcases my proficiency in data analysis and provides actionable insights into consumer preferences and market dynamics.
## Project Description
A comprehensive analysis of 1,465 Amazon products spanning multiple categories uncovered valuable trends and patterns in pricing strategies, discount offerings, customer ratings, and engagement metrics. This in-depth examination provided actionable insights into consumer behavior, market dynamics, and competitive landscapes, enabling data-driven decision-making and informed business strategies.

## Dataset Description
-  Source: The dataset were scraped from Amazon product pages
-  Number of Records: 1,465 rows
-  Number of Fields: 16
-  [Access the raw data here] ()

## Analysis Tasks Achieved

1. Average discount percentage by category
2. Number of products by category
3. Total number of reviews by category
4.  Products with the highest average ratings
5. Average actual price vs the discounted price by category
6. Products with highest number of reviews
7. Products with discount of 50% or more
8. Distribution of product ratings 
9. Total potential revenue by category
10. Number of unique products per price range bucket
11. How rating relate to the level of discount
12. Number of products with less than 1,000 reviews
13. Product categories with the highest discounts
14. Top 5 products in terms of rating and number of reviews combined

## Analytic Tool
Microsoft Excel 2019 [Download Here](https://microsoft-office-2019.en.uptodown.com/windows)

## Data Cleaning
### Step-by-Step Process
-  ***Identification and Removal of Duplicates***: 114 duplicates in `product_id` were identified and removed. This leaves the number of records at 1,351 unique products.
-  ***Removal of Unnecessary Columns***: Columns/fields that were not needed for the analysis were rempoved to make the dataset more manageable and easier to analyse, improves performance, enhances focus on relevant features and variables, minimizes noise and simplify data visualization.
-  ***Data Validation***: The filter tool was used to validate data type consistency of the values in each of the columns.
      -  The `actual_price` column had a value **1,39,900** which was corrected to **139,000**. The data type was changed to accounting and the currency symbol **"₹"** was assigned to the column.
      -  The `rating` column had a value **|** which was replaced with a zero.
      -  The `rating_count` column had two cells that were blank. Each blank cell was assigned zero.
  
  
