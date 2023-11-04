# Data-Mining-&-Analysis-Project
In this project, recommendations and insights are generated to tackle the problem described in the section to follow (i.e. About the project). Firstly SAS E-Miner was used to conduct exploratory data analysis on the "Listings" dataset [can be found here](http://insideairbnb.com/get-the-data). 
I then perform data preparation (which involves data cleaning, variable reduction, variable creation) using Microsoft Excel. 
Lastly using SAS E-Miner, a cluster analysis will be executed, followed by a decision tree (classification model) to classify a type/group (cluster) Airbnb hosts in Edinburgh that maybe engaged in illegal short term rental.

Resistance from homeowners and residents in communities with Airbnbs has intensified because of the issues below. 
1.	Pressure property owners into “switching from long-term tenancies to short-term rentals”. This may reduce housing availability through increased rent prices and by extension increase housing prices (Guttentag, 2018).
2.	Bring disturbances with noise and mess from large groups (house party bookings) (Salboy Limited, 2022).
3.	Influence the atmosphere and ethos of these communities because of “over-tourism” (i.e. too many visitors) (Gallagher, 2021).

## Problem Statement
Airbnb hosts are fuelling the impacts mentioned above by renting out their residential properties as illegal short-term rentals. 


## Section 1 - Data Understanding (SAS E-Miner)
Edinburgh is a city rich with culture, adventures and an atmosphere hospitable to tourists. This makes it a great place for Airbnbs to thrive as there is sure to be a flow of tourists and travellers throughout the city. The ‘listings’ dataset for this analysis comprises of variables that capture data about the hosts, listings and listing’s neighbourhoods in Edinburgh. 

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/63295d78-b03b-45d5-ba9a-ddb8611cc69b)

### Summary Statistics

Table 1 – Summaries Statistics

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/018df3d2-ff91-46ae-8465-87c46692f523)

Figure 1 - Distribution of Interval & Binary Variables

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/c5ee5890-9240-4b29-9e0b-e2079aa16265)
![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/ef72c8d3-644b-4744-91e9-2c44ed43584f)


Figure 1 shows all binary and interval variables except longitude, latitude & last_scraped as histograms. The white bar depicted on some of the charts represents the amount of missing data. 

In figure 1 and table 1 the minimum and maximum values displayed for ‘bedrooms’ & ‘price’ are distant from each other, thus suggests that outliers maybe present. “An outlier is a value that is very different from the other data in your data set” (StatisticsLectures.com, 2012).

The summaries statistics revealed that the data is mainly plagued by the following: 
(i)	24 out of the 75 variables are missing data, 
(ii)	possible outliers for ‘bedrooms’ & ‘price’, 
(iii)	8 out of the 32 class variables have 128+ levels/categories (impractical to carry out an analysis on these variables, data reduction needed).
(iv)	Possible correlation between variables based on figure 1 (variable no. 34-37, 40 47 & 49, 55-62).

### Data Visualisation

Figure 2

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/59419b3b-1aef-4b4e-b6d6-86b938f8c231)

Figure 2 shows that listings are somewhat fairly distributed throughout most of the neighbourhoods which does help to discern low and high-end areas. This will add some validity to the findings from this analysis of listings in Edinburgh neighbourhoods.
	
Figure 3

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/8267cdbd-ba8a-4a58-b5e7-71110f8a21f9)

Figure 4

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/e301e605-0c2c-48e1-94df-c8fb2f45d465)

Figure 3 shows that the vast majority of listings are either entire homes/apartments and private rooms, and figure 4 shows the average daily price of listings based on its number of bedrooms. 
Based on figure 3 and 4 it seems that these two types of properties (entire homes/apartment & private rooms) are the most likely to have hosts engaged in illegal short term rentals because the number of bedrooms and daily price of these properties are much higher than hotel rooms and shared rooms.


## Section 2 - Data Preparation (Microsoft Excel)

### Data Cleaning

Table 2 – Deleted Variables

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/1c414011-8e06-473d-98f1-42a5b8af35ad)
 
As identified in the previous phase the bathrooms_text variable contain missing data. Using the information provided in the description & listing_url variables, the missing data for 13 listings affected within the bathrooms_test variable was filled in via Excel. 
The missing data in 'bedrooms' (105), 'last_review' and 'reviews_per_month' (same 665 listings) variables was removed (770) from the dataset by filtering the blank observations for each variable and deleting them.

Figure 5 

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/e4ac4c3b-1b2b-4716-b6e9-8d62aaae8de6)


The description variable was once again used for the listings with 'bedroom' outlier values. Based on the information contained in this variable, the 'bedroom' outlier values are indeed accurate and was retained in the dataset. 
On the other hand the price variable had 6 unverifiable outliers (price on the listings website page did not correspond with the dataset’s price) and as such was removed by filtering out any listing priced under 5000. 

Table 3 – Price Variable Outliers

 ![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/4dd81b16-4311-43a6-87db-b579a1cfc758)

### Data Transformation

Two new variables was created using Excel. 

Figure 6

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/1dacc7a4-c19e-46cc-ab11-e66012693882)

(i) Occupancy Rate (OR) = reviews_per_month x minimum_nights x 12(months) / (365-availability_365) 
The formula for OR was derived from an article from Airbnb (2023) that detailed the occupancy rate as “the number of nights booked divided by total nights available to be booked”.

Figure 7

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/da844671-f8ed-496b-bc24-d2a833306385)

Occupancy rate variable: 
42 listings had full 365 availability = Since this was the case, the occupancy rate and listing income was set to 0 for these listings. 
1431 listings had 0 availability = thus the occupancy rate formula for these listings was changed to "reviews per month x minimum_nights x 12 / 365". 

(ii) Listing Income (LI) = occupancy rate x price x 365 
The formula for LI was derived from Airbtics (2022). They stated that revenue (listing_income) can be calculated by “multiplying the year-round occupancy rate” with the “average daily rate”.

Majority of the 1431 listings were entire home/apartments & private rooms and on average 'reviews per month' appear to be under 1 review. Visitors of these listings may have been uninformed about reviews by hosts to avoid detection as multiple rentals over the span of the year should result in multiple reviews (which is not reflected).
	
### Data Reduction

Duplicate and repetitive data sometimes go unchecked in the data preparation phase and although they may not hugely impact the final results, performing data reduction will certainly improve the final results by eliminating irrelevant data (Anunaya, 2023). Following a correlation analysis on the dataset in SAS Enterprise Miner, a few pairs of variables was identified with a correlation above 50% (appendix 1). Out of these pairs of the variables identified, the following variables was removed; bedrooms, number_of_reviews_l30d and number_of_reviews_ltm.

Additionally, to further reduce the variables in the dataset a principal component analysis (PCA) was executed on the interval variables. The PCA’s outcome from reducing 12 interval variables, yielded just 1 less variable as 11 new components at the confidence threshold of 95% was generated. Since only 1 less variable was generated and the meanings of the already existing 12 interval variables do not require further interpretation, the interval variables will be retained over the PC’s for the next phase of the analysis. 

The dataset now comprise of the following:



## Skills and tools used
- Exploratory Data Analysis (PCA, Univariate analysis, Bivariate analysis)
- Predictive Analytics
- Prescriptive Analytics
- SAS E-Miner
- Microsoft Excel

## Nodes and Functions used
- Variable Clustering
- Principal Components
- StatExplore
- Cluster Analysis
- Decision Tree
- Model Comparison

- Sort & Filter
- Text to Column
- Formula Bar

## Want to connect/have a question? 
[Linkedin](https://www.linkedin.com/in/kishawndorman/)

