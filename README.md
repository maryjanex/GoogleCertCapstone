# GoogleCertCapstone
Google Data Analytics Capstone: Cyclistic Case Study
Course: https://www.coursera.org/learn/google-data-analytics-capstone 
# Introduction
In this case study, I will work for a fictional company, Cyclistic, along with some key team members as their junior data analyst. To answer the business questions, I will follow the steps of the data analysis process: Ask, Prepare, Process, Analyze, Share, and Act. 
# Background
Cyclistic, a Chicago bike-share program, aims to convert casual riders (single-ride or day-pass users) into annual members. To achieve this, they need a deeper understanding of the differences between these two groups. By analyzing historical bike trip data, they can identify trends and tailor marketing strategies to appeal to casual riders and encourage them to become annual members.
# Ask
Three questions to guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?
Moreno has assigned me the first question: How do annual members and casual riders use Cyclistic bikes differently?
# Prepare
I will use Cyclistic's historical trip data to analyze and identify trends, I downloaded the previous 12 months of trip data from November 2023 to October 2024 from [divvy_tripdata](https://divvytripdata.s3.amazonaws.com/index.html). The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).
This is public data that can be used to explore how different customer types are using Cyclistic bikes. But note that data-privacy issues prohibit from using riders’ personally identifiable information. This means that we won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.
There are 12 files with the naming convention of MMYYYY-divvy-tripdata and each file includes information for one month, such as the ride id, bike type, start time, end time, start station, end station, start location, end location, and whether the rider is a member or not. The corresponding column names are ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng, end_lat, end_lng and member_casual.
# Process
I chose to use BigQuery to analyze my data as Microsoft Excel cannot process more than one million rows. The Cyclistic data has more than 5.9 million rows. 

**Data Combination**

SQL Query: [Data Combination](https://github.com/maryjanex/GoogleCertCapstone/blob/main/Data%20Combination)

I combined the 12 csv files into one table named "combined_data" containing 5,933,712 rows of data.

**Data Exploration**

SQL Query: [Data Exploration](https://github.com/maryjanex/GoogleCertCapstone/blob/main/Data%20Exploration)
  - The ride_id column is the primary key containing 16 numbers in all the rows.
  - rideable_type - three unique types of bikes
      electric bike: 1,408,308
      classic bike: 2,772,172
      electric scooter: 46,940
  - There are 7,801 trips with durations longer than 24 hours and 136,108 trips less than a one-minute duration removed from the dataset.
  - Total of 1,079,270 rows are removed where both start_station_name and start_station_id are missing.
  - Total of 1,112,056 rows are removed where both end_station_name and end_station_id are missing.
  - Total of 7,417 rows are removed where both end_lat and end_lng are missing.
  - member_casual column has two unique types of memberships
      member: 2,710,468
      casual: 1,516,952

**Data Cleaning**

SQL Query: [Data Cleaning](https://github.com/maryjanex/GoogleCertCapstone/blob/main/Data%20Cleaning)
- Rows with missing values were deleted.
- ride_length, day_of_week, and month are added.
- Trips longer than 24 hours and less than one minute were removed.
- 1,706,262 total rows were removed.
  
# Analyze & Share
Data Visualization: [Tableau](https://public.tableau.com/app/profile/mary.jane.nguyen4796/viz/GoogleDataAnalyticsCapstone_17325976399410/AvgRideLengthRideType)

After my exploration and cleaning - my dataset is ready to be visualized using Tableau. I created multiple tables for analysis and to visualize them.
**Main Question** _How do annual members and casual riders use Cyclistic bikes differently?_
I created four different visualizations
- Bike Type Comparison
Majority of the riders are members of Cyclistic with 64.12% being members while 35.88% are casual riders. Classic and electric bikes are used mainly by members while electric scooters are used more by casual riders.

- Monthly and Day-of-Week Comparison of Total Trips to Average Ride Duration
Members took more trips each month/day of the week but casual riders rode their bikes longer.

- Average Ride Length by Ride Type
Casual riders rode classic bikes longer than members by 15.56, electric bikes by 4.86, and electric scooters by 3.46.

# Act
Recommendations:
- Offer incentives for longer rides as casual riders ride longer than members to become members.
- Casual riders ride their bikes more over the weekends so offering short-term memberships could convert casual riders to members.
