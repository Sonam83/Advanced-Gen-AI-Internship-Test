# Advanced-Gen-AI-Internship-Test

# Food Orders Data Analysis

## Overview
This repository contains a data analysis project based on food orders. The analysis combines multiple datasets (`orders.csv`, `users.json`, and `restaurants.sql`) to generate insights on user behavior, restaurant performance, cuisine trends, and revenue patterns.  

The project focuses on **merging datasets**, calculating **total and average order values**, and identifying **top-performing restaurants, cuisines, and cities**.

---

## Datasets

1. **orders.csv**  
   - Contains order-level information including `order_id`, `user_id`, `restaurant_id`, `total_amount`, and `order_date`.  
   - Key for joining with users: `user_id`  
   - Key for joining with restaurants: `restaurant_id`

2. **users.json**  
   - Contains user information such as `user_id`, `membership_type` (Gold, Regular), `city`, and other personal details.  
   - Key for joining with orders: `user_id`  

3. **restaurants.sql**  
   - Contains restaurant details such as `restaurant_id`, `cuisine`, `rating`, `city`, and other attributes.  
   - Key for joining with orders: `restaurant_id`  

---

## Project Objectives

- Merge multiple datasets using **Pandas `merge()` function** to combine order, user, and restaurant information.  
- Analyze **user behavior** including:
  - Total orders placed by Gold members
  - Average order value for Gold members
  - Number of distinct users placing orders  
- Analyze **restaurant performance** including:
  - Restaurants with highest average order value (with conditions on order count)
  - Restaurant rating ranges generating highest revenue  
- Analyze **cuisine and city trends** including:
  - Top revenue cities and cuisines
  - Cuisine with lowest number of restaurants but significant revenue
  - Revenue patterns by membership type and cuisine combinations
- Time-based analysis:
  - Total revenue by quarter  
  - Orders and revenue distribution over time  

---

## Methodology

1. **Data Loading**  
   - `orders.csv` loaded using `pandas.read_csv()`  
   - `users.json` loaded using `pandas.read_json()`  
   - `restaurants.sql` loaded into a DataFrame using `sqlite3` or other SQL connectors  

2. **Data Merging**  
   - `orders` merged with `users` on `user_id` (LEFT JOIN)  
   - `orders` merged with `restaurants` on `restaurant_id` (LEFT JOIN)  
   - Missing values after join appear as `NaN`  

3. **Data Analysis & Aggregation**  
   - Used **groupby**, **agg**, and **sum/mean/nunique** functions in Pandas  
   - Calculated metrics like **total revenue**, **average order value**, **distinct users**, and **order counts**  
   - Filtered by conditions such as membership type, city, restaurant rating, and order count  

4. **Insights Generated**  
   - Top revenue cities and cuisines  
   - Highest average order value restaurants under specific conditions  
   - Revenue patterns by membership type and food type  
   - Seasonal trends based on quarterly revenue  

---

## Key Functions Used

- `pandas.read_csv()`, `pandas.read_json()`, `pd.read_sql()`  
- `merge()` for joining datasets  
- `groupby()` and `agg()` for aggregation  
- `sum()`, `mean()`, `count()`, `nunique()` for metrics  
- `.loc[]` and `.query()` for filtering data  
- `.dt` accessor for time-based features (quarters, months)  

---

## How to Run

1. Clone this repository:
```bash
git clone <your-repo-url>
