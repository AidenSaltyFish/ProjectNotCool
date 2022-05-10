---
title: 'Outline'
date: 2022-05-06
menu:
  main:
    name: "Outline"
---

# ReadMe
This is a course project in fulfillment of requirement of [course 02806, Social data analysis and visualization of Semester Spring 2022, in Technical University of Denmark](https://github.com/suneman/socialdata2022/wiki).

This website is developed via Hugo, with [template from Robert Austin](https://github.com/zerostaticthemes/hugo-winston-theme) and edited a little with love by Kewei Du.

ProjectNotCool is fully open-source. Please visit the [Github page](https://github.com/AidenSaltyFish/ProjectNotCool) for more information.

# Structure
Project NotCool contains three main parts. Each part holds a topic based on different perspective.

## [Part I : Youth, Tobacco and More]({{< ref "../posts/part_1.md" >}})

## [Part II : High Schools, Retailers and More]({{< ref "../posts/part_2.md" >}})
Geographically based, part II targets to find out the relation between the spatial distribution of high schools and that of registered tobacco retailers. Overviews of high schools and tobacco retailers in NYC with respect to each borough will be presented in an interactive way. We will discuss the relation at the end of this part via geographical data analysis.

## [Part III : Engine Starts]({{< ref "../posts/part_3.md" >}})


# DataSets
Tobacco control is always a heated topic within sustainability, especially the smoking behaviors among teeangers. It is part of the UN's sustainable goal to regulate the average age of tobacco users, and to avoid teenagers to smoke with full care and support.

In this project we are going to analyze NYC high school students' smoking behaviors, and to be more specific, how old are they do they start smoking. To dive deep on this issue, we combined three open dataset: the USA Youth Risk Behavior Surveillance Survey results, the NYC School Survey results, the 2019 NYC high school directory, and 2019 NYC licensed tobacco retailers.

The first two are survey results gathered from students, where YRBSS dataset contains in total 500,000 high school students' individual responses every other year from 1991 to 2019 all across USA, and NYC School Survey gives statistics of over 1000 schools of 5 boroughs in NYC every year aiming to evaluate the school's quality. With NYC high school directory we can focus on the high schools students only, and tobbaco retailers help to further expand our vision to see how commercialization of tobacco relates to exact smoking behaviors of teenagers.

To operate on a sufficient dataset, we extracted YRBSS results from 2007, because NYC School Survey started from 2007, and the NYC school survey in 2017 to 2019 because questions and answers have been consistent within these three years.

The data cleaning and preprocessing procedures are scattered through the following sections, including but not limited to filter needed columns, encoding boroughs and binarize values. Please refer to the specific section to see what we have done on these datasets and some basic stats.

# References
E. Segel and J. Heer, "Narrative Visualization: Telling Stories with Data," in IEEE Transactions on Visualization and Computer Graphics, vol. 16, no. 6, pp. 1139-1148, Nov.-Dec. 2010, doi: 10.1109/TVCG.2010.179.

# Main Libraries
pandas | geopandas | shapely | numpy | matplotlib | seaborn | folium | Bokeh

# Genre
Built on the *Magazine* and *Annotated Graph* genres introduced in Segal and Heer paper, we applied several methods on visual presentation and narrative presentation to better help us tell an attractive and logical story.

### Visual Presentation
We believe that good visual presentation could facilitate readers understanding our intention hiding in the context. For instance, heavily relying on geo-plot to demonstrate information with respect to boroughs, the project introduces many interactive geo-plots plotted via *folium* library. In these plots, readers are able to interact by changing map tiles and data layers to combine the information they prefer. Other examples can also be found in plots from *Bokeh* library.

We also value the power of design. we would like to present our project on a simple, bold, powerful or even little aggressive website. Starting from an open-source template, we made decent modifications to achieve the desired visual effect as presented. With a you-can-not-miss-it title, readers could be attracted by the article even at a quick glance.

### Narrative Presentation
Separated into three parts, the project attempts to keep the information taken by readers in a fair amount on every reading. Each part on an individual but connected topic contains consistent and not too much information. Provided with detailed outline, readers can customize their reading experiences. 

# Visualization
visualization in the project varies from static plots to interactive plots, from statistical plots to plain figures. We will discuss the choice of visualization in this section.

### Geo-plots
All geo-plots in the project in implemented with *folium* library. A typical geo-plot in the project should have layers whose visibility is customizable to readers by clicking the embedded layer button on the map. 

Choropleth plot appears most frequent in the layers, as one of the most common geo-data structure we were facing is the value distribution with respect to the five boroughs in NYC. Choropleth plot can precisely describe the geographical distribution using distinguishable colors. 

Markers are used only once for marking high school locations on the map. They are effective when comes to demonstrating exact locations of a dataset in a small scale on the map. However, things become messy when you try to mark too many locations on the map due to their memory consuming nature. Our machine died once for running more than 4,000 retailers markers on the map. That is also the reason we limit its usage.

Heatmap provides readers with straight and decent experience, which is the perfect choice for identifying where something occurs, and demonstrate areas of high and low density. We used heatmap for describing the retailer distribution and density. We found that heatmap shows its excellence also at the time when plotting the exact location is not important, or not possible: it does a good job leaving readers with quick impressions.

Combined with a time slider bar, choropleth in time series offers a power tool for visualization over time. Dataset with data from multiple years are shown with this type of visualization mostly. Through dragging the top bar, readers can check the differences across the timescale.

### Statistical Plots
Statistical plots are implemented in various ways. *Bokeh* library is applied for making interactive plots in particular.

The stacked bar plot, with fixed vertical length and flexible partial length for each element representing the accounted portion, makes itself much repetitive appearance in Part I. This type of plot offers an easy way for readers to compare among data from different items, say boroughs, while sometimes people may think pie chart is a little clumsy when comes to compare across.

Classic bar plot and line chart are always solid. Box plot gives a visual summary of the data , through which readers can quickly identify mean values, the dispersion of the data set, and signs of skewness. It is useful when we are talking about data distributions.

# Discussion
### What Is Good
Franking speaking, we are satisfied with the topic of the project. Having had a friend who addicted himself to cigarette, we are happy to have the chance to dig into a problem that we actually care about. 

About the project contents, we do believe that it contains a large volume of work with decent analysis on three individual topics related to the project. In total ... . We do appreciate our time spent on the project by generating better analysis and reading experiences.

Diving into the data is always the toughest part, and we have successfully cracked the mystery inside with plenty of labor understanding them. Some data came in the form of questionnaire, where
we had to pay extra work finding the explanation to each answer. To make things worse, data from different years came with different sets of answer, for which we had to do a large amount of data cleaning and merging.

Given large amount of visualization, we did a nice job delivering them in a variant and interactive way. 

Abundant explanatory texts also ensure that readers can reach our insight in a fast pace. 

### What Is To Improve
