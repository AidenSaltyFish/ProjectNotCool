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

## [Part I : ]({{< ref "../posts/part_1.md" >}})

## [Part II : High Schools, Retailers and More]({{< ref "../posts/part_2.md" >}})
Geographically based, part II targets to find out the relation between the spatial distribution of high schools and that of registered tobacco retailers. Overviews of high schools and tobacco retailers in NYC with respect to each borough will be presented in an interactive way. We will discuss the relation at the end of this part via geographical data analysis.

## [Part III : ]({{< ref "../posts/part_3.md" >}})


# DataSets

# References
E. Segel and J. Heer, "Narrative Visualization: Telling Stories with Data," in IEEE Transactions on Visualization and Computer Graphics, vol. 16, no. 6, pp. 1139-1148, Nov.-Dec. 2010, doi: 10.1109/TVCG.2010.179.

# Main Libraries
- pandas 
- geopandas
- shapely
- numpy
- matplotlib
- seaborn
- folium
- Bokeh

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

# Discussion
### What Is Good
Franking speaking, we are satisfied with the topic of the project. Having had a friend who addicted himself to cigarette, we are happy to have the chance to dig into a problem that we actually care about. 

About the project contents, we do believe that it contains a large volume of work with decent analysis on three individual topics related to the project. In total ... . We do appreciate our time spent on the project by generating better analysis and reading experiences.

Diving into the data is always the toughest part, and we have successfully cracked the mystery inside with plenty of labor understanding them. Some data came in the form of questionnaire, where
we had to pay extra work finding the explanation to each answer. To make things worse, data from different years came with different sets of answer, for which we had to do a large amount of data cleaning and merging.

Given large amount of visualization, we did a nice job delivering them in a variant and interactive way. 

Abundant explanatory texts also ensure that readers can reach our insight in a fast pace. 

### What Is To Improve
