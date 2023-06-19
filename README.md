# Bellabeat Data Analysis Project

# Project Overview
* Bellabeat is a small, successful company that has the potential to become a larger company in the global smart device market. 
* There is a need to analyze smart device fitness data to unlock new growth opportunities for the company. 
* The analysis focuses on one of Bellabeat's products. 
* The smart device data analysis helps gain insights into how consumers use Bellabeat's smart devices and will further guide the marketing strategy for the company. 
* Smart device usage data is viewed based on daily activity, calories, intensity, sleep time, and weight.
* This analysis uses five selected tables with a total of 45,618 queries from the entire database of 18 tables.
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
* Analyze smart device usage data to discover new growth opportunities, and the resulting insights can develop marketing strategies for companies.

## Step 2: Prepare

## Key tasks
1. Download data and store it appropriately.
2. Identify how it’s organized.
3. Sort and filter the data.
4. Determine the credibility of the data.

## Deliverable
A description of all data sources used:
* Activities at the **Step 2 Prepare** consist of downloading the R library, importing, and understanding the dataset.
* The R libraries are 'tidyverse', 'lubridate', 'ggplot2', 'dplyr', and 'tidyr'.
* Imported datasets that have previously been downloaded via Kaggle. You can see the raw data in this [Link](https://www.kaggle.com/datasets/arashnic/fitbit)
* The imported dataset consists of several tables: ' dailyActivity', 'hourlyCalories', 'hourlyIntensities', 'sleepDay', and 'weightLogInfo'.
* To understand the dataset, I used R's glimpse() function. 

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
* After the fix, I rechecked the dataset to ensure the data type format was as desired.
* As in the 'calories' table below, the data type format is appropriate.

![output](https://github.com/al1fandi/Bellabeat_Project/blob/main/images/output.png?raw=true)

## Step 4: Analyze

## Key tasks
1. Aggregate your data so it’s useful and accessible.
2. Organize and format your data.
3. Perform calculations.
4. Identify trends and relationships.

## Deliverable
A summary of your analysis:

## Exploring and summarizing the data
## Summary statistic
Exploration is performed by looking for summary statistics for a descriptive dataset overview.

There are several key findings, namely:
1. The average user utilizes his/her **daily activity** with **7638 steps**. This average value is not in line with the WHO recommendation of a minimum of **8,000** steps or more per day.
2. Based on the average value of **sedentaryminutes**, most users only move for a maximum of 991 minutes or 16 hours. There is a need for reminder notifications on smart devices to make users do more movement or activity so that **sedentaryminutes** can be reduced.
3. Most users do activities that are categorized as **light** in minutes, compared to activities that are categorized as **moderate** or **high**.
4. Based on the average **BMI value of 25.56**, which means that users are classified as **obese**. This result must still follow the **recommended normal BMI** value between **18.5 - 22.9**. The device needs additional features to make users more aware of BMI values and provide attractive solution options to reduce them.

## Step 5: Share

## Key tasks
1. Determine the best way to share your findings.
2. Create effective data visualizations.
3. Present your findings.
4. Ensure your work is accessible.

## Deliverable
Supporting visualizations and key findings:

## Visualization

Let's visualize the data to determine whether there is a relationship between variables and get valuable insights for a conclusion and recommendations to stakeholders.

#### Total Steps vs. Calories (Activity)

![images/TotalSteps vs. Calories.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Total_Steps%20vs.%20Calories.png?raw=true)

* There is a positive correlation between total steps and calories. As the total steps increase, the number of calories will increase.

#### Total Minutes Asleep vs. Total Time in Bed (Sleep)

![images/TotalMinutesAsleep vs. TotalTimeinBed.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Total%20Minutes%20Asleep%20vs.%20Total%20Time%20in%20Bed.png?raw=true)

* a linear relationship exists between sleep duration and total time in bed. The more time spent in bed, the longer the sleep duration.
* However, there is a need to improve sleep quality by informing the right time to sleep by providing automatic bedtime reminders.
* If necessary, it is equipped with an automatic alarm/reminder if the sleep time is excessive (following health recommendations by WHO or health experts) and encourages users to move immediately.

#### Average Total Intensity vs. Time (Intensities)

![images/AverageTotalIntensity vs. Time.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Average%20Total%20Intensity%20vs.%20Time.png?raw=true)

* The range of user intensity starts to increase from 5 am to 10 pm.
* The highest intensity occurs from 5 pm to 7 pm. Most users utilize this time frame to increase their intensity by exercising after work.
* An automatic reminder can be given to users to exercise during the time range with the highest intensity, 5 - 7 pm.

#### Minutes Asleep vs. Sedentary Minutes (Merged data (activity & sleep))

![images/MinutesAsleep vs. SedentaryMinutes.](https://github.com/al1fandi/Bellabeat_Case_Study/blob/main/images/Minutes%20Asleep%20vs.%20Sedentary%20Minutes.png?raw=true)

* There is a negative correlation between sedentary time and sleep duration
* Sleep quality must be improved by telling users when to sleep to reduce sedentary time. This improvement in sleep quality will make users more productive in doing many activities that benefit their health.

## Step 6: Act

## Key tasks
1. Create your portfolio.
2. Add your case study.
3. Practice presenting your case study to a friend or family member.

## Deliverable
Your top high-level insights based on your analysis:

### Final conclusion and recommendations for the Bellabeat
The data to formulate the conclusions consisted of daily activity, calories, intensity, sleep time, and weight, including the user's habits in using Bellabeat smart devices. Despite the limited data available and the number of respondents, the conclusions of the results and recommendations will provide an overview of smart device usage that is useful for developing marketing strategies for Bellabeat products. The findings and recommendations are as follows:
* The data shows an increase in the intensity of using Bellabeat smart devices between 5 pm - 7 pm. This data indicates that most female users increase their intensity to exercise after work. For this reason, Bellabeat's product sales target is recommended for women who work full-time from morning to evening.
* The average number of 7638 steps has yet to reach the WHO recommended value. This average number indicates that users of this smart device have yet to realize the importance of maintaining their health. Bellabeat needs to create an online campaign for users and non-users about the health benefits of activities that result in a minimum of 8,000 steps or more daily. The existence of this campaign will attract new users to use Bellabeat because they (new users) will feel educated about maintaining a healthy body.
* The sedentary minutes' value reveals that users are inactive daily. Therefore, there is a need for a "challenge" feature in the Bellabeat app that will encourage users to move their bodies. Each user who completes the challenge is rewarded, e.g., a discounted membership fee if necessary. This challenge feature will provide a new experience for users and can attract new users to use the Bellabeat app.
* Based on the user's BMI value, there is a need for additional features in the Bellabeat application. The feature recommends activities that can lose weight even when the user is busy working (based on the average intensity over some time).
* Improving sleep quality is essential to reduce sedentary minutes for users. Therefore, adding an automatic reminder feature to let users know when to sleep according to health recommendations would be beneficial for users to improve their sleep quality.
* You can access the code in this [LINK](https://github.com/al1fandi/Bellabeat_Project/blob/16b860bf742e33d16340e470ccb55bf949f9cf2a/code/data-analysis-project-bellabeat.ipynb)
