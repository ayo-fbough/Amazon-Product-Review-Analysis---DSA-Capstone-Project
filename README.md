# Amazon Product Review Analysis
## Introduction
In this project, being my first project as a beginner data analyst, I analyzed Amazon product reviews, leveraging Excel to identify key trends in pricing, ratings, and customer behavior. The analysis showcases my proficiency in data analysis and provides actionable insights into consumer preferences and market dynamics.
## Project Description
A comprehensive analysis of 1,465 Amazon products spanning multiple categories uncovered valuable trends and patterns in pricing strategies, discount offerings, customer ratings, and engagement metrics. This in-depth examination provided actionable insights into consumer behavior, market dynamics, and competitive landscapes, enabling data-driven decision-making and informed business strategies.

## Dataset Description
-  Source: The dataset were scraped from Amazon product pages
-  Number of Records: 1,465 rows
-  Number of Fields: 16
-  [Access the raw data here](https://github.com/ayo-fbough/Amazon-Product-Review-Analysis---DSA-Capstone-Project/blob/main/Amazon%20Product%20Review%20Analysis.xlsx)

## Exploratory Data Analysis (EDA)

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
- [Microsoft Excel 2019](https://microsoft-office-2019.en.uptodown.com/windows) for the data cleaning and wrangling.
-  Skills Applied:
  
        - Data cleaning and formatting
        -  Pivot Tables & Charts
        -  Conditional formatting
        -  Dashboard creation


## Data Cleaning
### Step-by-Step Process
-  ***Identification and Removal of Duplicates***: 114 duplicates in `product_id` were identified and removed. This leaves the number of records at 1,351 unique products.
-  ***Removal of Unnecessary Columns***: Columns/fields that were not needed for the analysis were rempoved to make the dataset more manageable and easier to analyse, improves performance, enhances focus on relevant features and variables, minimizes noise and simplify data visualization.
-  ***Data Validation***: The filter tool was used to validate data type consistency of the values in each of the columns.
      -  The `actual_price` column had a value **1,39,900** which was corrected to **139,000**. The data type was changed to accounting and the currency symbol **"₹"** was assigned to the column.
      -  The `rating` column had a value **|** which was replaced with a zero.
      -  The `rating_count` column had two cells that were blank. Each blank cell was assigned zero.
-  ***Creation of Subcategory***: The category is multi-level in nature. Thus, it was splitted into subcategory to ease analysis and visualisation, using the **Text to Column** tool.

## Analysis
  ### Calculated Columns and Formulas
  -  **`Total_Potential_Revenue`**: The values of this field were derieved by the product of `actual_price` and `rating_count`
  -  **`Price_Range_Bucket`**`: The values of this filed were derieved from condition sets from the `discounted_price`
    
                    =IF(I60<1000,"<₹1000",IF(OR(I60=1000,I60<2000),"<₹2000",IF(OR(I60=2000,I60<3000),"<₹3000",IF(OR(I60=3000,I60<4000),"<₹4000",IF(OR(I60=4000,I60<5000),"<₹5000",IF(OR(I60=5000,I60<6000),"<₹6000",IF(OR(I60=6000,I60<7000),"<₹7000",IF(OR(I60=7000,I60<8000),"<₹8000",IF(OR(I60=8000,I60<9000),"<₹9000",IF(OR(I60=9000,I60<10000),"<₹10000",">₹10000"))))))))))
     
  -  **`Discount_Range_Bucket`**: The values of this field were derieved from conditions set to categorise `discount_percentage` for simplified analysis
    
                 =L2<=40%,"31-40%",IF(L2<=50%,"41-50%",IF(L2<=60%,"51-60%",IF(L2<=70%,"61-70%",IF(L2<=80%,"71-80%",IF(L2<=90%,"81-90%","91"-100%)))))))))

  -  **`>=50% Discount_Percentage`**: The values for this field were obtained by setting conditions for `discount_[ercentage` to determine vales that are equal to or greater than 50%.

                 =IF(L2>=50%,"Yes","No")

### Pivot Table
The pivot table facilitates the summarization and exploration of the dataset quickly and interactively. Pivot tables were utilized to efficiently analyze the data, allowing insights to be drawn by organizing and comparing key factors such as product categories, pricing tiers, discount rates, and customer engagement indicators

## Visualisation
The dataset was presented through an interactive dashboard featuring a variety of visualizations, including bar charts, clustered columns, line graphs, and KPI cards to effectively highlight key insights.

## Insights Drawn From the Analysis

- **Number of Products with ≥50% Discount**: Over 49% (662 out of 1351) of the products are being heavily discounted. This may suggest:
    -  Overstock or clearance strategies
    -  Attempts to boost visibility or sales velocity
    -  High competition in price-sensitive categories

Implication: Discounting is being used aggressively. This may impact profit margins if not carefully managed.

-  **Number of Products with < 1,000 Reviews**:	Roughly 23% of products have very low engagement (<1,000 reviews).

Implication: These products may suffer from low visibility or traffic and weak marketing or poor product-market fit

-  **Product Category Distribution**: Home and Kitchen, Health and Personal Carem Electronics and Office products are the major product category. This shows that purchases are heavily reliant on Home & Kitchen, Health & Personal Care, and Electronics. While this portrays the risk of overdependence on a few categories, it equally shows the area of potential concentration. Health & Personal Care and Electronics do not only have a high number of products but also strong review volumes, showing strong customer interest and performance.

-  **Product Rating Distribution**

    -  Ratings cluster heavily between 3.8 and 4.4.
    -  Very few products rated below 3.5 or above 4.8.
    -  Only a handful of products achieved 5-star ratings.
 
  This indicates generally positive customer sentiment, but also that most products are not seen as *“outstanding.”* There may be room for product or service enhancement.

## Conclusions

-  Discounts drive visibility: Over half of all products with deep discounts (≥50%) appear across categories with strong review volumes.

-  Electronics dominate revenue and engagement: Despite stiff competition, Electronics have the highest number of reviews and potential revenue.

-  High ratings are achievable: Top products consistently receive near-perfect scores, showing that quality and satisfaction can go hand-in-hand.
