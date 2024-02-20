In this project, recommendations and insights are generated to tackle the problem described in the section to follow (i.e., about the project). Firstly, SAS E-Miner was used to conduct exploratory data analysis on the "Listings" dataset, which [can be found here](http://insideairbnb.com/get-the-data). 

I then performed data preparation (which involves data cleaning, variable reduction, and variable creation) using Microsoft Excel. 

Lastly, using SAS E-Miner, a cluster analysis was executed, followed by a decision tree (classification model) that classifies a type or group (cluster) of Airbnb hosts in Edinburgh that may be engaged in illegal short-term rental.


## Table of Contents

[**About the Project**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#about-the-project) 

[**Overall Flow Model**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#overall-flow-model) 

[**Section 1 - Data Understanding(SAS E-Miner)**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#section-1---data-understanding-sas-e-miner) 
- [**Summary Statistics**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#summary-statistics)
- [**Data Visualisation**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#data-visualisation)

[**Section 2 - Data Preparation (Microsoft Excel)**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#section-2---data-prearation-microsoft-excel) 
- [**Data Cleaning**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#data-cleaning)
- [**Data Transformation**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#data-transformation)
- [**Data Reduction**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#data-reduction)

[**Section 3 - Cluster Analysis**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#section-3---cluster-analysis) 

[**Section 4 - Classification Modelling**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#section-4---classification-modelling) 
- [**Decision Tree**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#decision-tree)
- [**Model Evaluation**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#model-evaluation)

[**Section 5 - Conclusion**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#section-5---conclusion) 
- [**Recommendation**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#recommendation)
- [**Limitation**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#limitation)

[**Skills and Tools Used**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#skills-and-tools-used) 

[**Nodes and Functions Used**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#nodes-and-functions-used)

## About the Project

Resistance from homeowners and residents in communities with Airbnbs has intensified because of the issues below. 

1. Pressure property owners into “switching from long-term tenancies to short-term rentals." This may reduce housing availability through increased rent prices and, by extension, increase housing prices (Guttentag, 2018).
2. Bring disturbances with noise and mess from large groups (house party bookings) (Salboy Limited, 2022).
3. Influence the atmosphere and ethos of these communities because of “over-tourism” (i.e., too many visitors) (Gallagher, 2021).

Problem Statement: **Airbnb hosts are fueling the impacts mentioned above by renting out their residential properties as illegal short-term rentals.**

Objective: **Use host and listing characteristics to identify listings that may be engaged in illegitimate rental.**

## Overall Flow Model

![Screenshot 2023-11-10 211434](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/5794b3b2-383d-447d-9ad9-b713c80790dc)


## Section 1 - Data Understanding (SAS E-Miner)

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/63295d78-b03b-45d5-ba9a-ddb8611cc69b)


### Summary Statistics

Table 1 – Summaries Statistics

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/018df3d2-ff91-46ae-8465-87c46692f523)

Figure 1 - Distribution of Interval & Binary Variables

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/c5ee5890-9240-4b29-9e0b-e2079aa16265)
![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/ef72c8d3-644b-4744-91e9-2c44ed43584f)


Figure 1 shows all binary and interval variables except longitude, latitude, and last_scraped as histograms. The white bar depicted on some of the charts represents the amount of missing data. 

In Figure 1 and Table 1, the minimum and maximum values displayed for ‘bedrooms’ and ‘price’ are distant from each other, thus suggesting that outliers may be present.

The summary statistics revealed that the data is mainly plagued by the following: 
(i) 24 out of the 75 variables are missing data. 
(ii) possible outliers for ‘bedrooms’ and ‘price’. 
(iii) 8 out of the 32 class variables have 128+ levels or categories (it is impractical to carry out an analysis on these variables; data reduction is needed).
(iv) Possible correlation between variables based on Figure 1 (variables 34–37, 40, 47, and 49, 55–62).

### Data Visualisation

Figure 2

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/59419b3b-1aef-4b4e-b6d6-86b938f8c231)

Figure 2 shows that listings are somewhat fairly distributed throughout most of the neighbourhoods, which does help to discern low- and high-end areas. This will add some validity to the findings from this analysis of listings in Edinburgh neighbourhoods.
	
Figure 3

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/8267cdbd-ba8a-4a58-b5e7-71110f8a21f9)

Figure 4

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/e301e605-0c2c-48e1-94df-c8fb2f45d465)

Figure 3 shows that the vast majority of listings are either entire homes or apartments with private rooms, and Figure 4 shows the average daily price of listings based on their number of bedrooms. 
Based on figures 3 and 4, it seems that these two types of properties (entire homes, apartments, and private rooms) are the most likely to have hosts engaged in illegal short-term rentals because the number of bedrooms and daily price of these properties are much higher than hotel rooms and shared rooms.


## Section 2 - Data Preparation (Microsoft Excel)

### Data Cleaning

Table 2 – Deleted Variables

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/1c414011-8e06-473d-98f1-42a5b8af35ad)
 
As identified in the previous phase, the bathrooms_text variable contains missing data. Using the information provided in the description and listing_url variables, the missing data for 13 listings affected within the bathrooms_test variable was filled in via Excel. The missing data in 'bedrooms' (105), 'last_review', and 'reviews_per_month' (same 665 listings) variables was removed (770) from the dataset by filtering the blank observations for each variable and deleting them.

Figure 5 

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/e4ac4c3b-1b2b-4716-b6e9-8d62aaae8de6)


The description variable was once again used for the listings with 'bedroom' outlier values. Based on the information contained in this variable, the 'bedroom' outlier values are indeed accurate and were retained in the dataset. 
On the other hand, the price variable had 6 unverifiable outliers (the price on the listings website page did not correspond with the dataset’s price) and, as such, was removed by filtering out any listing priced under £5,000.

Table 3 – Price Variable Outliers

 ![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/4dd81b16-4311-43a6-87db-b579a1cfc758)

### Data Transformation

Two new variables was created using Excel. 

Figure 6

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/1dacc7a4-c19e-46cc-ab11-e66012693882)

(i) Occupancy Rate (OR) = reviews_per_month x minimum_nights x 12(months) / (365-availability_365) 
The formula for OR was derived from an article from Airbnb (2023) that detailed the occupancy rate as “the number of nights booked divided by the total nights available to be booked.”

Figure 7

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/da844671-f8ed-496b-bc24-d2a833306385)

Occupancy rate variables: 
42 listings had full-365 availability. Since this was the case, the occupancy rate and listing income were set to 0 for these listings. 
1431 listings had 0 availability, so the occupancy rate formula for these listings was changed to "reviews per month x minimum nights x 12 / 365." 

(ii) Listing Income (LI) = occupancy rate x price x 365 The formula for LI was derived from Airbtics (2022). They stated that revenue (listing_income) can be calculated by “multiplying the year-round occupancy rate” with the “average daily rate.”

The majority of the 1431 listings were entire homes, apartments, and private rooms, and on average,'reviews  per month' appear to be under 1 review. Visitors to these listings may have been uninformed about reviews by hosts to avoid detection, as multiple rentals over the span of the year should result in multiple reviews (which are not reflected).

### Data Reduction

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/567bc5b5-91b6-43b2-a802-bafe96977b79)

Following a correlation analysis on the dataset in SAS Enterprise Miner, a few pairs of variables were identified with a correlation above 50%. Out of these pairs of variables identified, the following variables were removed: bedrooms, number_of_reviews_l30d, and number_of_reviews_ltm.

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/d17dc569-13bf-4174-acfb-0635de65f846)

PCA’s outcome from reducing 12 interval variables yielded just 1 less variable at a confidence threshold of 95%. Since only one less variable was generated, the interval variables will be retained over the PC’s for the next phase of the analysis. 

The dataset now comprises the following:

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/c0f02b57-c256-4e12-9c01-acdecad8e9b8)


## Section 3 - Cluster Analysis 

**Variables Used for Cluster Nodes**

![Screenshot 2023-11-10 163034](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/d9eb1c56-6ca3-475d-9be3-4eef1576d024)


A series of clustering techniques was used by adjusting (i) a type of clustering method and (ii) a type of clustering distance property (standardisation or range) in the cluster node settings. Five different clustering settings were used to derive 2–3 clusters with a fairly equal distribution of listings between them.

![Screenshot 2023-11-10 164324](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/458d025b-f55f-47fc-992e-f2788e488351)


**Cluster Results**

![Screenshot 2023-11-10 164813](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/0f0910ff-2ae3-4178-8c92-712aabfc7fb2)

![Screenshot 2023-11-10 165634](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/fb0787a8-3779-4f00-855d-1cfe3f43b1cd)

Based on the mean statistics, the clusters were interpreted as follows: Cluster 1 will be classified as **low-priced listings** because it has the lowest mean listing income and the highest mean maximum nights (hosts may opt for higher maximum nights at a lower price to attract long-stayers with the hope of establishing a source of continuous income for the course of the year). 

Cluster 2 will be classified as **standard-priced listings** because its mean listing income is the median out of the three clusters and has much higher industry-standard maximum nights’ limits in comparison to the other clusters. Although the occupancy rate is marginally higher than cluster 1 (the lowest occupancy rate), it is still very much within the logical occupancy rate of a genuine short-term Airbnb listing. But the mean availability of listings in this cluster was significantly lower than the other clusters, which suggests that on average, these listings may be rented out all year round. 

Cluster 3 will be classified as a **high income-generating** listing because its mean listing income and price are the highest out of the 3 clusters. Their minimum nights value is also the highest (suggest that hosts may charge a lofty price for each booking), the number of reviews is the lowest (since listings are possibly priced the highest, visitors may be very few and, as a result, fewer reviews), and calculated host listings count the highest (suggest that these hosts may be running an accommodation business). 


## Section 4 - Classification Modelling

Based on the clusters and segments generated, segment 2 seems the most likely out of the segments to contain listings involved in illegal short-term rental. With that in mind, this segment will be used along with **a binary (0=no, 1=yes) target variable that represents whether or not a listing is likely to be illegitimately rented out or not** to build a decision tree.  

### Decision Tree

![Screenshot 2023-11-10 223651](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/3694fa5b-960a-4518-8b71-202dc4224255)

![Screenshot 2023-11-10 222839](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/630cdc1a-9b9d-4d1a-9ee1-50ba7e2b9ab8)

![Screenshot 2023-11-10 223514](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/3fd80655-fef2-47d9-874f-32e1fdd921eb)

The default settings for the decision tree node were retained, with the exception of the maximum depth being changed from 6 to 3. Although retaining a higher depth would not necessarily be detrimental to the model results, having a higher depth means lower accuracy in the lower leaf nodes (which does not help the aim of classifying listings with high accuracy).

The decision tree performed well at accurately classifying listings, as the missclassification rate, maximum absolute error, and average squared error rates showed high accuracy and stability across the train, validation, and test data sets and partitions (note: to simulate a supervised and unsupervised environment, the data was split into a "train," "validation," and "test" partition; 40%, 30%, 30%).

![Screenshot 2023-11-10 231514](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/a6403b78-8c15-40b4-a7be-b9efe83133e8)

![Screenshot 2023-11-10 231825](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/d2f2582e-f308-427f-89d7-449248ce88ce)

Although the decision tree model performed well at classification, the variables selected by the algorithm were not great classifiers of illegitimate listings (the accuracy of the decision tree lowers as you progress down the tree). As a result, two decision trees were created with different parameters to change how the algorithm selects variables and classifies those variables in the decision tree. But, unfortunately, this did not yield any meaningful changes towards having strong classifications of illegitimate listings. 

Thus, the original **(Tree Name: "Standard") decision tree** was retained as the classification model.

### Model Evaluation

![Screenshot 2023-11-10 232903](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/bfcf8bd6-686c-46b4-a807-81cd62695d8b)

Five models, including the decision tree, were compared using the model evaluation node. The gradient boosting model was the best as it yielded the lowest missclassification rate (PS: the gradient boosting model performs several iterations (i.e., several decision trees), where at each iteration it learns from the previous, thus gradually reducing the misclassification error). 


## Section 5 - Conclusion

Cluster 1 - Low-Priced Listings
Cluster 2 - Standard-Priced Listings
Cluster 3 - High-Income Listings

Cluster/Segment 2 was chosen as the group of listings likely to comprise illegitimate listings. Although the three clusters generated had different characteristics, it was evident that illegitimate activity from listings in each of these clusters is very much a possibility. 

The decision tree model showed that "occupancy rate,"  "listing income,"  "calculated host listing counts," and "minimum nights" were not great classifications of illegitimate listings based on this data, as the majority of the listings in the train and validation sample groups fell under 0=listing not engaged in illegitimate rental.

![Screenshot 2023-11-11 013424](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/bd1d778c-3929-44ad-a00a-eaf8a9e9b782)

The decision tree did, however, classify some of the listings as 1 (the validity of this classification is limited because of the sample for this aspect of the decision tree).

**Standard-Priced Listings 
->-> occupancy rate of >=54% then 68% chance of it being 1 (illegitimate) 
->-> adding on to the prev listing criteria, if it has listing income >=36,900 or the income is not defined for the listing, 
then 83% chance of that listing being engaged in illegitimate rental.**

### Recommendation

Although the variables used for the classification model had disproportionate sample groups, it revealed that illegitimate rental is very much present among Airbnb hosts. As a course of action, exploring the deployment of a classification model similar to what was created above would certainly help with detecting hosts and/or properties being disruptive and harming Airbnb's ecosystem. The integration and consideration of other variables, like whether or not a host and/or listing have "booking rules" and "guest verification criteria," would certainly present new avenues for detection. 

### Limitation

During the data preparation phase, many issues were found that could undermine the analysis and ultimately the model. A few listings were identified as potentially affected by unusually high price values, as they appeared to be outliers. Although the outliers may have been addressed, the credibility and, particularly, the accuracy of the classification model could still have been affected by hidden data errors. For example, a price value within the average range of the dataset would be more difficult to detect than a price value that is extremely high or low.  

## References

Airbnb, Inc., 2023. How do I read my performance data for occupancy and rates?. [Online] 
Available at: https://www.airbnb.co.uk/help/article/2715/?_set_bev_on_new_domain=1679103185_YTdmMjJhOGUwMjgw
[Accessed 15 May 2023].

Airbtics, LLC. , 2022. How much can I make on Airbnb?. [Online] 
Available at: https://airbtics.com/airbnb-income-calculator/
[Accessed 16 May 2023].

Gallagher, K., 2021. What Is Overtourism and Why Is It Such a Big Problem?:Treehugger. [Online] 
Available at: https://www.treehugger.com/what-is-overtourism-definition-and-examples-5181255
[Accessed 9 March 2023].

Guttentag, D., 2018. What Airbnb really does to a neighbourhood:BBC. [Online] 
Available at: https://www.bbc.co.uk/news/business-45083954
[Accessed 9 March 2023].

Salboy Limited, 2022. A Look at Airbnbs and Their Impact on Local Communities:Salboy Limited. [Online] 
Available at: https://salboy.co.uk/2022/09/a-look-at-airbnbs-and-their-impact-on-local-communities/
[Accessed 9 March 2023].


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

