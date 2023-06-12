# Bellabeat Data Analysis Project

# Project Overview
* Bellabeat is a small, successful company that has the potential to become a larger company in the global smart device market. 
* There is a need to analyze smart device fitness data to unlock new growth opportunities for the company. 
* The analysis focuses on one of Bellabeat's products. 
* The smart device data analysis is useful to gain insights into how consumers use Bellabeat's smart devices and will further guide the marketing strategy for the company. 
* The results of the analysis will be presented to the executive team along with recommendations for Bellabeat's marketing strategy.
* Smart device usage data is viewed based on daily activity, calories, intensity, sleep time, and weight.
* This analysis uses 5 selected tables with a total of 45,618 queries from the entire database of 18 tables.
* The entire analysis using R programming language.

# About the company
Urška Sršen and Sando Mur founded Bellabeat, a high-tech company that manufactures health-focused smart products. Sršen used her background as an artist to develop beautifully designed technology that informs and inspires women around the world. Collecting data on activity, sleep, stress, and reproductive health has allowed Bellabeat to empower women with knowledge about their own health and habits. Since it was founded in 2013, Bellabeat has grown rapidly and quickly positioned itself as a tech-driven wellness company for women. By 2016, Bellabeat had opened offices around the world and launched multiple products. Bellabeat products became available through a growing number of online retailers in addition to their own e-commerce channel on their website. The company has invested in traditional advertising media, such as radio, out-of-home billboards, print, and television, but focuses on digital marketing extensively. Bellabeat invests year-round in Google Search, maintaining active Facebook and Instagram pages, and consistently engages consumers on Twitter. Additionally, Bellabeat runs video ads on Youtube and display ads on the Google Display Network to support campaigns around key marketing dates.

## Step 1: Ask
Sršen asks you to analyze smart device usage data in order to gain insight into how consumers use non-Bellabeat smart devices. She then wants you to select one Bellabeat product to apply these insights to in your presentation. These questions will guide your analysis:
1. What are some trends in smart device usage?
2. How could these trends apply to Bellabeat customers?
3. How could these trends help influence Bellabeat marketing strategy?

## Key tasks
1. Identify the business task
2. Consider key stakeholders

## Deliverable
A clear statement of the business task:
* Analyze smart device usage data to discover new growth opportunities and the resulting insights can develop marketing strategies for companies.

## Step 2: Prepare

## Key tasks
1. Download data and store it appropriately.
2. Identify how it’s organized.
3. Sort and filter the data.
4. Determine the credibility of the data.

## Deliverable
A description of all data sources used:

### Installing and loading the packages
```r
install.packages('tidyverse')
install.packages('lubridate')
install.packages('tidyr')

library(tidyverse)
library(lubridate)
library(ggplot2)
library(dplyr)
library(tidyr)
```

### Importing dataset
```r
activity <- read.csv("dailyActivity_merged.csv")
calories <- read.csv("hourlyCalories_merged.csv")
intensities <- read.csv("hourlyIntensities_merged.csv")
sleep <- read.csv("sleepDay_merged.csv")
weight <- read.csv("weightLogInfo_merged.csv")
```
You can see the raw data in this [Link](https://www.kaggle.com/datasets/arashnic/fitbit)

### Getting to know the data
```r
glimpse(activity)
glimpse(calories)
glimpse(intensities)
glimpse(sleep)
glimpse(weight)
```

## Step 3: Process

## Key tasks
1. Check the data for errors.
2. Choose your tools.
3. Transform the data so you can work with it effectively.
4. Document the cleaning process.

## Deliverable
Documentation of any cleaning or manipulation of data:

### Manipulating and fixing the data
#### Activity
```r
activity$ActivityDate = as.POSIXct(activity$ActivityDate, format = "%m/%d/%Y", 
                                 tz = Sys.timezone())
activity$date <- format(activity$ActivityDate, format = "%m/%d/%y")
```
#### Calories
```r
calories$ActivityHour = as.POSIXct(calories$ActivityHour, format = "%m/%d/%Y %I:%M:%S %p", 
                                 tz = Sys.timezone())
calories$time <- format(calories$ActivityHour, format = "%H:%M:%S")
calories$date <- format(calories$ActivityHour, format = "%m/%d/%y")
```
#### Intensities
```r
intensities$ActivityHour = as.POSIXct(intensities$ActivityHour, format = "%m/%d/%Y %I:%M:%S %p",
                                    tz = Sys.timezone())
intensities$time <- format(intensities$ActivityHour, format = "%H:%M:%S")
intensities$date <- format(intensities$ActivityHour, format = "%m/%d/%y")
```
#### Sleep
```r
sleep$SleepDay = as.POSIXct(sleep$SleepDay, format = "%m/%d/%Y %I:%M:%S %p", tz = Sys.timezone())
sleep$date <- format(sleep$SleepDay, format = "%m/%d/%y")
```
```r
glimpse(activity)
glimpse(calories)
glimpse(intensities)
glimpse(sleep)
```

## Step 4: Analyze

## Key tasks
1. Aggregate your data so it’s useful and accessible.
2. Organize and format your data.
3. Perform calculations.
4. Identify trends and relationships.

## Deliverable
A summary of your analysis:

### Exploring and summarizing the data
#### Distinct "id" value
```r
n_distinct(activity$Id)
n_distinct(calories$Id)
n_distinct(intensities$Id)
n_distinct(sleep$Id)
n_distinct(weight$Id)
```

#### Observations each dataframe
```r
nrow(activity)
nrow(calories)
nrow(intensities)
nrow(sleep)
nrow(weight)
```

#### Summary statistic
```r
# Activity
activity %>% 
  select(TotalSteps, TotalDistance, SedentaryMinutes, Calories) %>% 
  summary()

activity %>% 
  select(VeryActiveMinutes, LightlyActiveMinutes, FairlyActiveMinutes) %>% 
  summary()  
  
# Calories
calories %>% 
  select(Calories) %>% 
  summary()

# Sleep
sleep %>% 
  select(TotalTimeInBed, TotalMinutesAsleep, TotalSleepRecords) %>% 
  summary()

# Weight
weight %>% 
  select(BMI, WeightKg) %>% 
  summary()
```

#### Merging between activity and sleep data (for visualization)
```r
merged_data1 <- merge(sleep,activity, by = c("Id", "date"))
n_distinct(merged_data1)
glimpse(merged_data1)
```

## Step 5: Share

## Key tasks
1. Determine the best way to share your findings.
2. Create effective data visualizations.
3. Present your findings.
4. Ensure your work is accessible.

## Deliverable
Supporting visualizations and key findings:

### Visualization
#### Total Steps vs. Calories (Activity)
```r
ggplot(data=activity, aes(x=TotalSteps, y=Calories)) +
  geom_point() + geom_smooth() + labs(title = "Total Steps vs. Calories") +
  theme(plot.title = element_text(hjust = 0.5)) + 
  ylab("Calories") + xlab("Total Steps")
```
![images/TotalSteps vs. Calories.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Total_Steps%20vs.%20Calories.png?raw=true)

#### Total Minutes Asleep vs. Total Time in Bed (Sleep)
```r
ggplot(data=sleep, aes(x=TotalMinutesAsleep, y=TotalTimeInBed)) +
  geom_point() + labs(title = "Total Minutes Asleep vs. Total Time in Bed") +
  theme(plot.title = element_text(hjust = 0.5)) + geom_jitter() +
  ylab("Total Time In Bed") + xlab("Total Minutes Asleep")
```
![images/TotalMinutesAsleep vs. TotalTimeinBed.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Total%20Minutes%20Asleep%20vs.%20Total%20Time%20in%20Bed.png?raw=true)

#### Average Total Intensity vs. Time (Intensities)
```r
intensities2 <- intensities %>% 
  group_by(time) %>% 
  drop_na() %>% 
  summarise(mean_int= mean(TotalIntensity))
```
```r
ggplot(data=intensities2, aes(x=time, y=mean_int)) +
  geom_histogram(stat = "identity", fill = "lightblue") + 
  theme(axis.text.x = element_text(angle = 90)) +
  theme(plot.title = element_text(hjust = 0.5)) +
  ylab("Avg Total Intensity") + xlab("Time") +
  labs(title = "Average Total Intensity vs. Time")
```
![images/AverageTotalIntensity vs. Time.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Average%20Total%20Intensity%20vs.%20Time.png?raw=true)

#### Minutes Asleep vs. Sedentary Minutes (Merged data (activity & sleep))
```r
ggplot(data=merged_data1, aes(x=TotalMinutesAsleep, y=SedentaryMinutes)) +
  geom_point(color="darkblue") + geom_smooth() + labs(title = "Minutes Asleep vs. Sedentary Minutes") +
  theme(plot.title = element_text(hjust = 0.5)) + 
  ylab("Sedentary Minutes") + xlab("Total Minutes Asleep")
```
![images/MinutesAsleep vs. SedentaryMinutes.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Minutes%20Asleep%20vs.%20Sedentary%20Minutes.png?raw=true)

## Step 6: Act

## Key tasks
1. Create your portfolio.
2. Add your case study.
3. Practice presenting your case study to a friend or family member.

## Deliverable
Your top high-level insights based on your analysis:

### Final conclusion and recommendations for the Bellabeat
The data used to formulate the conclusions consisted of daily activity, calories, intensity, sleep time, and weight, which includes the user's habits in using Bellabeat smart devices. Despite the limited data available and the number of respondents, the conclusions of the results and recommendations will hopefully provide an overview of smart device usage that is useful for developing marketing strategies for Bellabeat products. There are some key findings and recommendations as follows:
* The data shows an increase in the intensity of using Bellabeat smart devices between 5 pm - 7 pm. This indicates that most female users increase their intensity to exercise after work. For this reason, Bellabeat's product sales target is recommended for women who work full-time from morning to evening.
* The average number of 7638 steps has not reached the WHO recommended value. This indicates that users of this smart device have not realized the importance of maintaining their health. Bellabeat needs to create an online campaign for users and non-users about the health benefits of doing activities that result in a minimum of 8,000 steps or more a day. The existence of this campaign will attract new users to use Bellabeat because they (new users) feel educated in maintaining a healthy body.
* The sedentary minutes value reveals that users are sedentary in their daily lives. Therefore, there is a need for a "challenge" feature in the Bellabeat app that will encourage users to move their bodies. Each user who successfully completes the challenge is given a reward, e.g. discounted membership fee if necessary. This challenge feature will provide a new experience for users and can attract new users to use the Bellabeat app.
* Based on the user's BMI value, there is a need for additional features in the Bellabeat application. The feature is a recommendation for activities that can lose weight even when the user is busy working (based on the average intensity over a period of time).
* Improving sleep quality is important to reduce sedentary minutes for users. Therefore, the addition of an automatic reminder feature to let users know when to sleep according to health recommendations would be beneficial for users to improve their sleep quality.
