# New-Product-Performance
Predicting New Product Performance
Objective
As a continuation of our sales performance analysis, we’ve decided to redo our initial prediction models to include the ‘product type’ attribute to better understand how are products perform against each other. 
We will use historical data to predict sales volumes of our new product offerings. 
To achieve this objective, we will:
Predict sales of four different product types: PC, Laptops, Netbooks and Smartphones
Assess the impact service and customer reviews have on the sales of different product types


Exploratory Data Analysis (EDA)
1.1 exploratory data analysis
We began with 80 observations, across 18 variables within our Existing Products data set. In examining the data we find that many of the variables will be irrelevant in determining which factors are crucial to predicting products sales performance, to include:
 Product dimensions 
 Best sellers rank
 Shipping weight

Another important step within the EDA process is to determine whether you have missing or duplicated values that might inappropriately skew your predictions. In this case we discovered 15 “NA” values within the ‘Best Sellers Rank’ data and 6 duplicative records within the ‘Extended Warranty’ data. We will address these concerns during the pre-processing section. 
Finally, we plot our data set to gauge how many, and to what degree, outliers reside within our raw data set. 

EDA Visualized
1.2 eda – data distribution
How is our data structured? How is the raw data distributed across the different features?

Pre-processing
How can we modify the raw data set to fit our needs and answer the questions we are seeking by eliminating “noise” that might skew the results we are working towards?
2.1 preprocessing of data 
Outlier Data
In the previous visual we saw a few outliers that significantly deviated from what we would deem to be a normal distribution or ‘bell curve’. Considering the relatively small size of our data set we should exercise caution in eliminating valuable intel and select a variable most impactful, which in this case has us taking a closer look at the dependent variable, Volume. 


For this project, we have elected to eliminate the most extreme outlier values; those >7000. We take further comfort in this action because these outlier values belong to the product types: accessories and game consoles, neither of which we are currently analyzing.

Scale Data
Finally, to round out the preprocessing phase, we scale the data. This is done to apply a layer of standardization across the independent variables, which most often possess different metrics or values assigned to the attributes. Without scaling the machine learning algorithms tend to assign a greater weight to larger values and a lesser value to smaller values, regardless of their units of measure. We scale all columns containing numeric values, excluding labels.

Feature EngineeringCorrelation Matrix, Dummy Variables, and Collinearity 
3.1 Correlation Matrix
Each cell within this table illustrates the correlation between two variable. The purpose of this matrix is to summarize the data and guide further analysis as a diagnostic tool.
In this specific matrix we can identify a strong correlation between volume of sales and customer ratings- both regarding service and product performance.
Feature EngineeringCorrelation Matrix, Dummy Variables, and Collinearity 
3.2 Dummy Variables
For this project we are trying to determine which new product types will perform best based on the historical data trends of existing products. In order to further examine the existing product types, which are categorical in nature, we will need to create placeholders by assigning them numeric values between 0 and 1. By creating dummy variables we are, in essence, indicating the absence or presence of a specified condition. These values can then be summed, marginalized and integrated over. 

Feature EngineeringCorrelation Matrix, Dummy Variables, and Collinearity 
3.3 Collinearity
The ability to interpret models is a key part of being a data scientist.
For regression models to perform optimally we want to ensure, to the best of our ability, that the regression coefficients are uniquely determined. If the features are too closely correlated, they have too great an influence on other features. This special case is referred to as collinearity.

Modeling
Linear Regression Model (lm), Random Forest (rf), Support Vector Machine (svm), Gradient Boosting Machine (gbm)
The algorithm we chose to use for predicting product type performance was Support Vector Machine (svm), more specifically svm-poly owing to the non-linear distribution. The purpose for choosing this algorithm over the other 3 is based on the results as follows:
RMSE = 346.56: among the lowest of all the algorithms even with have a few remaining outliers.
R-Squared = 0.887: is the closest value to 1.0 of all values. This is expected given the inverse relationship between RMSE and r-squared.
MAE = 224.06: this is our error-meter. For this reason, the lower the value or the closer to zero we can get, the better.

Final Predictions5.1 RESULTSApplication of SVM modeling on the New Products Data Set

Impact of Customer Reviews on Product Volume






