In this project, recommendations and insights are generated to tackle the problem described in the section to follow (i.e. About the project). Firstly SAS E-Miner was used to conduct exploratory data analysis on the "Listings" dataset [can be found here](http://insideairbnb.com/get-the-data). 
I then perform data preparation (which involves data cleaning, variable reduction, variable creation) using Microsoft Excel. 
Lastly using SAS E-Miner, a cluster analysis will be executed, followed by a decision tree (classification model) to classify a type/group (cluster) Airbnb hosts in Edinburgh that maybe engaged in illegal short term rental.

Resistance from homeowners and residents in communities with Airbnbs has intensified because of the issues below. 

1.	Pressure property owners into “switching from long-term tenancies to short-term rentals”. This may reduce housing availability through increased rent 		prices and by extension increase housing prices (Guttentag, 2018).
2.	Bring disturbances with noise and mess from large groups (house party bookings) (Salboy Limited, 2022).
3.	Influence the atmosphere and ethos of these communities because of “over-tourism” (i.e. too many visitors) (Gallagher, 2021).

Problem Statement: **Airbnb hosts are fuelling the impacts mentioned above by renting out their residential properties as illegal short-term rentals.** 


## Table of Contents
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

[**Skills and Tools Used**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#skills-and-tools-used) 

[**Nodes and Functions Used**](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis#nodes-and-functions-used)


## Overall Flow Model

![image](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/60eca701-4ae6-4130-a5bf-576dab3225df)


## Section 1 - Data Understanding (SAS E-Miner)


![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/63295d78-b03b-45d5-ba9a-ddb8611cc69b)

### Summary Statistics

Table 1 – Summaries Statistics

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/018df3d2-ff91-46ae-8465-87c46692f523)

Figure 1 - Distribution of Interval & Binary Variables

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/c5ee5890-9240-4b29-9e0b-e2079aa16265)
![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/ef72c8d3-644b-4744-91e9-2c44ed43584f)


Figure 1 shows all binary and interval variables except longitude, latitude & last_scraped as histograms. The white bar depicted on some of the charts represents the amount of missing data. 

In figure 1 and table 1 the minimum and maximum values displayed for ‘bedrooms’ & ‘price’ are distant from each other, thus suggests that outliers maybe present.

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

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/567bc5b5-91b6-43b2-a802-bafe96977b79)

Following a correlation analysis on the dataset in SAS Enterprise Miner, a few pairs of variables was identified with a correlation above 50% (appendix 1). Out of these pairs of the variables identified, the following variables was removed; bedrooms, number_of_reviews_l30d and number_of_reviews_ltm.

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/d17dc569-13bf-4174-acfb-0635de65f846)

PCA’s outcome from reducing 12 interval variables, yielded just 1 less variable at a confidence threshold of 95%. Since only 1 less variable was generated the interval variables will be retained over the PC’s for the next phase of the analysis. 

The dataset now comprise of the following:

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/c0f02b57-c256-4e12-9c01-acdecad8e9b8)


## Section 3 - Cluster Analysis 

**Variables Used for Cluster Nodes**

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/74c7148d-b55d-48b4-8d0b-91a848d2d861)

A series of clustering techniques was used by adjusting (i) a type of clustering method and (ii) a type of clustering distance property (standardization or range) in the cluster node settings. Five different clustering settings was used to derive 2-3 clusters with a fairly equal distribution of listings between them.

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/14a88be7-28a9-415f-970e-1938a9d9747b)

**Cluster Results**

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/e3d7069b-4244-4afd-8fe2-717ed79a8cb0)

![image](https://github.com/Kishawn-Dorman/Cluster-Analysis-and-Classification-Modelling/assets/146044118/9dac4437-c17e-4a54-b54b-8d49d6ac6002)

Based on the mean statustics the clusters were interpreted as follows. Cluster 1 will be classed as **low-priced listings** because it has the lowest mean listing income and highest mean maximum nights (hosts may opt for higher maximum nights at lower price to attract long-stayers with a hope of establish a source of continuous income for the course of the year). 

Cluster 2 will be classed as **standard-priced listings** because its mean listing income is medial out of the three clusters and had a much more industry standard maximum nights’ limits in comparison to the other clusters. Although the occupancy rate is marginally more than cluster 1 (lowest occupancy rate), it is still very much within the logical occupancy rate of a genuine short-term Airbnb listing. But the mean availability of listings in this cluster was significantly lower than the other clusters, which suggest that on average these listings may be rented out all year round. 

Cluster 3 will be classed as **high income generating** listings because its mean listing income and price are the highest out the 3 clusters. Their minimum nights value is also the highest (suggest that hosts may charge a lofty price for each booking), number of reviews the lowest (since listings are possibly priced the highest, visitors may be very few and as a result less reviews) and calculated host listings count the highest (suggest that these host may be running an accommodation business). 


## Section 4 - Classification Modelling

Based on the clusters/segments generated, segment 2 seems the most likely out of the segments to contain listings involved in illegal short-term rental. With that in mind this segment will be used along with **a binary (0=No, 1=Yes) target variable that represents whether or not a listing is likely to be illegitmately rented out or not** to build a decision tree.  

### Decision Tree

![Screenshot 2023-11-10 223651](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/3f1958c4-8c6c-4787-950b-9a9c947e453a)

![Screenshot 2023-11-10 222839](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/b3f6490e-fd1b-4b21-a845-2d354790a168)

![Screenshot 2023-11-10 223514](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/e2f57bc9-5886-4da7-ae2e-65ab484e6c32)

The default settings for the decision tree node was retained with the exception of the maximum depth being changed from 6 to 3. Although, retaining a higher depth would not necessarily be detrimental to the model results, having higher depth = lower accuracy in the lower leaf nodes (which does not help the aim of classifying listings with high accuracy).

The decision tree performed well at accurately classifying listings as the missclassifcation rate, maximum absolute error and average squared error rates showed high accuracy and stability across the train, validation and test data sets/partitions (note: to simulate a supervised and unsupervised environment the data was split into a "train", "validation" and "test" partition; 40%, 30%, 30%).

![Screenshot 2023-11-10 231514](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/a6d3eec8-57ac-40b6-b6cb-b8a09b44aeb2)

![Screenshot 2023-11-10 231825](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/ef43307d-c585-4ce2-bf8e-961a0bc71664)

Although the decision tree model performed well at classification, the variables selected by the algorithm were not great classfiers of illegitmate listings. As a result two decision trees was created with different parameters to change how the algorithm selects variables and classifies those variables in the decision tree. But, unfortunately this did not yield any meaningful changes towards having strong classifies of illegitmate listings. 

Thus the original **(Tree Name: "Standard") decision tree** was retained as the classfication model.

### Model Evaluation

![Screenshot 2023-11-10 232903](https://github.com/Kishawn-Dorman/Airbnb-Edinburgh-Housing-Dilemma-Analysis/assets/146044118/c9b27daf-b0ef-4b67-af5b-efb1858b965f)

Five models inclusing the decision tree was compared using the model evaluation node. Gradient Boosting model was the best as it yielded the lowest missclassification rate (P.S. the gradient boosting model performs several iteractions(i.e. several decision trees), where at each iteration it learns from the previous, thus gradually reducing the misclassification error). 


## Section 5 - Conclusion

only 2 out of the 15 input variables was recognised by the algorithm as being important to predicting the target. This limits the real world identification illegal short-term renting as having multiple characteristics (variables) allows for better identification as opposed to having only 2 characteristics.

The creation and/or inclusion of more host characteristics variables (e.g. booking rules & guest verification criteria) into the model would add more precise classifications to the model and add value to the models applicability to the real-world environment. 

During the data preparation phase many issues was found that could undermine the analysis and ultimately the model. As shown in table 4, a few listings was identified as being potentially affected by unusually high price values as the appeared to be outliers in figure 1. Although the outliers may have been addressed, the credibility and particularly the accuracy of the classification model could have still been affected by hidden data errors. For example, a price value within the average range of the dataset would be more difficult to detect, than a price value extremely high or low.  

Lastly, the clusters created for the classification model can also be affected by these data errors. But, on the hand the clusters created did show great stability when the cluster settings was tested against sample data (90% of data). This means that if changes (e.g. minor errors) to the data parameters were to occur, it would be unlikely to derive different clusters.

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

