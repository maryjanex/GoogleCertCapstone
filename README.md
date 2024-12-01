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

*Data Combination**
SQL Query: [Data Combination](https://github.com/maryjanex/GoogleCertCapstone/blob/main/Data%20Combination)

# Analyze
# Share
# Act
