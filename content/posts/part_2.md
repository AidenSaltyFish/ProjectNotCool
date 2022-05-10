---
title: 'Part II : Retailers and More'
date: 2022-05-08
description: Geographically based, part II targets to demonstrate the spatial distribution of high schools and that of registered tobacco retailers. Overviews of high schools and tobacco retailers in NYC with respect to each borough will be presented in an interactive way. We will discuss the relation at the end of this part via geographical data analysis.
---

# Introduction
One natural thought when comes to the factors contributing to youth tobacco issue would be like: students of schools in the areas with more tobacco retailers must have easier accesses to the cigarettes -- since schools are closer to retailers -- hence are more likely to be tempted. But are the high schools in the boroughs with higher retailer rate really closer to the retailers? We are trying to analysis the geographical pattern of high schools and registered tobacco retailers in this part.

Geo-plot doesn't show the map? Don't panic! Click the top-right button and choose a map tile layer!

# Overview of High Schools
First let’s go with the spatial of high schools in NYC and their statistics with respect to each borough.

## Geographical Distribution
Bar Chart below shows the number of high schools in each borough.
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

## School Scoring
![IMAGE](/part_2/part_2_score_on_items.svg/)

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
With outstanding amount of schools as well as decent population, Bronx and Manhattan make themselves the best boroughs when comes to the number of school per capita in the borough. Things become a little messy in Queens and Brooklyn. Given top population among boroughs, citizens may have to live  with the fact that getting education nearby would be challenging due to fair expectations on competition.


# Overview of Registered Tobacco Retailers
New it's time to check the retailers' geographical distributions, and also their data on each borough.

## Geographical Distribution
When comes to number of retailers, it is not surprised that NYC has a huge amount of tobacco retailers in total. Check the geographical information of legally registered tobacco retailers using the map below. You can click the button on top-right of the map for different information related to retailers. By default, you will be looking at the heatmap describing the retailer distribution.

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
Interestingly, inverse relation is told by the geo-information. Roughly scanning the map, you would find that high schools on Staten Island shares a large mean distance to its nearest retailers, while the retailer/school ratio is highest among all the boroughs; you can also check the counter-intuitive phenomenon in Manhattan and Bronx, where the mean distances are kept short with low retailer/school ratios.

We can dive into the phenomenon from another perspective. Please switch the map to markers of high schools and heatmap for retailers by clicking top-right button on the map and ticking these two layers. On Staten Island, things could attribute to the uneven and unmatched distribution between school and retailers. Most of the retailers, seen from heatmap, are located in the north, while some high schools locate themselves away from north, in the middle or even south of the island. As for Manhattan, though with a lower retail/school ratio, the distribution patterns for them are geographically similar, resulting in a much smaller mean distance from schools to retailers.

Both mean distance to retailers and retail/school ratio cannot be solid criteria for school scoring, since the calculation does not involve the relationship between schools and legal tobacco retailers. However, out of reasonable suspect, we will go deeper into the problem in the next section using machine learning model via random forest algorithm.
