**Data**

In order to design a coherent spatial analysis experiment, it was necessary to identify the following data as suitable for establishing a statistically significant relationship between the existence of socioeconomic variables (poverty and income) and the subjects’ location throughout the city’s political and administrative districts. In addition to both tabular and spatial data, provided by the American Community Survey, the Department of City Planning and the Census Bureau’s cartographic catalogue, the study selected spatial data available at New Yok City’s Open Data portal. Below, the detailed location of selected data is displayed:

•	Total Population by census tract (Tabular data-ACS 2009-2012 American Community Survey).

•	Census tract Shapefile for New York City (Spatial data -Census Bureau Cartographic boundaries and products) 

•	LinkNYC locations (Tabular data-NYC open data)

•	MapPLUTO Shapefile (Spatial data -Bytes of the Big Apple)

•	Internet Use (Tabular data-ACS 2014 estimates).

•	Poverty (Tabular data-ACS 2009-2012 estimates)

•	Mean income in the past 12 months (in 2014 inflation-adjusted dollars) Tabular data-ACS 2009-2012 five year estimates.

With the inclusion of computer/internet use questions as part of the American Community Survey-ACS, estimates have been created for several geography levels and for a wider segment of the American population. However, the design of the survey’s questionnaire could generate biased results. 

The American Community Survey’s computer/internet use data contains estimates on more than 3.5 million addresses, located only at eligible geographies. Only locations with populations over 65,000 were surveyed, disregarding smaller geographies in terms of their population sizes. Additionally, the self-reporting nature of the survey relied on households’ members’ knowledge on the type of computer owned (desktop, handheld or other) and/or about the presence/specifications of an internet subscription (Digital subscriber Line-DSL or cable-modem service) originating a survey bias. 

Lastly, it is also necessary to state that all utilized ACS data acknowledges a sampling error. Given the fact that these datasets contain estimates based on samples rather than on values for total population, a margin of error is calculated for all values contained in the data.   

**Data wrangling and processing**

The original design of this study required extensive data cleaning and processing, as it aimed to merge both spatial and tabular information. The first step was to manipulate the LinkNYC kiosk location data, as the purpose of this portion of the project was to plot the number of Links by community board. A loop was implemented both to display only the numerical portion of the Link identification code ('CB Link ID') and to omit the word “LINK” (See figure 1).

In subsequent steps, and after obtaining ACS-Computer use data, the original information in the format: CITY-Borough-Community District number-PUMA Name-City, was replaced by the traditional borough name, followed by the community board number, and the column name was changed from “Qualifying name” to “Community district” (See figure 2). Lastly, duplicates were dropped and panda’s integer-location based indexing tool (. iloc) was utilized to define internet use as the “households with an internet subscription”. 

A similar procedure was applied for the demographic data, provided by the course’s website. All values contained under the community board id were processed and all duplicates, were dropped. Finally, all columns’ names were changed in order to prepare all data sets for a merging based on the “community district” column (See figure 3). 

The last portion of the data processing stage, involved the conversion of selected values from the spatial data into numerical values. For this task, professor Bianco’s “cancovert” function was utilized to identify the number of entries with the capacity to be converted into float values. After applying this procedure, both poverty tabular data and census tract spatial data were merged based in the “GEOID” column (See figure 4).
