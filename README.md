Google Data Analytics Capstone Project: Case Study 1
# Cyclistic
## How does a bike-share navigate a speedy success
![Screenshot 2024-05-07 1 16 07 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/e265eb53-2e21-4a7b-8149-a96431376189)


### INTRODUCTION
This is a part of the capstone project for the professional certificate on “Google Data Analytics” offered through Coursera. This will be a great chance to apply the practices and procedures associated with the data analysis process to a given set of data. I am on the way to demonstrate my ability to handle real-life data as a junior data analyst; and this is going to be the first of my online portfolio.

#### Scenario
Here, the case study context is, I am a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve my recommendations, so they must be backed up with compelling data insights and professional data visualizations.

#### Characters and teams
- Cyclistic: A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use the bikes to commute to work each day.
- Lily Moreno: The director of marketing and my manager. Moreno is responsible for the development of campaigns and initiatives to promote the bike-share program. These may include email, social media, and other channels.
- Cyclistic marketing analytics team: A team of data analysts who are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy. I joined this team six months ago and have been busy learning about Cyclistic’s mission and business goals—as well as how I, as a junior data analyst, can help Cyclistic achieve them.
- Cyclistic executive team: The notoriously detail-oriented executive team will decide whether to approve the recommended marketing program.

#### About the company
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.
Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.
Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a solid opportunity to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.
Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

### ASK
The objective of this phase was to identify the business task and consider the key stakeholders.
Business task of the case study is as below:
- How do casual riders and annual members use Cyclistic bikes differently?

From the answer of the above question, my team will design a new marketing strategy to convert casual riders into annual members; because, the director of marketing, Lily Moreno, believes the company’s future success depends on maximizing the number of annual memberships. 

### PREPARE
In this phase, I downloaded the data and stored it appropriately. I have also identified how the data is organized. I have sorted and filtered the data to check and determined the credibility of the data. 
The data is downloaded from the following [link](https://divvy-tripdata.s3.amazonaws.com/index.html). It has been made available by Motivate International Inc. under this [license](https://www.divvybikes.com/data-license-agreement). As per guidelines, I need to use last 12 months data for this case study. I, therefore, have downloaded data from April 2023 to March 2024. There were 12 individual monthly zip files which I have saved in a folder of my google drive.
![Screenshot 2024-04-30 11 20 22 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/8d3294f5-1319-47f2-87f9-0f46eea84e21)

Once unzip, there were 12 individual CSV files which I analyzed for getting required insight. Each CSV file is structured in rows and columns.
![Screenshot 2024-05-02 3 05 04 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/6db6a9a3-bda0-4a56-990f-25c8dc913994)

I opened the CSV file one after another to check its ROCCC (reliable, original, comprehensive, current, cited). The data is from open sourced and first source (from the company itself), anonymised, unbiased and latest. It is also complete and accurate. Hence it is reliable, original, current and cited data to work with. It is also comprehensive which contains all the critical information to answer the business task.

### PROCESS
In this section, I checked the data for errors, chose the tools for the cleaning process and transformed my data through cleaning for further analysis.

#### Tools for Data Process
I could not use MS Excel or Google Sheet tools for data processing though I am very much adept in using these tools. This is because I am going to handle “Big Data” here which spreadsheets can not load for processing. So, I used BigQuery to aggregate the monthly CSV files into a single table from April 2023 to March 2024. 

#### Uploading the data in BigQuery
It wasn’t a straightforward process for me. I faced some challenges while doing this and I resolved those on the go. The summary of the process was as below:
I created a dataset named “case_study_1_cyclistics”.
Among the 12 CSV files, I managed to locally upload 6 CSV files whose sizes were under 100 MB. These files were:
- Apr 2023 (named “202304-divvy-tripdata”)
- Nov 2023 (named “202311-divvy-tripdata”)
- Dec 2023 (named “202312-divvy-tripdata”)
- Jan 2024 (named “202401-divvy-tripdata”)
- Feb 2024 (named “202402-divvy-tripdata”)
- Mar 2024 (named “202403-divvy-tripdata”)

Files with sizes over 100 MB can’t be uploaded locally and I had 6 similar files to work with. These files were:
- May 2023 (named “202305-divvy-tripdata”)
- Jun 2023 (named “202306-divvy-tripdata”)
- Jul 2023 (named “202307-divvy-tripdata”)
- Aug 2023 (named “202308-divvy-tripdata”)
- Sep 2023 (named “202309-divvy-tripdata”)
- Oct 2023 (named “202310-divvy-tripdata”)
To tackle this issue, I made a bucket in “Google Cloud Storage” and uploaded those 6 files over there. Later, I imported those files in BigQuery from Google Cloud Storage.

#### Check the data for organizations
I checked the schema of all the tables in BigQuery to see how these were organized. I found that there were 13 identical columns in all the tables. So, the tables were identical in structure and they were organized as below.
![Screenshot 2024-05-03 8 17 15 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/066e9767-fd90-4276-9f02-a835592ea77e)

#### Merge the data
There were 12 identical structured CSV files uploaded in BigQuery in a dataset named “case_study_1_cyclistics”. I used SQL Query to merge these data in a single table named “combined_12m_data”.
![Screenshot 2024-05-03 8 32 19 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/8950bb12-4e69-4edd-b07f-c292ece1e7f0)

The combined table contains 5,750,177 rows - I got the information from the bottom part of “PREVIEW” tab as below:
![Screenshot 2024-05-03 8 30 00 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/f85c13ba-0e0f-4351-9523-62f2b5cff884)

To double check, I have also used SQL query as below. As expected, I got the same result.
![Screenshot 2024-05-03 10 16 11 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/9ba5f885-edb9-4f44-ab62-7efcfa741a28)

#### Check the data for errors
I have used SQL query to check the new combined table, “combined_12m_data”, to find null values.
![Screenshot 2024-05-03 10 13 36 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/ded020c2-9dd8-4072-a954-8ca0caf5de94)

To make the above query result more readable, I have given this in below long tabular form:
![Screenshot 2024-05-07 11 52 59 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/4047cd6f-36a7-4c50-8b02-2dcb5839c2c2)

There were 15.3% null values which was really significant. However, I have decided to kept all the data into consideration for my analysis due to below reasons:
1. The data may lose reliability and representativeness if I delete this large amount of data from the record.
2. The columns where null value existed will not affect the data quality.
3. It’s not going to impact my analysis considering the business task I’m dealing with.
I have also checked data through SQL query to know whether there’s any data duplication. I found no duplicate records in the new combined table.
![Screenshot 2024-05-03 9 54 33 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/938f01ef-d68e-4578-b49b-4d3745601af9)

The above was also confirmed through below SQL query:
![Screenshot 2024-05-03 9 57 25 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/259e2590-fa8d-434e-aefd-69f18064df13)

I also checked the length of the ride_id column and have found a unique character length as below:
![Screenshot 2024-05-04 1 08 14 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/34e39e0e-10b9-49ff-a68d-0c9a8e549ff3)

We can consider the ride_id column as primary id because it shows no duplicate, no null value, unique value and unique character length.
I have checked the unique values of rideable_type column and found 3 unique values as below:
![Screenshot 2024-05-04 1 18 07 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/c598e2d5-5543-4556-9e51-0d71fd4b0ec8)

As below, I have identified the TIMESTAMP of the records at started_at and ended_at columns. It was YYYY-MM-DD hh:mm:ss UTC
![Screenshot 2024-05-04 1 45 16 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/90f3df93-3f34-48a4-b3bf-2931956adbd0)

I have checked the unique values of member_casual column and found 2 unique values as below:
![Screenshot 2024-05-04 1 50 52 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/2f4ed59b-d933-4b7d-aeeb-defa5b4e7630)

#### Creating new table for analysis
I have created a new table for analysis. For creating this table, I have gone through below activities:
- From the existing combined table, I have chosen following 8 columns to include in my new table - ride_id, rideable_type, started_at, ended_at, start_station_name, start_lat, start_lng, member_casual
- I have planned following 4 new columns for my new table - ride_length_minute, day_of_week, month, hour
-- ride_length_minute ~ to determine the “length of the bike rides” in minutes
-- day_of_week ~ to determine the “day of the bike rides”
-- month ~ to determine the “month of the bike rides”
-- hour ~ to determine the “hour of the bike rides”
- I have planned to keep the table cleaned from illogical ride length (zero and negative value in ride length)

The SQL query below was used to execute the above plan and to create the new table  - it was named “combined_12m_data_processed”.
![Screenshot 2024-05-04 10 57 00 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/fa2e12f4-1884-4d8f-888b-d2a9a3fafca2)

### ANALYZE
The new data table was stored appropriately in my dataset of BigQuery. So, it was cleaned, organized with useful data, formatted and readily accessible. So, in this phase, I will perform calculations to identify trends and relationships which will eventually facilitate me to complete my business task.
I have calculated the total number of rides, total length of rides, average length of rides, maximum ride length, and minimum ride length. This was done considering below grouping:
- member_casual
- member_casual, rideable_type
- member_casual, month
- member_casual, day_of_week
- member_casual, hour
- member_casual, start_station_name

#### Group by → member_casual
SQL query and glimpse of result was as below:
![Screenshot 2024-05-05 12 02 50 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/e1fcf144-b5fc-422a-a063-6425a5e2207b)

- Members were availing the more number of rides. But the average ride length was significantly higher for Casual Riders. This makes the total ride length higher for the Casual Riders for the entire period.

#### Group by → member_casual | rideable_type
SQL query and glimpse of result was as below:
![Screenshot 2024-05-05 12 17 26 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/602607f4-b5b4-4de8-adf4-e641fcac00a8)

- Members don’t use docked_bike at all and they like classic_bike most.
- Casual Riders take electric_bike mostly but for shorter trip duration and they use classic_bike for longer trip duration.

#### Group by → member_casual | month
SQL query and glimpse of result was as below:
![Screenshot 2024-05-05 12 38 04 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/a3191322-bd13-4c73-b7f6-899b7b10be0d)

- Members used rides mostly in August and least in January. Their average trip durations across the months were very close (11.2 ~ 13.7 min).
- Casual Riders used mostly in July and least in January. Their average trip durations across the months varied greatly (19.9 ~ 35.6 min).

#### Group by → member_casual | day_of_week
SQL query and glimpse of result was as below:
![Screenshot 2024-05-05 12 53 48 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/c361e049-8029-4d1b-b036-9c16fbd7a609)

- Members took most of the rides on Thursday which was closely followed by Wednesday. Their use was significantly lower on Sunday, which is the weekend.
- Casual Riders took most of the rides on Saturday, which is just before the weekend. Their use was lowest on Monday, the first day of the week.

#### Group by → member_casual | hour
SQL query and glimpse of result was as below:
![Screenshot 2024-05-05 1 08 12 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/cde04d7a-49c1-4fd2-9a6a-411a96df6944)
![Screenshot 2024-05-05 1 09 37 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/8514d523-bbc3-4c71-b49c-50a4ed8d546c)

- Members took most of the rides at 17 hours - their most trips were between 15 to 18 hours. And, they took the least of the rides at 4 hours - their least trips were between 3 to 4 hours.
- Casual Riders also took most of the rides at 17 hours - their most trips were between 15 to 18 hours like Members. And, like Members, they took the least of the rides at 4 hours - their least trips were between 3 to 4 hours.

#### Group by → member_casual | start_station_name
SQL query and glimpse of result was as below:
![Screenshot 2024-05-05 1 33 20 AM](https://github.com/CMMKabir/cyclistics/assets/161144452/b978a061-8630-4fb9-b53a-f588a214afcc)

- For Members, most of the trips started from 2 stations - “Clinton St & Washington Blvd” and “Kingsbury St & Kinzie St”.
- For Casual Riders, most of the trips started from “Streeter Dr & Grand Ave”. 

### SHARE
I have gained insights from my analysis in the earlier step. In this step, I have created visualizations using Tableau to share my findings. I have done it with utmost care because the Director of Marketing, Lily Moreno, was expecting sophisticated and polished work in order to effectively communicate to the executive team.
In the beginning, I compared who used the rides most in terms of number of rides and time (in minutes).
![Sheet 1 (1)](https://github.com/CMMKabir/cyclistics/assets/161144452/eb7c25d6-5228-404f-b6bf-b72373a601ce)

- Members used bikes more frequently compared to Casual riders; but the latter tend to use bikes for a longer time period even with the less number of rides. Average ride length for Casual riders were significantly higher (2.3x).

Next, I compared their bike type selection for their rides in below section:
![Sheet 1 (2)](https://github.com/CMMKabir/cyclistics/assets/161144452/9abdb49a-37e0-430d-a104-4f92bea76996)

- In terms of total rides, Classic bikes and Electric bikes were with almost equal preference both for Members and Casual riders. Classic bikes were a higher choice for Members and Electric bikes were a higher choice for Casual riders.
- Interestingly, average ride length for Casual riders in Classic bikes was significantly higher from Electric bikes (2.3x). It was also significantly higher from Classic bikes of Members (2.3x).
- Docked bikes were only used by Casual riders in a few instances (3.5%); but its average ride length was awfully high. Members never used this bike in the year.

I have compared the user behavior over the quarters in below section:
![Sheet 1 (7)](https://github.com/CMMKabir/cyclistics/assets/161144452/262ca136-6416-452c-a845-68e67d5bfe00)

- For both Members and Casual riders, 3rd quarter was the most frequent using period closely followed by 2nd quarter and thereafter followed by 4th quarter.
- Average ride length was similar in all the quarters for Members (11.46 ~ 13.38); but it varied a lot for Casual riders (21.50 ~ 31.55).

I have checked the use pattern over the months in below section:
![Sheet 1 (3)](https://github.com/CMMKabir/cyclistics/assets/161144452/22f4c005-f86d-4502-9d91-1626f6233683)

- There was a pure trend here. Use frequency increased over the month consistently and reached its maximum in July for Casual riders and in August for Members. Later the frequency started decreasing consistently and reached its minimum in January.
- Average ride length was similar and consistent for Members (11.2 ~ 13.72); but it varied a great deal for Casual riders (19.86 ~ 35.60).

Use pattern was also identified across the days of the week.
![Sheet 1 (4)](https://github.com/CMMKabir/cyclistics/assets/161144452/6e344d34-19f6-412d-9ecb-003f66c284de)

- For Casual riders, use frequency was higher during weekend (Sunday) and the day before the weekend (Saturday); it was simply opposite for Members.
- Average ride length was also high for Casual riders in the above mentioned pick days; whereas it’s consistently similar across the days for Members.
- For Members, use frequency was higher in the middle of the weekdays (Tuesday ~ Thursday). 
- The difference from highest to lowest use was slim (32%) for Members, and it’s higher (44%) for Casual riders. 

I have also evaluated the use pattern across the hours of the day in below section:
![Sheet 1 (6)](https://github.com/CMMKabir/cyclistics/assets/161144452/69cf47ab-8f0c-49a1-9c31-33dae45b00ca)

- For both Members and Casual riders, the top-6 busy hours for initiating rides were 14 hours ~ 19 hours; and top-3 busy hours were 16 hours ~ 18 hours. The top most busy hour was 17 hours for both user groups.

I have also identified a similar heat map in terms of the journey start station, as below.
![Screenshot 2024-05-06 3 45 39 PM](https://github.com/CMMKabir/cyclistics/assets/161144452/2abdb449-3706-470e-8681-287f215485df)

And, the top origin stations are as per below section:
![Dashboard 2 (1)](https://github.com/CMMKabir/cyclistics/assets/161144452/408b07fc-1cfe-4001-9186-745a46a6cd7e)

- For Members, some of the most frequent origin stations were - Clinton St & Washington Blvd, Kingsbury St & Kinzie St, Clark St & Elm St, Clinton St & Madison St, Wells St & Concord Ln, etc.
- For Casual riders, some of the most frequent origin stations were - Streeter Dr & Grand Ave, DuSable Lake Shore Dr & Monroe St, Michigan Ave & Oak St, DuSable Lake Shore Dr & North Blvd, Millennium Park, etc.

### ACT
In this step, I am going to prepare the deliverables my Marketing Director, Lily Moreno, asked me to create including the three top recommendations based on my analysis.

#### Inference from the analysis
I can summarize the findings I gather in the different steps above. These are:
- Members used bikes more frequently compared to Casual riders; but the latter tend to use bikes for a longer time period even with the less number of rides. Average ride length for Casual riders were significantly higher (2.3x).
- In terms of total rides, Classic bikes and Electric bikes were with almost equal preference both for Members and Casual riders. Classic bikes were a higher choice for Members and Electric bikes were a higher choice for Casual riders. Interestingly, average ride length for Casual riders in Classic bikes was significantly higher from Electric bikes (2.3x). It was also significantly higher from Classic bikes of Members (2.3x). Docked bikes were only used by Casual riders in a few instances (3.5%); but its average ride length was awfully high. Members never used this bike in the year.
- For both Members and Casual riders, 3rd quarter was the most frequent using period closely followed by 2nd quarter and thereafter followed by 4th quarter. Average ride length was similar in all the quarters for Members (11.46 ~ 13.38); but it varied a lot for Casual riders (21.50 ~ 31.55).
- There was a pure trend in the month scenario. Use frequency increased over the month consistently and reached its maximum in July for Casual riders and in August for Members. Later the frequency started decreasing consistently and reached its minimum in January. Average ride length was similar and consistent for Members (11.2 ~ 13.72); but it varied a great deal for Casual riders (19.86 ~ 35.60).
- For Casual riders, use frequency was higher during weekend (Sunday) and the day before the weekend (Saturday); it was simply opposite for Members. Average ride length was also high for Casual riders in the above mentioned pick days; whereas it’s consistently similar across the days for Members. For Members, use frequency was higher in the middle of the weekdays (Tuesday ~ Thursday). The difference from highest to lowest use was slim (32%) for Members, and it’s higher (44%) for Casual riders. 
- For both Members and Casual riders, the top-6 busy hours for initiating rides were 14 hours ~ 19 hours; and top-3 busy hours were 16 hours ~ 18 hours. The top most busy hour was 17 hours for both user groups.
- For Members, some of the most frequent origin stations were - Clinton St & Washington Blvd, Kingsbury St & Kinzie St, Clark St & Elm St, Clinton St & Madison St, Wells St & Concord Ln, etc. For Casual riders, some of the most frequent origin stations were - Streeter Dr & Grand Ave, DuSable Lake Shore Dr & Monroe St, Michigan Ave & Oak St, DuSable Lake Shore Dr & North Blvd, Millennium Park, etc.

#### Recommendations | Answer of Business Task
From this detailed analysis, I do like to place my top 3 recommendations as below:
1. Casual riders use Classic bikes for significantly longer time length - that means they spend much on this transportation vehicle. 
Therefore, we can offer Casual riders a limited time discount X% on trip fare for taking Classic bikes if they become new members within the defined campaign timeline.
2. Casual riders use bikes mostly on Saturday and Sunday - that means they spend much on these days. 
Therefore, we can offer Casual riders a limited time discount Y% on trip fare for taking bikes (except Classic bikes) on Saturday & Sunday if they become new members within the defined campaign timeline.
3. Top start stations for Casual riders are Streeter Dr & Grand Ave, DuSable Lake Shore Dr & Monroe St, Michigan Ave & Oak St, DuSable Lake Shore Dr & North Blvd, Millennium Park, etc - this means a good number of target customers (Casual riders) live in the vicinity. And, peak hours for them are 14 hours ~ 19 hours.
Therefore, we can organize membership registration festivals from temporary booths for a certain defined period in these places (offering some freebies like “limited time discount Z% on next 5 rides”) during peak hours (14 hours ~ 19 hours) to reach the maximum number of target audience.

### CONCLUSION
This was the capstone project which was part of a professional certificate course on “Google Data Analytics”. While proceeding on this project, I was thinking about applying and showing all the skills I have gained through this professional certificate course. I was especially motivated to apply my new skills of SQL, Tableau and R programming in this project. If I did that I would use both Tableau and R programming for visualization. On a similar note, it was my responsibility to do this project in a professional manner which means I should choose and use any one from those tools for my purpose of the project. I chose SQL and Tableau for this project activity. In my new project next time, I am surely going to use R programming to prove my skills on this.
