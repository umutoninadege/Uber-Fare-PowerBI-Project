# Uber Fare Power BI Data Analysis Project

This repository contains a comprehensive Power BI data analysis project focused on understanding Uber trip data. The project involves a complete workflow from raw data import, cleaning, and transformation using Python with Pandas, to creating interactive charts and dashboards in Power BI to uncover key trends and metrics.

## Project Overview

The main objective of this project is to:
* Perform data loading and initial exploration.
* Clean and preprocess the dataset, including handling missing values.
* Engineer new features from datetime information (e.g., hour, day, month, peak/off-peak).
* Aggregate trip data to analyze demand patterns.
* Visualize key metrics and trends using Power BI.
* Derive actionable insights into Uber's operations and user behavior.

## Data Source

The original dataset is an Uber trip record CSV file.

**Access the raw dataset here:** [Uber Original Data (CSV) 

---

## Python for Data Preprocessing & Feature Engineering

This section details the Python scripts used for initial data handling, cleaning, and creating new analytical features.

### 1. Data Loading and Initial Exploration

This script initiates the data analysis process by loading the Uber dataset from a CSV file into a Pandas DataFrame. It then provides an initial overview of the data's structure and contents, displaying the first few rows, dimensions, and general information.

![Screenshot of Python script for Uber data loading and exploration](https://github.com/user-attachments/assets/3a82d8d5-1533-4ba9-9e01-f4e61cb40f84)

![Screenshot of Pandas info and dtypes](https://github.com/user-attachments/assets/c0ce83f7-a4a3-429f-9b8c-d9254eab64fb)

![Screenshot of Pandas describe output](https://github.com/user-attachments/assets/4ba2e214-f80a-4769-a3ef-07c8186ba06a)

### 2. Missing Value Check

This part of the script identifies and quantifies missing (null) values in each column of the dataset, which is a crucial step before cleaning.

![Screenshot of Python script checking for missing values](https://github.com/user-attachments/assets/cffc7c3b-c823-41a2-9c1c-810e71d75aec)

### 3. Handling Missing Data (Dropping Nulls)

This step removes any rows that contain missing (NaN) values from the dataset, ensuring that subsequent analyses are performed on complete records. The script then prints the new dimensions of the dataset after this cleaning operation.

![Screenshot of Python script for dropping missing values](https://github.com/user-attachments/assets/a04b8ed4-04d7-44d1-a620-ff5895f2a9cf)

### 4. Creating Time-Based Features

This part of the script focuses on extracting useful information from the `pickup_datetime` column. It converts the datetime to a timezone-naive format and then creates new features such as `hour`, `day`, `month`, and `day_of_week`. Additionally, a `time_period` column is generated to classify rides as 'Peak' or 'Off-Peak' based on defined peak hours.

![Screenshot of Python script for datetime feature engineering](https://github.com/user-attachments/assets/8964ef73-790b-467f-9464-52e974c14210)

### 5. Exporting Cleaned Data

After cleaning and feature engineering, the processed dataset is exported to a new CSV file (`uber_cleaned.csv`). This file is now ready for further analysis, visualization in tools like Power BI, or use in machine learning models.

![Screenshot of Python script for exporting cleaned data](https://github.com/user-attachments/assets/6f1dfd13-0451-4139-affc-2f2dd856a766)

**Access the cleaned dataset here:** [Uber Cleaned Data (CSV)](https://drive.google.com/file/d/1aByobIszoKi-wipnMD3N5x5uDff20og5/view?usp=sharing)

---

## Power BI Analysis & Visualizations

This section showcases the key visualizations and insights generated using Power BI from the cleaned and processed dataset.

### 1. Data Import into Power BI Desktop

The cleaned CSV file was imported into Power BI Desktop, where further modeling and visualization were performed.

![Screenshot of data imported into Power BI Desktop](https://github.com/user-attachments/assets/f8a77e70-d5f0-4f10-8b37-ebe71b8dd180)

### 2. Global Pickup Location Distribution

This map visualizes the geographical spread of Uber pickups.

![Map of pickup locations](https://github.com/user-attachments/assets/3764fcea-9598-4a99-b948-67278b73cfd5)

**Conclusion:** The map of pickup locations clearly shows **dense clusters in major global cities, particularly in North America**, reflecting Uber's primary operational regions.

### 3. Monthly Passenger Count Distribution

This chart displays the total passenger count aggregated by month.

![Passenger Count by Month](https://github.com/user-attachments/assets/c1481211-bf19-4e06-99f0-39c4a3352c89)

**Conclusion:** Passenger activity remains relatively **consistent across months**, with slight variations indicating stable demand throughout the year.

### 4. Passenger Count Distribution (Pie Chart)

This pie chart illustrates the breakdown of trips by the number of passengers.

![Pie Chart of Passenger Count Distribution](https://github.com/user-attachments/assets/e35b1f8e-889c-4874-90a9-10f8cfac5e8f)

**Conclusion:** The vast majority of Uber trips (**over 69%**) are for a **single passenger**, highlighting the prevalence of individual travel.

### 5. Daily Average Fare Over Time

This line chart shows the daily fluctuations in average fare amount over the years.

![Average Fare by Year](https://github.com/user-attachments/assets/5c8586cc-7560-4a13-a617-15bd3b5e3852)

**Conclusion:** Average fares exhibit **daily variability across years**, indicating a dynamic pricing environment influenced by factors such as demand, time of day, and special events.

### 6. Fare Amount Trend Over Time

This chart depicts the overall trend of fare amount across the dataset's duration.

![Fare Amount Trend Over Time](https://github.com/user-attachments/assets/3705eb26-97fe-475c-92b0-9e2d89cf5782)

**Conclusion:** The overall trend in fare amount shows a **gradual decrease over the recorded years**, suggesting potential shifts in pricing strategies or ride characteristics over time.

### 7. Average Fare by Time Period (Peak/Off-Peak)

This bar chart compares the average fare based on the engineered 'TimePeriod' feature (Peak vs. Off-Peak).

![Average Fare by TimePeriod](https://github.com/user-attachments/assets/11c47020-182a-49c8-b89a-fced0b31db92)

**Conclusion:** A significant portion of the total fare amount is generated during **'Off-Peak' hours**, which could be due to longer duration of off-peak periods or consistent demand outside peak times. (Note: If your Power BI graph only shows 'Off-Peak', this conclusion accounts for that. If 'Peak' is also shown, adjust accordingly.)

---

## Key Findings & Overall Conclusion

This project successfully demonstrates a comprehensive data analysis workflow for an Uber trip dataset, from raw data loading and preprocessing to insightful visualization. Through Python with Pandas, the dataset was meticulously cleaned, and critical features like hourly, daily, and monthly trip data, as well as peak/off-peak indicators, were engineered from datetime information.

The subsequent Power BI visualizations provided clear and actionable insights into Uber's operational patterns and user behavior:

* **Demand Peaks:** Analysis of trip distribution by hour and day clearly identified **consistent peak demand during traditional commute hours and amplified activity on weekends**, highlighting specific periods of high service utilization.
* **Passenger Trends:** The majority of Uber trips (**over 69%**) were found to accommodate a **single passenger**, reinforcing Uber's role in individual mobility and suggesting potential for ride-sharing optimization.
* **Fare Dynamics:** While overall fare amounts showed a **gradual decrease over the recorded years**, daily average fares exhibited **significant variability**, likely influenced by dynamic pricing and real-time demand fluctuations.
* **Geographical Footprint:** The map of pickup locations confirmed Uber's strong presence and **concentration in major urban centers globally, particularly in North America and parts of Europe**, reflecting its primary operational regions.

In summary, this analysis provides valuable insights into Uber's service demand patterns, emphasizing key times and locations of high activity. These findings are crucial for informing operational strategies, driver allocation, and dynamic pricing models to optimize service efficiency and meet user demand effectively.

---

## Technologies Used

* Python (Pandas)
* Power BI Desktop
* Google Drive (for data storage)



[umutoninadege]
