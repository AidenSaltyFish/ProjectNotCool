---
title: Part I
date: 2022-05-07
description: Part I
---

# Read the dataframe and data overview
- Read all the YRBSS results of the US dated from 1991
- Extract data of 5 boroughs of New York from 2007, because NYC school survey starts from 2007, make it possible for further comprehensive study.
- Show the overview of the dataset for all the following analysis in this notebook: total each year, total number of each borough in all years and each year.
  ![IMAGE](/part_1/part_1_1.svg/)
  ![IMAGE](/part_1/part_1_2.svg/)
  ![IMAGE](/part_1/part_1_3.svg/)
  ![IMAGE](/part_1/part_1_4.svg/)

# Demographic Overview 

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_demographic.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

![IMAGE](/part_1/part_1_5_race_year.svg/)
![IMAGE](/part_1/part_1_6_grade.svg/)
![IMAGE](/part_1/part_1_7_grade_age.svg/)

## Comments
### Gender
The dataset contains fairly unbiased distribution on genders, with gender ratio approximate to 1:1 for each borough, except that Manhattan shows a slightly higher proportion of female respondants with about 60%.

### Race
Respondants of the 5 boroughs don't share the same race distribution. Bronx, Manhatten and Queens are dominated by Hispanic/Latino students, while Brooklyn reports more Black/African American participants. To our surprise, Staten Island seems to be the only borough that are mostly comprised of White students.

Seeing from the line chart of the four ethnic groups in each borough, the race distribution of each borough remains rather steady through the years. Only few intersections, such as Black/African American with Hispanic/Latino in Brooklyn and White with Hispanic/Latino in Staten Island are shown, implying small fluctuations of the racial diversity.

### Age/Grade
The dataset is sampled in a similar distribution of age groups across boroughs, where 14-17 year-old participants takes part in the majority. Age 14, 15, 16 and 17 each contributes roughly 20%-25% of the total samples in each borough.

Similarly, the grade distribution is also the same across boroughs. The dataset is of high school students, so grade 9-12 are evenly sampled in all 5 boroughs.

Further check on the age distribution by grade across all boroughs, it can be seen that grade 9 students are centered around 14 years old, grade 10 around 15 years old, and so on and so forth. There are no signs of early or late schooling in any borough, because their pattern of grade-age distribution is almost the same.

# Smoking Behavior Analysis
## Smoking Cigarette in Each Borough
<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_pct_smokers.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

### Comment
Clearly, Staten Island and Queens reported more high school smokers - nearly 30% of high school students have tried smoking. Bronx, Brooklyn and Manhattan have a similar level of high school smokers, which is lower than the forementioned two boroughs, at about 22%.

![IMAGE](/part_1/part_1_10_1_days_smoke_pct.svg/)

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/70866bdfd5d2d05a6797ccfad3eb632e7cddcfee/static/part_1/part_1_days_smokers.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

### Comment
Since the amount of non-smokers is still overwhelmingly larger than smokers in all boroughs, we only visualize the sub-categories of smokers and analyze characteristics of smokers' behaviors in each borough.

Good news: In all boroughs, around 1/3 of the smokers only smoke occasionally, corresponding to the option 1 or 2 days in the last month. In Brooklyn and Manhatten the proportion is even larger, up to over 40%.

Both Queens and Staten Island reported significantly more smokers who smoke on over 20 days in a month. In particular, Staten Island seems to be the hot zone of heavy smokers, with smallest percentage of those who only smoke 1 or 2 days and largest percentage of those who smoke on all 30 days. In fact the percentage (and absolute number, too) of day-to-day smokers in Staten Island is so large that it doubles that of Manhatten.

Bronx shows a higher percentage of those who have smoked for 3 to 5 days. Be careful! These students are likely to more than just curious about cigarettes -- they are forming a habit of smoking!

![IMAGE](/part_1/part_1_11_1_per_day_pct.svg/)

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_cigarettes_perday_smokers.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

### Comment
Again on heavy smokers -- Stanten Island win! Over 10% participants smoked more than 10 cigarettes per day, while less than 50% consume up to 1 cigerette daily. Other 4 boroughs all have more than 50% participants smoking less than 1 cigerette, and more than 85% participants no more than 5 a day. Manhattan reports the largest percentage of students smoke no more than 1 cigerrete per day and the smallest percentage of smoking more than 5 cigerattes per day.

![IMAGE](/part_1/part_1_12_smoke_age_distr.svg/)

### Comment - NEED MORE
Surprisingly, Bronx have significantly larger percentage of students who start smoking before 8 years old, which is about 30%. What's more, the distribution in Bronx is obviously asymmetrical, which leans expands more to younger groups. Manhattan has a great proportion of almost 40% of smokers picking up smoking at 13 or 14 years, and compared to other 4 boroughs, an overall older age of smoking acquisition.

## Temporal Change of Tobacco Usage

![IMAGE](/part_1/part_1_13_time_smokers.svg/)

<iframe
src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_year_smoking_percentage.html"
sandbox="allow-same-origin allow-scripts"
width="100%"
height="500"
scrolling="no"
seamless="seamless"
frameborder="0">
</iframe>

### Comment
The high school students' smoking rate in all boroughs slide down quickly with time, starting from around 40%-50% in 2007 to around 10% in 2019. The slope remains steady for Bronx, Brooklyn and Manhatten, where the smoking rate decreses almost the same each year, while Queens were in a plateau in 2011-2015, and Staten Island went through a plummeting period in 2009-2011 and a remains stable after 2017.

Queens and Staten Island have retained a high smoking rate through most years, and both landed on slightly higher smoking rate in 2019 than other 3 boroughs. Recall that these are also sufferers of heavy smokers and early smokers, it should really raise a flag.

![IMAGE](/part_1/part_1_14_heavy_smoker.svg/)

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_year_heavy_smokers.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

### Comment
- The USA CDC have defined an indicator on top of q33 results, demonstrating the proportion of people who smoke more than 10 cigarettes per day among smokers.
- There is a sharp decrese from 2017 to 2019 in Queens.
- Manhatten remains the lowest heavy smoker rate through the years.
- Heavy smoker rate fluctuates mildly in Brooklyn, with an average of about 10%.
- The heavy smoker rate in Staten Island and Bronx in general raises through the years. This phenomenon partly originated from the decrease in total number of smokers within these boroughs through the years.

### Comment
- The patterns of days of smoking e-vapor and cigars per month don't differ much between boroughs.
- Smoking regular cigarettes, e-vapor products and cigars and alike are not strongly correlated, which means that smoking one type of product doesn't imply smoking other two products, and smoking one product very often in the last month doesn't necessarily imply smoking other two also that often.
- The frequency of smoking different products among smokers are  higher correlated than that of among the whole population, indicating the possible predictability whithin smokers.

