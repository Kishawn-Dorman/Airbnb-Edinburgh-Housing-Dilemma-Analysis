# Data-Mining-&-Analysis-Project
In this project, recommendations and insights are generated to tackle the problem described in the section to follow (i.e. About the project). Firstly exploratory data analysis was used on the "Listings" dataset [can be found here](http://insideairbnb.com/get-the-data). 
I then perform data preparation (which involves data cleaning, variable reduction, variable creation) using Microsoft Excel. 
Lastly using Python a cluster analysis is executed, followed by a decision tree (classification model) to classify a type/group (cluster) Airbnb hosts in Edinburgh that maybe engaged in illegal short term rental.

## About the project
“Airbnb offers you someone’s home as a place to stay instead of a hotel” (Rawes & Lacoma, 2021). This simply concept was seen as an opportunity for travellers to have cheaper accommodation prices and for home owners to monetize unused extra housing space. More than that Airbnb’s concept and popularity has made them become a fierce competitor for hotels (Atravellersfootsteps, 2017) and has lead them to being lauded by visitors and hosts as the modern temporary accommodation provider. However, there have been some echoes of the indirect impact Airbnbs are having on communities. Resistance from homeowners and residents in communities with Airbnbs has intensified because of the issues below. 

1.	Pressure property owners into “switching from long-term tenancies to short-term rentals”. This may reduce housing availability through increased rent prices and by extension increase housing prices (Guttentag, 2018).
2.	Bring disturbances with noise and mess from large groups (house party bookings) (Salboy Limited, 2022).
3.	Influence the atmosphere and ethos of these communities because of “over-tourism” (i.e. too many visitors) (Gallagher, 2021).

#### Problem Statement
It has been suggested that these impacts are fuelled by Airbnb hosts renting out their residential properties as illegal short-term rentals. To follow up on this report, I've explored data on listings from Edinburgh to provide insights into the hosts in Edinburgh renting out their properties as illegal short-term rentals (consistently like a hotel) rather than legal short-term rentals (occasionally).

## Section 1 - Data Understanding
Edinburgh is a city rich with culture, adventures and an atmosphere hospitable to tourists. This makes it a great place for Airbnbs to thrive as there is sure to be a flow of tourists and travellers throughout the city. The ‘listings’ dataset for this analysis comprises of variables that capture data about the hosts, listings and listing’s neighbourhoods in Edinburgh. The analysis will also be supplemented by a ‘calendar’ dataset that captures the price, availability and booking criteria of 2,955 listings for each calendar day of a listing starting from the 16/12/2022 to 15/12/2023 (1 year). As well as a ‘reviews’ dataset that captures the reviews for each listing. Below is a table showing the numerical values for each dataset.

Table 1 - Datasets

‘Inside Airbnb’ have made data available for many of the cities with Airbnb listings. However, clear cut metrics to indicate if hosts are/are not renting out properties as illegal short-term rentals have not been created. Analysing the variables within the listings dataset will help to derive some insights into the presence of illegal short-term rentals (if any). 

### Summary Statistics

Understanding the data captured for these different variables will be the first course of action to know “the full story” (ICF International Inc., 2020) as this will help derive accurate and quality findings from the analysis. “Data understanding involves accessing the data and exploring it using tables and graphics” (IBM Corporation, 2021). In the table 2 below the variables from the listings dataset are categorized as either ‘class’ (categorical/nominal) or ‘var’ (numeric/interval) and it also displays the summaries statistics for each of these variables.

Table 2 – Summaries Statistics

Figure 1 - Distribution of Interval & Binary Variables

In figure 1, all binary and interval variables except longitude, latitude & last_scraped (as these variables aren’t relevant for the analysis) was graphed as histograms to better gauge the impact of the issues revealed in the summaries statistics. The white bar depicted on some of the charts represents the amount of missing data. 

In addition, the minimum and maximum values displayed for ‘bedrooms’, ‘beds’ & ‘price’ are distant from each other within each of these variables. The charts for these variables and the exact figures seen in table 2 suggest that outliers maybe present. “An outlier is a value that is very different from the other data in your data set” (StatisticsLectures.com, 2012) and because of this any results generated from the analysis can be skewed because outliers affect the mean of a variable. 

The “minimum_nights_avg_ntm”, “minimum nights”, “maximum_minimum_nights”, “minimum_minimum_nights”, “calculated_host_listings_count”, “calculated_host_listings_count entire_homes”, “calculated_host_listings_count private_rooms” and " calculated_host_listings_count shared_rooms” variable charts in figure 1 above, appear to have outliers as well. But, upon interpretation of the description of these variables the contrasting data values may not be unexpected.

The summaries statistics revealed that the data is mainly plagued by the following: 
(i)	24 out of the 75 variables are missing data, 
(ii)	possible outliers for ‘bedrooms’ & ‘price’, 
(iii)	8 out of the 32 class variables have 128+ levels/categories (impractical to carry out an analysis on these variables, data reduction needed).
(iv)	Possible correlation between variables based on figure 1 (variable no. 34-37, 40 47 & 49, 55-62).

### Data Visualisation

Based on the fact that specific geographic location in a country typical has low priced listings in a particular region and high priced listing in another. The neighbourhoods of the dataset listings identify areas that could be susceptible illegal short-term renting. Also this will help to understand the parity and limitations (if any) of this variable in the dataset to better inform the analysis.   

Figure 2

Figure 2 shows that ‘Old Town, Princes Street and Leith Street’ has the most listings followed by ‘Deans Village’ then ‘Tollcross’.  The other segment of the pie chart represents the neighbourhoods with less than 2 percent of the total listings count for Edinburgh. The pie chart shows that listings are somewhat fairly distributed throughout most of the neighbourhoods which does help to discern low and high-end areas however, it will add some validity to the findings from this analysis of listings in Edinburgh neighbourhoods.
	
Figure 3

Figure 4

The other characteristics explored in the dataset was room types and listings prices based on the number of bedroom and room type. Figure 3 shows that the vast majority of listings are either entire homes/apartments and private rooms, and figure 4 shows the average daily price of listings based on its number of bedrooms. 

Based on this it seems that the reports of illegal short-term renting occurring in homes and apartments could be correct. These two types of properties (entire homes/apartment & private rooms) are the most likely to have host doing illegal short term rentals because the number of bedrooms and daily price of these properties are much higher than hotel rooms and shared rooms.


## Skills and tools used
- Exploratory Data Analysis (PCA, Univariate analysis, Bivariate analysis)
- Predictive Analytics
- Prescriptive Analytics
- Python

## Libraries used
- pandas
- numpy

## Want to connect/have a question? 
[Linkedin](https://www.linkedin.com/in/kishawndorman/)

