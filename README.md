# Zomato Ad Performance Analysis - README

## Project Overview
The **Zomato Ad Performance Analysis** project aims to analyze **advertising revenue, CPC trends, and food vs. restaurant ad performance** on Zomato. The dataset is designed to be highly **realistic and India-based**, incorporating **real restaurant names, city-wise branches, and localized food items**. The project is structured to showcase **SQL, Power BI, and statistical analysis skills**, making it suitable for job applications at companies like Zomato, Amazon, and similar data-driven firms.

## Dataset Structure
The dataset consists of multiple **normalized tables** to ensure a well-structured relational database. Below are the core tables and their details:

### **1. Customers Table**
- **Purpose:** Stores customer demographic details and order frequency.
- **Columns:**
  - `customer_id` (Primary Key)
  - `name`
  - `city`
  - `age`
  - `gender`
  - `total_orders`
  - `customer_segment` (e.g., "Frequent Diner," "Occasional User")
  - `last_order_date`

### **2. Restaurants Table**
- **Purpose:** Stores restaurant and branch details, ensuring clear segmentation.
- **Columns:**
  - `restaurant_id` (Primary Key)
  - `restaurant_name`
  - `branch_name` (e.g., "Burger King - Connaught Place")
  - `branch_id` (Coded format: e.g., BK1/4 for 1st Burger King branch out of 4)
  - `city`
  - `cuisine`

### **3. Food Items Table**
- **Purpose:** Stores menu details for each restaurant.
- **Columns:**
  - `food_id` (Primary Key)
  - `restaurant_id` (Foreign Key)
  - `food_name`
  - `food_category`
  - `price`
  - `food_code` (Coded format: e.g., BKF1/10 for 1st item of 10 in Burger King's menu)

### **4. Ads Table**
- **Purpose:** Stores details of food-based and restaurant-based ads.
- **Columns:**
  - `ad_id` (Primary Key)
  - `ad_type` (Food-Based or Restaurant-Based)
  - `ad_category` (e.g., "Discount Ad," "Festival Promo")
  - `season` (e.g., "Diwali Promo," "Summer Special")
  - `total_cost`
  - `start_date`
  - `end_date`

### **5. Ad Clicks Table**
- **Purpose:** Tracks user interactions with ads.
- **Columns:**
  - `click_id` (Primary Key)
  - `ad_id` (Foreign Key)
  - `customer_id` (Foreign Key)
  - `click_time`
  - `device_type`
  - `location`
  - `time_of_day` (e.g., "Morning," "Afternoon")

## Step-by-Step Changes Implemented
1. **Realistic Restaurant Segmentation:**
   - Restaurants have **multiple branches within the same city** (e.g., "Dominos - Andheri," "Dominos - Bandra").
   - Branches are **clearly labeled** with a **coded branch ID** (e.g., BK1/4).
2. **Menu Realism:**
   - **Food items are restaurant-specific**, maintaining authenticity (e.g., "Paneer Makhani Pizza" for Dominos India).
   - **Food item codes** track their position in the restaurant's menu (e.g., BKF1/10).
3. **Enhanced Ad Categorization:**
   - Ads are segmented into **"Discount Ads," "Festival Promotions," "New Launch Ads."**
   - A **seasonality impact column** helps analyze performance trends during events like **Diwali, Holi, and Monsoon.**
4. **Customer Insights:**
   - **Customer segmentation** is introduced (e.g., "Frequent Diner," "Occasional User").
   - **Order frequency tracking** through `total_orders` and `last_order_date`.
5. **Ad Click Behavior Tracking:**
   - `time_of_day` column added to **analyze peak engagement hours** (Morning, Afternoon, Evening, Late Night).

## Next Steps
- **Generate full dataset (~500K+ rows) in MySQL-compatible format**.
- **Perform SQL-based ad performance analysis** (e.g., highest CPC ads, seasonal trends).
- **Visualize insights in Power BI** (ad effectiveness, peak engagement times, customer behavior patterns).

This README will be continuously updated as we progress through the project.

