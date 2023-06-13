# Bellabeat Data Analysis Project

# Project Overview
* Bellabeat is a small, successful company that has the potential to become a larger company in the global smart device market. 
* There is a need to analyze smart device fitness data to unlock new growth opportunities for the company. 
* The analysis focuses on one of Bellabeat's products. 
* The smart device data analysis is useful to gain insights into how consumers use Bellabeat's smart devices and will further guide the marketing strategy for the company. 
* Smart device usage data is viewed based on daily activity, calories, intensity, sleep time, and weight.
* This analysis uses 5 selected tables with a total of 45,618 queries from the entire database of 18 tables.
* The entire analysis using R programming language.

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
* Activities carried out at the **step 2 prepare** consist of downloading the r library to be used, importing, and understanding the dataset.
* The r libraries used are 'tidyverse', 'lubridate', 'ggplot2', 'dplyr', and 'tidyr'.
* Imported datasets that have previously been downloaded via kaggle, you can see the raw data in this [Link](https://www.kaggle.com/datasets/arashnic/fitbit)
* The imported dataset consists of several tables, namely 'dailyActivity', 'hourlyCalories', 'hourlyIntensities', 'sleepDay', and 'weightLogInfo'.
* To understand the dataset, I used the glimpse() function in r 

## Step 3: Process

## Key tasks
1. Check the data for errors.
2. Choose your tools.
3. Transform the data so you can work with it effectively.
4. Document the cleaning process.

## Deliverable
Documentation of any cleaning or manipulation of data:

## Manipulating and fixing the data
After importing and understanding the dataset, it was found that there were errors in some columns containing date and time data that needed to be resolved.
* Fixing the error column by changing the format of the right data type.
* After the fix, I checked the dataset again to make sure that the data type format was as desired.
* As in the 'calories' table below, the data type format is appropriate.

**GAMBAR**

## Step 4: Analyze

## Key tasks
1. Aggregate your data so it’s useful and accessible.
2. Organize and format your data.
3. Perform calculations.
4. Identify trends and relationships.

## Deliverable
A summary of your analysis:

### Exploring and summarizing the data
## Summary statistic
Exploration is performed by looking for summary statistics to get a descriptive overview of the dataset.

**GAMBAR**

There are several key findings, namely:
1. The average user utilizes his/her **daily activity** with **7638 steps**. This average value is not in line with the WHO recommendation of a minimum of **8,000** steps or more per day.
2. Based on the average value of **sedentaryminutes**, most users do not move for 991 minutes or 16 hours. There is a need for reminder notifications on smart devices, to make users do more movement or activity so that **sedentaryminutes** can be reduced.
3. Most users do activities that are categorized as **light** in minutes, compared to activities that are categorized as **moderate** or **high**.
4. Based on the average **BMI value of 25.56**, which means that users are classified as **obese**. This result is still not in accordance with the **recommended normal BMI** value which is between **18.5 - 22.9**. There is a need for additional features in the device to make users more aware of BMI values and provide attractive solution options to reduce them.

## Step 5: Share

## Key tasks
1. Determine the best way to share your findings.
2. Create effective data visualizations.
3. Present your findings.
4. Ensure your work is accessible.

## Deliverable
Supporting visualizations and key findings:

## Visualization

#### Total Steps vs. Calories (Activity)

![images/TotalSteps vs. Calories.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Total_Steps%20vs.%20Calories.png?raw=true)

* There is a positive correlation between total steps and calories. As the total steps increase, the number of calories will increase.

#### Total Minutes Asleep vs. Total Time in Bed (Sleep)

![images/TotalMinutesAsleep vs. TotalTimeinBed.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Total%20Minutes%20Asleep%20vs.%20Total%20Time%20in%20Bed.png?raw=true)

* There is a linear relationship between sleep duration and total time in bed. The more time spent in bed, the longer the sleep duration.
* However, there is a need to improve the quality of sleep by informing the right time to sleep by providing automatic reminders of bedtime.
* If necessary, it is equipped with an automatic alarm/reminder if the sleep time is excessive (in accordance with health recommendations by WHO or health experts) and encourages users to move immediately.

#### Average Total Intensity vs. Time (Intensities)

![images/AverageTotalIntensity vs. Time.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Average%20Total%20Intensity%20vs.%20Time.png?raw=true)

* The range of user intensity starts to increase from 5 am to 10 pm.
* The highest intensity occurs from 5 pm to 7 pm. I estimate that the majority of users utilize this time frame to increase their intensity by exercising after work.
* Maybe an automatic reminder can be given to users to exercise during the time range with the highest intensity, which is 5 - 7 pm.

#### Minutes Asleep vs. Sedentary Minutes (Merged data (activity & sleep))

![images/MinutesAsleep vs. SedentaryMinutes.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Minutes%20Asleep%20vs.%20Sedentary%20Minutes.png?raw=true)

* There is a negative correlation between sedentary time and sleep duration
* Sleep quality needs to be improved by telling users when to sleep to reduce sedentary time. This improvement in sleep quality will make users more productive in doing many activities that are beneficial to their health.

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
* You can access the code in this LINK
