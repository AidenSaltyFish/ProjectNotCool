---
title: 'Part II : High Schools, Retailers and More'
date: 2022-05-08
description: Geographically based, part II targets to demonstrate the spatial distribution of high schools and that of registered tobacco retailers. Overviews of high schools and tobacco retailers in NYC with respect to each borough will be presented in an interactive way. We will discuss the relation at the end of this part via geographical data analysis.
---

# Introduction
One natural thought when comes to the factors contributing to youth tobacco issue would be like: students of schools in the areas with more tobacco retailers must have easier accesses to the cigarettes -- since schools are closer to retailers -- hence are more likely to be tempted. But are the high schools in the boroughs with higher retailer rate really closer to the retailers? We are trying to analysis the geographical pattern of high schools and registered tobacco retailers in this part.

Geo-plot doesn't show the map? Don't panic! Click the top-right button on each plot and choose a map tile layer!

# Overview of High Schools in NYC
First let’s go with the spatial of high schools in NYC and their scores under a given scoring system.

## Geographical Distribution
Bar chart below shows the number of high schools in each borough.
![IMAGE](/part_2/part_2_high_school_distribution_borough.svg/)

An overview for distributions of high schools and population in NYC with respect to five boroughs. You can play with the layers using the button on the right top corner.

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/5a0a99e585d0aa5e42b05e258423eb4c35aa1045/static/part_2/part_2_high_school_overview.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

## Comments
With outstanding amount of schools as well as decent population, Bronx and Manhattan make themselves the best boroughs when comes to the number of school per capita in the borough. Things become a little messy in Queens and Brooklyn. Given top population among boroughs, citizens may have to live  with the fact that getting education nearby would be challenging due to fair expectations on competition.

## School Scoring
### Framework: six elements
1. Rigorous Instruction
2. Collaborative Teachers 
3. Supportive Environment
4. Effective School Leadership,
5. Strong Family-Community Ties
6. Trust

### Methodology
The following process is used to generate a survey element score:  
1. (1) Question-level percent positive (percentage of positive responses to a
question)  
2. (2) Measure-level percent positive (average of the question-level percent
positive values for all questions within the measure)   
   3. (3) Measure score (score based on the measure-level percent positive)
   > Scaling Method:  
       **Rating Category | Percent  Positive (PP) Cut Level**  
       4.99 Top of Scoring Range |
       citywide mean + 2 SD, not to exceed 100  
       4.00-4.99 Exceeding Target (4 bars) |
       citywide mean PP + 0.75 SD, not to exceed 95   
       3.00-3.99 Meeting Target (3 bars) |
       citywide mean PP – 0.5 SD, not to exceed 90  
       2.00-2.99 Approaching Target (2 bars) | citywide mean PP – 1 SD, not to exceed 85  
       1.00-1.99 Bottom of Scoring Range | citywide mean + 2 SD, not to fall below 0

3. (4) Survey element score (average of measure scores for all measures within
the element)

For more information, please check [this website](https://infohub.nyced.org/docs/default-source/default-document-library/framework-school-survey-scoring-technical-guide.pdf).

### Choose Elements:  Supportive Environment
- M1 **Classroom behavior**  
  - q6a, q6b, q6c, q6d, q6e
- M2 **Guidance**  
  - q9a, q9b, q10a, q10b, q10c, q10d, q11a, q11b
- M3 **Peer support for academic work**  
  - q6f, q6g, q6h, q6i
- M4 **Personal attention and support**  
  - q3a, q3b, q3c, q3d, q3e
- M5 **Preventing bullying**  
  - q8a, q8b, q8c, q8d, q8e
- M6 **Safety**  
  - q4h, q7a, q7b, q7c, q7d

### Visualization
Bar plot counting the answers for previous questions shows below.
![IMAGE](/part_2/part_2_score_on_items.svg/)

Here shows a yearly changed school scoring geo-plot for each borough. Drag the slider bar on the top to check the score changes in year 2017, 2018 and 2019. Date and month can be safely ignored as it is a necessity for generating the time series plot.

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/5a0a99e585d0aa5e42b05e258423eb4c35aa1045/static/part_2/part_2_school_score_yearly_change.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

## Comments
Gladly we are seeing a period of change when the score for high schools in each borough are mostly increasing. This implies a positive trend where the environment becomes more supportive for students in NYC.


# Overview of Registered Tobacco Retailers in NYC
New it's time to check the retailers' geographical distributions.

## Geographical Distribution
When comes to number of retailers, it is not surprised that NYC has a huge amount of tobacco retailers in total. Bar chart below shows the number of registered tobacco retailers in each borough.
![IMAGE](/part_2/part_2_retailer_distribution_borough.svg/)

Check the geographical information of legally registered tobacco retailers using the map below. You can click the button on top-right of the map for different information related to retailers. By default, you will be looking at the heatmap describing the retailer distribution.

<iframe 
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/5a0a99e585d0aa5e42b05e258423eb4c35aa1045/static/part_2/part_2_retailer_overview.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

## Comments
 Given the knowledge that Manhattan ranks as the most famous and recognizable borough in NYC with Wall Street lies on, this borough enjoys the most intense distribution of legal tobacco retailers, seen from both heatmap and per 100k capita plot. Bronx, with the highest crime rate in NYC, keeps its population mild, hence a rather lower density for retailers in this borough than you might expect. This phenomenon also shows less relation between the crime rate with legal tobacco retailer density.

# Are They Related?
At the end of this part, we would like to come back to the question: are the high schools in the boroughs with higher retailer rate really closer to the retailers? 

We defined retailer-high-school ratio as the ratio between the number of retailers and number of high schools. This ratio is defined to describe the density of retailers in each borough and serves the purpose as a general criteria for measuring the rate of retailers in this borough. The closeness between high school and retailers is determined by the mean distance from each high school to its closet five retailers.

## Statistical Information
Mean distance from high schools in each borough to their nearest five retailers are presented statistically below.
![IMAGE](/part_2/part_2_mean_dist_bar.svg/)
![IMAGE](/part_2/part_2_mean_dist_box_kde.svg/)

## Geographical Information
As usual, top-right button on the map offers you more options to review. By default, you are viewing the retailer-high-school ratio in each borough, and the mean distance from each high school to its nearest five retailers, shown by the radius of each circle.

<iframe
    src="https://rawcdn.githack.com/AidenSaltyFish/ProjectNotCool/5a0a99e585d0aa5e42b05e258423eb4c35aa1045/static/part_2/part_2_school_vs_retailer.html"
    sandbox="allow-same-origin allow-scripts"
    width="100%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>


## Comments
Seen from bar plots and box plot and generally speaking, Staten island possesses the longest mean distance and also the largest variance, while Manhattan, on the other hand, enjoys the shortest for both. Roughly scanning the map, you would find that high schools on Staten Island shares a large mean distance to its nearest retailers and in Manhattan the mean distance is short. All are just as statistical plots show.

Interestingly, inverse relation is told by the geo-information. Staten Island, on the one hand, has a large mean distance to its nearest retailers. On the other hand, the retailer/school ratio is highest among all the boroughs here; you can also check the counter-intuitive phenomenon in Manhattan, where the mean distance is kept short with a low retailer/school ratio.

We can dive into the phenomenon from another perspective. Please switch the map to markers of high schools and heatmap for retailers by clicking top-right button on the map and ticking these two layers. On Staten Island, things could attribute to the uneven and unmatched distribution between school and retailers. Most of the retailers, seen from heatmap, are located in the north, while some high schools locate themselves away from north, in the middle or even south of the island. As for Manhattan, though with a lower retail/school ratio, the distribution patterns for them are geographically similar, resulting in a much smaller mean distance from schools to retailers.

Both mean distance to retailers and retail/school ratio cannot be solid criteria for school scoring, since the calculation does not involve the relationship between schools and legal tobacco retailers. However, out of reasonable suspect, we will go deeper into the problem in the next section using machine learning model via random forest algorithm.
