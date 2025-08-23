World Life Expectancy (SQL) — Project README
A concise, copy‑paste ready README describing a SQL project for cleaning and analyzing a World Life Expectancy dataset. This version intentionally avoids code blocks.

Overview
This repository provides a complete, SQL‑only workflow to:

Clean a raw world life expectancy dataset (deduplicate, standardize, and impute key fields)

Explore trends and relationships across life expectancy, GDP, BMI, and adult mortality

It includes two SQL scripts:

Data Cleaning: world-life-expectancy.sql

Exploratory Data Analysis (EDA): EDA-of-world-life-expectancy.sql

Key Features
Duplicate detection and removal using a country + year business key

Filling missing development Status per country (Developed/Developing)

Imputing missing life expectancy values using neighbor-year averages

Trend analysis of life expectancy over time

Comparisons of life expectancy by GDP, BMI, and development status

Rolling adult mortality summaries by country

Repository Structure
sql/

world-life-expectancy.sql (Data Cleaning)

EDA-of-world-life-expectancy.sql (EDA)

data/

world_life_expectancy.csv (add your dataset here)

README.md

Requirements
MySQL 8.0 or newer (window functions required)

A database table named “world_life_expectancy” with columns:

Row_ID (unique identifier)

Country

Year

Status (Developed/Developing)

Life expectancy

GDP

BMI

Adult Mortality

Notes:

Columns with spaces should be referenced using backticks in SQL.

If the dataset stores missing values as empty strings instead of NULL, adjust conditions accordingly.

How It Works
Data Cleaning

Inspect and verify raw data structure

Identify duplicate records by country and year

Remove exact duplicates while preserving one canonical record

Backfill missing Status per country based on existing entries

Impute missing life expectancy by averaging the previous and next year within the same country

EDA

Calculate per‑country change in life expectancy across the observed period

Compute global average life expectancy per year to visualize trend

Compare country‑level average life expectancy against average GDP

Split cohorts by GDP threshold (e.g., 1500) to compare life expectancy

Summarize life expectancy by development Status and count distinct countries

Explore BMI and life expectancy at the country level

Produce rolling sums of adult mortality per country over time

Usage
Place the dataset CSV in the data directory and import it into a MySQL database as “world_life_expectancy”.

Run the Data Cleaning script first to remove duplicates and fill missing values.

Run the EDA script to generate analyses and insights.

Adjust thresholds (e.g., GDP split) and filters to suit specific research questions.

Expected Outcomes
A cleaned, deduplicated table suitable for downstream analysis

Quantified increase in life expectancy by country

Year‑over‑year global trend in life expectancy

Insights into relationships between GDP, BMI, and life expectancy

Comparative metrics for Developed vs Developing countries

Rolling indicators of adult mortality across time
