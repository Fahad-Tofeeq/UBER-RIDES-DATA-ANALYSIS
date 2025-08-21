# Uber Rides Data Analysis
## Project Overview
This repository contains a comprehensive data analysis project on a dataset of Uber rides, performed using Python in a Jupyter Lab environment. The project covers data wrangling, data cleansing, data transformation (ETL), and data visualization to uncover insights about ride patterns, purposes, and trip characteristics. The dataset includes 322 Uber trips with details such as start/end dates, locations, miles, and purposes.

# Dataset
### The dataset (UberDataset.csv) includes the following columns:
### START_DATE: Start time of the trip
### END_DATE: End time of the trip
### CATEGORY: Trip category (Business or Personal)
### START: Starting location
### STOP: Ending location
### MILES: Distance traveled (in miles)
### PURPOSE: Purpose of the trip (e.g., Meeting, Meal/Entertain, Customer Visit)
## Key dataset characteristics:
Rows: 322
Missing Values: ~80 in PURPOSE (handled during cleansing)
Date Range: January 1, 2016, to March 5, 2016

# Project Structure
### Notebook: uber_rides_analysis.ipynb - Main Jupyter notebook with all code for data processing and visualization.
### Data: The dataset is embedded as a string in the notebook for reproducibility. Users can replace it with a CSV file if needed.
### Outputs: Visualizations (histograms, pie charts, bar plots, box plots) and summary tables generated within the notebook.

# Methodology
## 1. Data Wrangling and Cleansing
Loaded the dataset from a CSV string using Pandas.
Converted START_DATE and END_DATE to datetime, handling mixed formats (e.g., "01-01-2016" vs. "1/13/2016") with pd.to_datetime(format='mixed', errors='coerce').
Replaced missing/empty PURPOSE values with 'Unknown'.
Checked for duplicates (none found) and outliers (no removal needed; miles range 0.5–310.3 deemed reasonable).
## 2. Data Transformation (ETL)
Extract: Loaded raw data into a Pandas DataFrame.
Transform:
Calculated trip duration in minutes (DURATION_MIN).
Extracted DAY_OF_WEEK and HOUR from START_DATE.
Categorized trips by distance (TRIP_TYPE: Short [0–5 miles], Medium [5–20 miles], Long [>20 miles]).
Load: Created a transformed DataFrame (transformed_df) for analysis. (Note: In a production ETL pipeline, this could be saved to a database or CSV.)

## 3. Exploratory Analysis
Key Metrics:
Total Trips: 322
Total Miles: ~4014.6
Average Miles: 12.47
Business Trips: ~84.5%
By Category:
Business: 272 trips, mean 13.72 miles, total 3731.0 miles
Personal: 50 trips, mean 5.67 miles, total 283.6 miles
By Purpose:
Most common: Meal/Entertain (69 trips), Meeting (68 trips)
Longest average: Customer Visit (37.41 miles, 50.31 minutes)

## 4. Data Visualization
The notebook includes the following visualizations (using Matplotlib and Seaborn):
Pie Chart of Categories: ~84% Business, ~16% Personal.
Bar Plot of Purposes: Meal/Entertain and Meeting dominate.
Box Plot of Miles by Day of Week: Longer trips on weekends (e.g., Saturday).
Bar Plots of Average Miles and Duration by Purpose: Customer Visit has the highest averages.
Trip Type Distribution: ~40% Short, ~40% Medium, ~20% Long.

# Insights
Business trips dominate (~84.5%), with longer average distances and durations.
Customer Visit trips are the longest (mean 37.41 miles, 50.31 minutes).
Most trips occur during work hours (11 AM–5 PM) and are short/medium (80% <20 miles).
Weekends show longer trips, especially on Saturdays.
# Contact
### For questions or contributions, please open an issue or contact [fahadtofeeq1999@gmail.com]

