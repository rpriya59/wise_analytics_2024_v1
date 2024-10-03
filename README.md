# Data Transformation Overview

This document outlines the data transformations applied to calculate various additional fields for trip data analysis.

## Additional Fields Calculated

1. **Trip Duration**
   - Calculate the duration of each trip in minutes and seconds.

2. **Fare Amount**
   - Calculate the fare amount per mile to analyze price trends.

3. **Flag**
   - Assign a flag value of "High" for trips with unusually high fares or long distances for further investigation.

4. **Total Fare**
   - Calculate the total fare for each trip.

5. **Total Surcharges**
   - Aggregate various surcharge amounts for each trip.

6. **Day/Night Indicator**
   - Determine the time of day for the trip:
     - "Day" if the hour of the trip is between 6 AM and 6 PM.
     - "Night" if the hour of the trip is between 6 PM and 6 AM.

7. **Weekday**
   - Calculate the weekday when the trip was taken:
     - 0 - 'Monday'
     - 1 - 'Tuesday'
     - 2 - 'Wednesday'
     - 3 - 'Thursday'
     - 4 - 'Friday'
     - 5 - 'Saturday'
     - 6 - 'Sunday'

8. **Rush Hour Indicator**
   - Determine if the trip occurred during rush hour:
     - "Yes" if the hour of the trip is between 7 AM and 9 AM or 4 PM and 7 PM.
     - "No" if the hour of the trip is between 9 AM and 4 PM or 7 PM and 7 AM.

9. **Daily Summary**
   - Calculate the daily summary of data for the month of January on the following columns:
     - Total distance covered on all trips for the given day.
     - Total amount earned on the day.
     - Passenger count on the given day.
# Exploratory Data Analysis (EDA) on Cab Trip Data

## Overview

This project performs an exploratory data analysis (EDA) on a dataset containing cab trip records. The analysis focuses on understanding key metrics such as passenger count, average fare, trip hour, and related trends. The insights derived from this analysis can help in making data-driven decisions related to cab services.

## Dataset

The dataset includes the following columns:

- **VendorID**: ID of the cab vendor (int32)
- **tpep_pickup_datetime**: Pickup date and time (timestamp[us])
- **tpep_dropoff_datetime**: Drop-off date and time (timestamp[us])
- **passenger_count**: Number of passengers (int64)
- **trip_distance**: Distance of the trip (double)
- **RatecodeID**: Rate code (int64)
- **store_and_fwd_flag**: Indicates if the trip was stored for future forwarding (string)
- **PULocationID**: Pickup location ID (int32)
- **DOLocationID**: Drop-off location ID (int32)
- **payment_type**: Type of payment (int64)
- **fare_amount**: Base fare amount (double)
- **extra**: Extra charges (double)
- **mta_tax**: MTA tax (double)
- **tip_amount**: Tip amount (double)
- **tolls_amount**: Tolls amount (double)
- **improvement_surcharge**: Improvement surcharge (double)
- **total_amount**: Total fare amount (double)
- **congestion_surcharge**: Congestion surcharge (double)
- **Airport_fee**: Airport fee (double)

## EDA Insights

### Key Metrics Analyzed
1. **Passenger Count**: Distribution of the number of passengers per trip.
2. **Average Fare**: Analysis of average fare amounts across different hours and days.
3. **Trip Hour**: Understanding the distribution of trips by hour of the day.
4. **Pickup Trends**: Insights into peak hours and days for cab pickups.

### Visualizations

1. **Passenger Count Distribution**:
   - A bar chart showing the distribution of passenger counts across trips.
   - Helps identify the most common passenger counts.

2. **Average Fare Amount by Pickup Hour**:
   - A combined bar and line chart displaying the average fare amount and number of pickups per hour.
   - Provides insights into fare trends throughout the day.

## Usage

Follow the instructions below to perform the transformations and load the results into your data analysis system.

The dataset used is `yellow_tripdata_2024-01.parquet`, which can be downloaded from the following link:

[NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

## Instructions

1. **Download the Dataset**: 
   - Download the `yellow_tripdata_2024-01.parquet` file from the link provided above.
   - Store the file in your Google Cloud Storage (GCS) location.

2. **Set File Path**:
   - Modify the `gcs_parquet_file_path` variable in your script to point to the path where you saved the file in GCS.

3. **Configure BigQuery Settings**:
   - Provide your BigQuery `table_id` and `dataset_id` in the script to load the data appropriately.
