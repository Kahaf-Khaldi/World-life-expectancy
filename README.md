World Life Expectancy (SQL) — Data Cleaning & EDA
A comprehensive SQL project exploring global life expectancy trends, development status differences, GDP/BMI relationships, and adult mortality over time. This repository focuses on robust data cleaning and exploratory analysis using MySQL.

📊 Project Overview
This project prepares a world life expectancy dataset for analysis and answers practical questions around trends, socioeconomic relationships, and cross-country differences.

Key Questions Addressed
How much did life expectancy change for each country over the observed period?

What is the global trend in average life expectancy by year?

How does average GDP relate to average life expectancy across countries?

How do Developed vs Developing countries differ in average life expectancy?

What patterns emerge between BMI and life expectancy?

How do rolling totals of adult mortality evolve over time within each country?

Repository Structure
sql/

world-life-expectancy.sql — Data Cleaning

EDA-of-world-life-expectancy.sql — Exploratory Data Analysis

data/

world_life_expectancy.csv — Place your dataset here

README.md

🧰 What’s Included
Data Cleaning

Identify and remove duplicate records using Country + Year

Backfill missing development Status consistently within each country

Impute missing life expectancy values using neighbor-year averages

Ensure consistent handling of blanks vs NULLs

Exploratory Data Analysis

Per-country life expectancy change (min vs max and total increase)

Global yearly averages of life expectancy

Country-level comparisons: average life expectancy vs average GDP

GDP cohort comparison (e.g., threshold of 1500) for life expectancy

Developed vs Developing comparisons: averages and distinct country counts

BMI vs life expectancy relationships

Rolling sums of adult mortality over time by country

Requirements
MySQL 8.0+ (window functions required)

A database table named “world_life_expectancy” with the following columns:

Row_ID (unique identifier)

Country

Year

Status (Developed/Developing)

Life expectancy

GDP

BMI

Adult Mortality

Notes:

Columns that include spaces should be referenced with backticks in SQL.

If the dataset stores missing values as empty strings rather than NULL, adjust checks accordingly.

🚀 How to Use
Add the dataset file to the data directory and import it into a MySQL database as “world_life_expectancy”.

Run the Data Cleaning script to:

Remove duplicates based on Country + Year

Fill missing Status using existing values within the same country

Impute missing Life expectancy using averages of adjacent years

Run the EDA script to:

Generate global and per-country trend insights

Compare GDP cohorts and development status groups

Analyze BMI relationships and rolling adult mortality

Customize thresholds and conditions (e.g., GDP cutoff) to suit analytical goals.

Key Insights & Outcomes
Clean, deduplicated, and analysis-ready dataset

Quantified life expectancy increases by country

Year-over-year global life expectancy trend

Relationships between GDP/BMI and life expectancy

Clear comparisons between Developed and Developing groups

Rolling adult mortality indicators by country
