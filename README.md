##World Life Expectancy (SQL) — Data Cleaning & EDA
A SQL-only project that prepares and analyzes a global life expectancy dataset to uncover country-level trends, global patterns, GDP/BMI relationships, and adult mortality dynamics.

#Project Overview
This repository contains a complete workflow to:

Clean a raw life expectancy dataset (remove duplicates, fill missing values, standardize fields)

Perform exploratory analysis across countries and years

Compare Developed vs Developing groups and GDP cohorts

Examine BMI relationships and rolling adult mortality indicators

Key Questions
How much did life expectancy change for each country across the observed period?

What is the global trend in average life expectancy by year?

How does average GDP relate to average life expectancy across countries?

How do Developed vs Developing countries differ in life expectancy?

What patterns emerge between BMI and life expectancy?

How do rolling totals of adult mortality evolve over time within each country?

Dataset
Table: world_life_expectancy

Fields: Row_ID, Country, Year, Status (Developed/Developing), Life expectancy, GDP, BMI, Adult Mortality

Notes:

Columns with spaces (e.g., Life expectancy) should be referenced with backticks in SQL.

Some raw files store missing values as empty strings instead of NULL.

Add dataset source, coverage period, and license here.

Repository Structure
sql/

world-life-expectancy.sql — Data Cleaning

EDA-of-world-life-expectancy.sql — Exploratory Data Analysis

data/

world_life_expectancy.csv — Place the dataset here

README.md

Data Cleaning & Preparation
Identified and removed duplicate records using Country + Year as the business key.

Filled missing Status values within each country using existing labels.

Imputed missing Life expectancy values by averaging adjacent years for the same country.

Standardized handling of blanks vs NULLs to ensure consistent analysis.

Exploratory Data Analysis
Per-country life expectancy change (min, max, and total increase over the period).

Global yearly averages of life expectancy.

Country-level comparison: average life expectancy vs average GDP.

GDP cohort comparison (e.g., threshold 1500) for life expectancy contrasts.

Developed vs Developing summaries: average life expectancy and distinct country counts.

BMI vs life expectancy relationships by country.

Rolling sums of Adult Mortality per country over time.

Requirements
MySQL 8.0+ (window functions required)

Correct column names and compatible data types as listed in the Dataset section

How to Use
Import the CSV into a MySQL database table named world_life_expectancy.

Run the Data Cleaning script to remove duplicates and fill missing values.

Run the EDA script to generate trend, cohort, and rolling-metric analyses.

Adjust thresholds (e.g., GDP split) and filters to match analysis goals.

Expected Outcomes
Cleaned, deduplicated, analysis-ready dataset

Quantified life expectancy increases by country

Year-over-year global trendline

Insights into GDP–life expectancy and BMI–life expectancy relationships

Clear comparisons between Developed and Developing groups

Rolling adult mortality indicators by country
