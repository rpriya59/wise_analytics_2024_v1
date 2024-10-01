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
