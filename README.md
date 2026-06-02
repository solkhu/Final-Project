# Assignment 4 de Engenharia de Dados

**Objective: Clean and process a dirty Pima Indians Diabetes dataset for ingestion and EDA.**

## Data Wrangling
### Steps taken:
1. Loaded semicolon separated dirty csv from course repository
2. Dropped unnecessary `Unnamed: 0` and `Index` columns
3. Showed descriptive statistics
4. Removed trailing whitespaces from column names
5. Standardized categorical values and replaced unclear "missing values" for actual nulls
6. Converted categorical columns like `Age, Glucose, Insulin` and `Body Mass Index` to numerical
7. Replaced numerical and categorical missing values with the median and `unknown` respectively
8. Dropped duplicated rows
9. Verified if numerical outliers exist
10. Exported cleaned dataframe as csv

## Pymongo Ingestion
### Steps taken:
1. Defined container access configuration witth new database
2. Created classes for MongoDB connection management and CRUD operations
3. Defined functions to map csv rows to a MongoDB document and insert them into database
4. Tested connection response
5. Tested ingestion with 10 csv rows
6. Ingested entire clean csv into database

## Exploratory Data Analysis
### Steps taken:
1. Imported classes from ingestion notebook
2. Established configuration, reconnected to database
3. Loaded collection as dataframe
4. Showed descriptive statistics
5. Standardized outliers in `Age` column (expected values are between 21 and 81)
6. Replaced negative values in numerical columns with the median
7. Replaced `unknown` value in categorical columns with null, then with the mode
8. Changed `routine` value rows in `Care Path` column to `routine follow-up`, following the dataset dictionary
9. Standardized `Patient Segment` values (`Adult, Senior`) based on `Age` column

## Files

This repository contains the `rsc` folder with 3 notebooks for each of the main steps above, a `.gitignore` file, the `docker-compose.yml` file, and this `README.md` file.
