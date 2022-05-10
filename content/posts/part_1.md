---
title: "Part I: Youth, Tobacco and More"
date: 2022-05-07
description: "YRBSS provides all around records on teenagers’ risk behaviors, just as in our common sense: drinking alcohol, physical fights, exercise and diet, mental health, sexual behaviors… and of course, smoking.  There are extensive possibilities to dig in, so you can easily get an idea how NYC high school students behave in terms of smoking: such as how many of them do they smoke, how often do they smoke and how the number of teenage smokers change with time."
---

# Say Hi to YRBSS
YRBSS provides all around records on teenagers’ risk behaviors, just as in our common sense: drinking alcohol, physical fights, exercise and diet, mental health, sexual behaviors… and of course, smoking.  Since our focus would be NYC alone since 2007, let’s first see how many records we can extract, and how many are there in each survey year.
![IMAGE](/part_1/part_1_1.svg/)
![IMAGE](/part_1/part_1_2.svg/)

The YRBSS dataset have different number of records each year. 2007, 2013 and 2015 have smaller amount at about 7500, and the rest years each have about 8000-10000 records, but in general, the scale is on the same level through the years.
The YRBSS dataset records quite balanced amounts of the 5 boroughs. Bronx, Brooklyn and Manhattan each have about 15000 records in total, and Queens and Staten Island each have about 12000 -- Good news, isn’t it?

Then let’s see the composition in each year. See the two figures below: One about each borough’s number of responses each year, and the other about the proportion each borough takes up.
![IMAGE](/part_1/part_1_3.svg/)
![IMAGE](/part_1/part_1_4.svg/)

The 5 boroughs are not equally sampled through the years. The numbers of records in each borough each year show no steady pattern, although the yearly proportion proves that the boroughs are sampled with similar weights through years, which usually Bronx, Brooklyn and Manhatten are sampled more.

# Say Hi to the Students
For any survey on large scale population, we care about the people’s inherent differences and how these differences influence their other features. Hence let’s check on the demographic distribution about the gender, race, and age distribution of the students taking the survey.

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_demographic.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

#### Gender
The dataset contains fairly unbiased distribution on genders, with gender ratio approximate to 1:1 for each borough, except that Manhattan shows a slightly higher proportion of female respondants with about 60%.
#### Race
Respondants of the 5 boroughs don't share the same race distribution. Bronx, Manhatten and Queens are dominated by Hispanic/Latino students, while Brooklyn reports more Black/African American participants. To our surprise, Staten Island seems to be the only borough that are mostly comprised of White students.
#### Age/Grade
The dataset is sampled in a similar distribution of age groups across boroughs, where 14-17 year-old participants takes part in the majority. Age 14, 15, 16 and 17 each contributes roughly 20%-25% of the total samples in each borough.
But these are not enough. We have noticed some nuances in race and gender so let’s dive deeper.
You may wonder if the racial distribution of each borough twists in certain years perhaps due to immigrants, and here is the result:
![IMAGE](/part_1/part_1_5_race_year.svg/)

Seeing from the line chart of the four ethnic groups in each borough, the race distribution of each borough remains rather steady through the years. Only few intersections, such as Black/African American with Hispanic/Latino in Brooklyn and White with Hispanic/Latino in Staten Island are shown, implying small fluctuations of the racial diversity.
And further on age. Is YRBSS tested on all grades equally, or biased by the samples? Let’s see the grade distribution:
![IMAGE](/part_1/part_1_6_grade.svg/)

The grade distribution is also the same across boroughs. The dataset is of high school students, so grade 9-12 are evenly sampled in all 5 boroughs.
You may then wonder is there any chance that kids in one borough is so clever that they enter the school earlier than other places? Well, the answer is no! See the distribution line chart below:
![IMAGE](/part_1/part_1_7_grade_age.svg/)

It can be seen that in all boroughs, grade 9 students are centered around 14 years old, grade 10 around 15 years old, and so on and so forth. There are no signs of early or late schooling in any borough, because their pattern of grade-age distribution is almost the same.

# Shew – Smoke!
## Smokin’ Hot
YRBSS records multiple tobacco related questions, so first thing first—how many high school students actually tried smoking in each borough? See the lively, colorful map below:

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/50f6706abd698d57bd6bcf39310a7a4ab25abde4/static/part_1/part_1_pct_smokers.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

Through all the recorded years, Staten Island and Queens reported more high school smokers - nearly 30% of high school students have tried smoking. Smoking alert!
Bronx, Brooklyn and Manhattan have a similar level of high school smokers, which is lower than the forementioned two boroughs, at about 22%.

## Smokin’ Hot Everyday
For these students who have tried smoking, are they already live with cigarettes or just happen to have tasted it? Let’s see how many days they smoke in the last month:

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/70866bdfd5d2d05a6797ccfad3eb632e7cddcfee/static/part_1/part_1_days_smokers.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

Good news: In all boroughs, around 1/3 of the smokers only smoke occasionally, corresponding to the option 1 or 2 days in the last month. In Brooklyn and Manhattan the proportion is even larger, up to over 40%.
Both Queens and Staten Island reported significantly more smokers who smoke on over 20 days in a month. In particular, Staten Island seems to be the hot zone of heavy smokers, with smallest percentage of those who only smoke 1 or 2 days and largest percentage of those who smoke on all 30 days. In fact the percentage (and absolute number, too) of day-to-day smokers in Staten Island is so large that it doubles that of Manhattan.
Bronx shows a higher percentage of those who have smoked for 3 to 5 days. Be careful! These students are likely to more than just curious about cigarettes -- they are forming a habit of smoking!
The distribution can also bee seen with the bar chart below:
![IMAGE](/part_1/part_1_10_1_days_smoke_pct.svg/)

## Infinitely Smokin’ Hot
YRBSS also asked the students how many cigarettes per day do the students smoke, and surprisingly their options extend to even 20 cigarettes per day! Cigarette, why can’t you just leave that kid be?
<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_cigarettes_perday_smokers.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

Again on heavy smokers -- Stanten Island win! Over 10% participants smoked more than 10 cigarettes per day, while less than 50% consume up to 1 cigerette daily.
Other 4 boroughs all have more than 50% participants smoking less than 1 cigerette, and more than 85% participants no more than 5 a day.
Manhattan reports the largest percentage of students smoke no more than 1 cigerrete per day and the smallest percentage of smoking more than 5 cigerattes per day.
See also the bar chart to get a feel about how many cigarettes the kids are smoking:
![IMAGE](/part_1/part_1_11_1_per_day_pct.svg/)

## Young and Beautiful, Really?
See one thing we care the most: when do these high school students start smoking? Through the years the results are a little stunning, that quite a few smoked their first puff even before 8 years old:
![IMAGE](/part_1/part_1_12_smoke_age_distr.svg/)

Surprisingly, Bronx have significantly larger percentage of students who start smoking before 8 years old, which is about 30%. What's more, the distribution in Bronx is obviously asymmetrical, which leans expands more to younger groups.
Manhattan has a great proportion of almost 40% of smokers picking up smoking at 13 or 14 years, and compared to other 4 boroughs, an overall older age of smoking acquisition.

# How Time Flies!
Back in 2007, the high school students were territories of the millennials, but those days are gone, and Gen-Z kids are the new trends. With a great change of the whole society and life style, YRBSS also recorded changes of smoking behaviors through the years. Most importantly, fewer and fewer teenagers would try to smoke in the first place. See the slope all along the years:

![IMAGE](/part_1/part_1_13_time_smokers.svg/)

You can get a more vivid feel of how this changes through time:

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/678ae15f6bef1110c14b703e867ca87dab55c8c6/static/part_1/part_1_year_smoking_percentage.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

The high school students' smoking rate in all boroughs slide down quickly with time, starting from around 40%-50% in 2007 to around 10% in 2019. The slope remains steady for Bronx, Brooklyn and Manhattan, where the smoking rate decreases almost the same each year, while Queens were in a plateau in 2011-2015, and Staten Island went through a plummeting period in 2009-2011 and a remains stable after 2017.
Queens and Staten Island have retained a high smoking rate through most years, and both landed on slightly higher smoking rate in 2019 than other 3 boroughs. Recall that these are also sufferers of heavy smokers and early smokers, it should really raise a flag.
How about those strongly addicted students reporting that they could smoke more than 10 cigarettes a day? See the line chart or play around the map below:
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

The USA CDC have defined an indicator on top of q33 results, demonstrating the proportion of people who smoke more than 10 cigarettes per day among smokers.
There is a sharp decrees from 2017 to 2019 in Queens.
Manhattan remains the lowest heavy smoker rate through the years.
Heavy smoker rate fluctuates mildly in Brooklyn, with an average of about 10%.
The heavy smoker rate in Staten Island and Bronx in general raises through the years. This phenomenon partly originated from the decrease in total number of smokers within these boroughs through the years.

# E-cigarette Is Also Cigarettes
YRBSS also recorded behaviors on variations of nicotine products such as cigars, chewing tobacco, and new-born products like e-vapor. We wonder if they are all related to regular cigarette, and come and check the plots below of the age distribution of smoking e-vapors and cigars and alike:
![IMAGE](/part_1/part_1_15_other.svg/)

The patterns of days of smoking e-vapor and cigars per month don't differ much between boroughs, except that in Staten Island there is significantly more students obsessed with e-vapor and smoke it every day.
And we also care about how much smoking one product is related to smoking another, and here are some correlation matrix plots between products:
![IMAGE](/part_1/part_1_16_correlation.svg/)

Smoking regular cigarettes, e-vapor products and cigars and alike are not strongly correlated, which means that smoking one type of product doesn't imply smoking other two products, and smoking one product very often in the last month doesn't necessarily imply smoking other two also that often.
- The frequency of smoking different products among smokers are higher correlated than that of among the whole population, indicating the possible predictability within smokers.
