# Credit-Card-Fraud-Detection

# Executive Summary 

Credit card fraud can be stated as unauthorized use of credit or a debit card, or similar kind of payment to fraudulently obtain money or property. The details of these credit or debit cards can be stolen from unsecured websites or it can also be obtained in any theft identity schemes. Credit card fraud is the most widely recognized sort of fraud, as per a 2020 Federal Trade Commission report. This sort of fraud commonly involves somebody assuming control over an individual's current credit card accounts and charging without consent or opening new records utilizing another person's very own financial data. 
In the two cases, the convict escapes with the products and the buyer is left managing the credit, financial, and psychological damage. Credit card frauds is not just an online issue but also happens in stores. There are some challenges being faced when it comes to detecting fraud that happened on-ground and not a bluff. Some of the challenges are: 

•	The frauds detected each time are not easy to recognize whether they are actual on-ground fraud or not.

•	Many business owners are not familiar with impact of fraud on their business. 

•	How do you exactly define frauds, because many at times it may happen that payments made are not fraudulent?

This project will involve making predictions by modelling past credit card transactions. Also, based on this model detect whether the new transaction made is a fraud or not. In this manner, we can help business owners, merchandisers minimize fraud. 

# Introduction 

The dataset contains data of credit card transactions made in September 2013 by the European cardholders. In this present dataset it states that 492 frauds have been detected out of 284,807 transactions in two days. This interprets that the data is highly imbalanced. The percentage of positive frauds of all transactions are 0.172%. As it involves confidential data, we just have following features V1 to V28 which are termed as the principal components. Apart from this we are been provided with time and transaction amount.  

Standard Scaler is a typical tool when working with classification issues this way. It changes the data to where there is a mean of 0 and a standard deviation of 1, in this way, normalizing the information into a typical conveyance takes place. Particularly with taking a shot at such a wide scope of sums and time, we saw that scaling data before running the tests gave better outcomes.

Another issue to address is the profoundly imbalanced dataset. With numerous non-fraudulent transactions set up, we can actualize Random Under sampling to diminish the quantity of non-fraudulent transactions and match it to the measure of fraudulent transactions.

# Implementation 

With our dataset, we tried to implement our data analysis through CNN, heat maps and correlation matrix. This data analysis is in respect to the time, amount w.r.t V1 and V3. Our main goal was to understand how heat maps work with our dataset when convoluted with neural networks. In pre-processing and cleaning our dataset, we followed the following steps:

1.	Gathering data.
2.	Importing dataset and their respective libraries.
3.	Remove missing values.
4.	Dividing the dataset into dependent and independent variables.
5.	Dealing categorical values and split into test and training sets.
6.	Feature Scaling.

# Exploratory Data Analysis

Exploratory Data Analysis (EDA) is an approach to extract the information enfolded in the data and summarize the main characteristics of the data. Exploratory Data Analysis refers to the critical process of performing initial investigations on data so as to discover patterns, to test hypothesis and to check assumptions with the help of summary statistics and graphical representations. In statistics, exploratory data analysis is an approach to analysing data sets to summarize their main characteristics, often with visual methods. After we are done with pre-processing our dataset, we can now move on to - EDA.

More importantly, Exploratory Data Analysis for seeing what the data can tell us beyond the formal modelling or hypothesis testing task. The Time distribution in hours presents two main peaks, roughly around the hour 15 and 40 (about 24h difference) which suggests that there is a daily modulation of the traffic, assuming that the data was captured from a single time-zone (this is one assumption) On the other hand, most of the Amount values are grouped near small values.

Now let us explore the Amount field. The best transformation to perform on the Amount is a logarithm. However, this will compromise the negative and zero values. Fortunately, there are no negative values and the number of records with zero amount is small. So, we can select the positive values of Amount and work on a specific model for the zero case, being the smallest non-zero value 0.01, consistent with one cent of the currency (this is another assumption).

# Conclusion 

1) We instrumented statistical modeling, interactive & elegant visualizations in matplotlib, scikit-learn, plotly, and seaborn.

2) We started off with exploring the dataset, checked for data imbalancing, visualized the features and understood the relationship between different features. Using, predictive models we analyzed the dataset further. This dataset is divided into three parts: a train dataset, a validation dataset and a test dataset but we used only the train and test dataset for perform further analysis. 

3) We started off with exploratory data analysis to summarize their main characteristics, often with visual methods. EDA in order to check what data can tell us beyond the formal modelling or hypothesis testing task. Here, figured out that time distribution visual suggests that there is a daily modulation to the traffic, thereby assuming that the data was captured from a single time-zone. 

4) We followed with Correlation matrix where we found that these variables show high correlations: 

•	Amount & V2 (-0.53)

•	Time & V3 (-0.42)

•	Amount & V4 (0.4)

5) We then followed with XGBoost where we used both train-validation split and cross-validation to evaluate the model's effectiveness to predict class, wherein achieved AUC score 0.974 for valuidation set and 0.93 for cross-validation. 

6) Lastly, we performed random forest where we achieved accuracy of 99% with train dataset and 99.96% with test dataset. 
