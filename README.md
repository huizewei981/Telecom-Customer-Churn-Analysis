# Telecom-Customer-Churn-Analysis

### This project is owned by Huize Wei (Rebecca), Weitian Xie (Lance), Xuran Wang (Angela), Ying Chen (Mia), Yuxin Guo (Grace)


## Data Source:
Data Selection:
Our test data[1] was acquired through the Kaggle Platform. Originally, the data set was published by IBM Developer website for IBM Watson Studio training. The dataset contains 21 variables which cover core attributes of customer churn and value analysis. Thus, we selected it to formulate our Telecom analysis.

Data Attributes:
In the dataset, all the attributes can be categorized into three groups:
Demographic: variables regarding gender, age,  family status, year with company. 
Service: variables pertaining phone services, internet services, protection services, streaming services etc. 
Finance: variables related to contracts, billing, payment methods, payment amounts etc.

Data Wrangling:
The dataset contains 21 columns and 7043 rows. Each row has an unique ID that points to an unique customer. There is no missing value among different attributes. There are a total of 17 categorical variables in our dataset. For variables with two categories, we substituted each of them with one column containing “0” and “1” to represent the respective categories. For variables with k (k>2) categories, we introduced k-1 columns for each of them as dummy variables to capture their influence.

Data Usage:
Most categorical variables are used for our logistic regression model specifically for customer churn prediction. Numerical variables such as ‘monthly charges’ and ‘total charges’ are used to build both the churn prediction as well as Customer Lifetime Value analysis. Not all variables are finally fit into the model. We plotted visualizations on variable distributions using boxplots and mosaic plots to determine their potential fit to the model. 



## Model Development & Results:
Our first step is feature selection based on the domain knowledge of the telecom industry, and the Exploratory Data Analysis (EDA). Our data can be impacted by multicollinearity. That is, some certain variables can be predicted by another variable, to some extent. For example, there is a strong correlation between Monthly.Charge and Total.Charge. Thus, we excluded some variables that show strong correlations with one or more variables. Also, dummy variables transformed from categorical variables, such as Two-Year-Contract dummy variable, Credit-Card dummy variable, and Fiber Optic dummy variable are excluded from the model to ensure reliability of coefficients of independent variables when interpreting feature contribution. Additionally, given the domain knowledge of the telecom industry, we created new variables to account for the interaction effects between multiple accessory services in addition to internet and phone services, which are add-on services available only when the primary service is subscribed. 

Logistic regression model yielded an overall accuracy of 82% with a 87% AUC score across all test datasets. Random Forest yielded an overall accuracy of 81% with a 84% AUC score across all test datasets. Logistic regression is slightly better than Random Forest. Among 22 variables, 15 were statistically significant at 0.05 significance level. By analyzing coefficients of each variable in the model, we found that among contract-related variables, the odds of churn for customers who subscribed to short-term contracts are significantly higher than those who subscribed to long-term contracts. Customers who subscribed to phone service, add-on services of the internet service or those who were charged with lower monthly fees have lower churn probability than those who did not. One thing worth noting is the synergy effect of movie service and TV service. Individually speaking, purchasing TV or Movie subscription both reduce customer churn rate. However, their synergy effect increases the overall churn probability. Among customer demographic variables, senior citizens and customers who chose paper billing are more likely to churn. Customers who have stayed with the company for longer periods tend to have lower churn probability.  



### Citation:
[1]BlastChar. (2018, February 23). Telco Customer Churn. Retrieved December 15, 2020, from https://www.kaggle.com/blastchar/telco-customer-churn
[2]Aubron, X. (n.d.). Ask Meaningful Questions to Improve Learning. Retrieved December 16, 2020, from https://blog.gutenberg-technology.com/en/ask-meaningful-questions-learning
[3]Petkovski, A. J., Stojkoska, B. L. R., Trivodaliev, K. V., & Kalajdziski, S. A. (2016, November). Analysis of churn prediction: A case study on telecommunication services in Macedonia. In 2016 24th Telecommunications Forum (TELFOR) (pp. 1-4). IEEE. 
[4]Maverick, J. (2020, August 28). What is the average profit margin for a company in the telecommunications sector? Retrieved December 15, 2020, from https://www.investopedia.com/ask/answers/060215/what-average-profit-margin-company-telecommunications-sector.asp
[5]Wong, K. K. K. (2010). Fighting churn with rate plan right-sizing: A customer retention strategy for the wireless telecommunications industry. The Service Industries Journal, 30(13), 2261-2271.

[6]Dahiya, K., & Bhatia, S. (2015, September). Customer churn analysis in telecom industry. In 2015 4th International Conference on Reliability, Infocom Technologies and Optimization (ICRITO)(Trends and Future Directions) (pp. 1-6). IEEE.

