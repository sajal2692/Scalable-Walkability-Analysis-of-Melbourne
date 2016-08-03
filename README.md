# Scalable Walkability Analysis of Melbourne
Repository for my final semester computing project at the University of Melbourne, under the supervision of Dr. Richard Sinnott. 

## Purpose
 'Walkability Index' of a suburb measures how 'walkable' a given neighborhood is, in terms of road connectivity, population density, and land use mix. 
 
 Using data from Australian Urban Research Infrastructure Network's (AURIN) e-infrastructure, this project explores possible statistical and spatial analysis of large scale areas (in our case, Inner Melbourne), by breaking them down into smaller chunks, and aggregating them during analysis. The approach allows us to calculate, and present the walkability metric for intuitively understandable areas like suburbs or greater regions. 

## Smaller chunks?
The idea of breaking down and aggregating regions is based on the concept of Statistical Areas (SAs) in Australia. Defined by the Australian Bureau of Statistics, SAs can be represented as:

* **Statistical Areas Level 1 (SA1s):** The smallest units (atleast for purposes of Census data), SA1s have a population of 200 to 800 persons, averaging at about 400. 
* **Statistical Areas Level 2 (SA2s):** Built up from SA1s, SA2s are general purpose medium sized areas. They represent a community (or, say, a suburb) that interacts socially and economically. SA2s have an average population of about 10,000 persons. 
* **Statistical Areas Level 3 (SA3s):** Built up from SA2s, SA3s provide a standardized regional breakup of Australia. They have populations of about 30,000 to 130,000 persons and are often used to represent regional cities.
* **Statistical Areas Level 4 (SA4s):** These are the largest sub-state regions and are built up from SA3s. There are 88 SA4s in Australia.

#### Why? 
AURIN's 'Walkability Workflow' is the process which is used to generate the walkability data for a given area. Calculating the walkability of a neighborhood is a resource intensive task, the cost of which, in terms of time and computations, increases with the area of the neighborhood (say, SA4). This is because the workflow involves computationally expensive tasks including 'road network traversal' in all possible directions in a given area. 

At the time of this project, AURIN's system was unable to handle processing of large areas in an acceptable time limit. 

#### So... 
Aggregating the SA1s that are contained within an SA2, we can represent that SA2, without extra computational costs on the AURIN systems. We can also group together SA1s to represent SA3s or even SA4s. Similarly, we can aggregate the results (obtained from the walkability workflow), to give a walkability score to larger regions. 

For this project, we decided to take the mean of the walkability indices of SA1s to represent the SA2s, SA3s, and SA4s that they belong to. A very basic approach, but it opens the doors to large scale analytics, once the SA1s have been processed (in parallel if possible, but this is a data analysis project, so no details on that here).

As an advantage, we can use AURIN's public health, transportation, economic value data for SA2s, which we'll correlate with the walkability scores for more insight!

## Notebooks and Analyses
The project includes the following notebooks (data manipulation and analyses):

* [Walkability Index Bar Plots for Melbourne Suburbs](https://github.com/sajal2692/Scalable-Walkability-Analysis-of-Melbourne/blob/master/Walkability%20Index%20Bar%20Plots%20for%20Melbourne%20Suburbs.ipynb)
* [Choropleth Map Visualisations for Melbourne](https://github.com/sajal2692/Scalable-Walkability-Analysis-of-Melbourne/blob/master/Choropleth%20Map%20Visualisations%20for%20Melbourne%20Suburb%20Walkability.ipynb)
* [Merging Social-Economic Features with Walkability Indices](https://github.com/sajal2692/Scalable-Walkability-Analysis-of-Melbourne/blob/master/Merging%20Socio-Economic%20Features%20with%20Walkability.ipynb)
* [Walkability Index Correlations with Socio-Economic features](https://github.com/sajal2692/Scalable-Walkability-Analysis-of-Melbourne/blob/master/Walkability%20Index%20Correlations%20with%20Socio-Economic%20Metrics.ipynb)
* [Spatial Autocorrelations for Melbourne Suburbs](https://github.com/sajal2692/Scalable-Walkability-Analysis-of-Melbourne/blob/master/Spatial%20Autocorrelations%20for%20Melbourne%20Suburbs%20and%20Neighbours%20.ipynb)
* [Melbourne - Sydney Walkability Comparisons](https://github.com/sajal2692/Scalable-Walkability-Analysis-of-Melbourne/blob/master/Melbourne%20-%20Sydney%20Walkability%20Comparisons.ipynb)

The code, including its result, relevant to a particular topic is described in its notebook. It is recommended to view the notebooks in the above order to avoid missing out on code explainations.

## Tech

The following technologies were used for this part of the project:

* **Python 2**
* **iPython Notebooks:** For interactive code development and result presentation.
* **Pandas:** Python package for data analysis.
* **Matplotlib and Seaborn:** Python 2D plotting library.
* **Leaflet Maps + Folium:** Python package for building choropleth-maps.

--- 

Note: Choropleth maps are available in the choropleth-map directory as html files, and should be downloaded to be viewed (as they are not inherently rendered in an iPython notebook). 
