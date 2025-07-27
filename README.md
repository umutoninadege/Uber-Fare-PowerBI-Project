# Uber-Fare-PowerBI-Project
Power BI Data Analysis Assignment This repository contains my Power BI project files focused on data visualization and insight generation. The project involves importing datasets, cleaning and transforming data, and creating interactive charts and dashboards to uncover key trends and metrics.


# Data Loading and Exploration Script
<img width="907" height="552" alt="Image" src="https://github.com/user-attachments/assets/3a82d8d5-1533-4ba9-9e01-f4e61cb40f84" />

<img width="1069" height="477" alt="Image" src="https://github.com/user-attachments/assets/c0ce83f7-a4a3-429f-9b8c-d9254eab64fb" />
<img width="1366" height="759" alt="Image" src="https://github.com/user-attachments/assets/4ba2e214-f80a-4769-a3ef-07c8186ba06a" />

.Handling Missing value
<img width="428" height="82" alt="Image" src="https://github.com/user-attachments/assets/cffc7c3b-c823-41a2-9c1c-810e71d75aec" />
<img width="428" height="82" alt="Image" src="https://github.com/user-attachments/assets/cffc7c3b-c823-41a2-9c1c-810e71d75aec" />
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# ✅ Load the cleaned dataset
uber_df = pd.read_csv("C:/Users/nadege/Documents/uber_cleaned.csv")

# Convert pickup_datetime to datetime and remove timezone info
uber_df['pickup_datetime'] = pd.to_datetime(uber_df['pickup_datetime'], utc=True).dt.tz_localize(None)

# ✅ Extract full datetime features
uber_df['hour'] = uber_df['pickup_datetime'].dt.hour
uber_df['day'] = uber_df['pickup_datetime'].dt.day
uber_df['month'] = uber_df['pickup_datetime'].dt.month
uber_df['weekday'] = uber_df['pickup_datetime'].dt.day_name()  # Monday, Tuesday, ...

# ✅ Filter out unrealistic fare amounts
uber_df = uber_df[(uber_df['fare_amount'] > 0) & (uber_df['fare_amount'] < 200)]

# 📊 Plot average fare by hour
plt.figure(figsize=(10, 6))
sns.lineplot(x='hour', y='fare_amount', data=uber_df, estimator='mean', ci=None, marker='o')
plt.title('Average Fare Amount by Hour')
plt.xlabel('Hour of Day')
plt.ylabel('Average Fare ($)')
plt.grid(True)
plt.tight_layout()
plt.show()

# 📊 Plot average fare by weekday
plt.figure(figsize=(10, 6))
sns.barplot(x='weekday', y='fare_amount', data=uber_df, estimator='mean', ci=None, palette='coolwarm')
plt.title('Average Fare by Day of the Week')
plt.xlabel('Weekday')
plt.ylabel('Average Fare ($)')
plt.tight_layout()
plt.show()



