# Quantium-Virtual-Internship
Virtual Internship at Quantium. Task 1
This is a virtual internship provided by Quantium and Forage.
It consists of data analysis concerning commerce data, in particular the sales of chips.

- The project consits of three tasks

# Code and resources used:
Python Version: 3.9
Packages: pandas, numpy, matplotlib, seaborn, datetime, scipy

# Task 1: Data preparation and customer analytics
- The goal was to analyse customer's transaction data to determine customer purchasing behaviours, and to generate insights and provide commercial recommendations.

# Data cleaning:
- Removed salsa products, so that all products are chips.
- Transformed dates from integer to date-time format.
- Removed outliers that would impair our statistical analysis.
- Extracted the size of each product
- Extracted brand names from product name, combined brands written in multiple ways. 

# Data analysis on customer types:
- Identified whether the sales data by customer type follows a normal distribution.
- Identified the relationship between customer rating and sales.
- Identified the relationship between lifestage and sales.
- Performed statistical analysis (ANOVA, T-test) to determine the significance of observed differences.

# Task 2: Experimentation and uplift testing
Extend analysis from Task 1 to help identify benchmark stores to test the impact of the trial store layouts on customer sales.
- Client selected store number 77, 86 and 88 as trial stores. The goal of this task is to select 1 control store for each trial store.
- Control store will be chosen based on combined similarity magnitude of "Monthly overall sales revenue" and "Monthly number of customers" of the store with the trial stores.
- Groupby each store into monthly groups and remove stores that had less than 12 months of transaction data.
- Each groupby store has columns consisting total sales, number of customers, transactions per customer, chips per customer and the average price per unit.
- Made 2 functions that calculates trial store's correlation of chosen metric to other stores (using pandas DataFrame.corrwith method) and another that calculates normalized distance magnitude of chosen metric to other store 1 - ( (value - min_value) / (max_value - min_value) )
- The above 2 funcitons are used and averaged to compute the magnitude of similartiy for the trial stores based on Total_Sales and Number_of_Customers.
- Highest average score (average of Total_Sales and Number_of_Customers magnitude of similarity) for each trial store is chosen as the control store.
- Next phase is to assess trial store's performance compared to control store's scaled performance (scaled control store's performance to match trial store's). Used t-value to check if each trial and control store's percentage difference is statistically significant during the trial phase compared to the percentage difference during pre-trial phase.

# Task 3: Creating a power-point presentation to present our findings
- Used Pyramid principle with its top to bottom approach to deliver insights to Category Manager
