# NYC-ABNB-Occupancy-
1) Title
NYC ABNB Occupancy Analysis

2) Link to data set you are planning to use
http://data.insideairbnb.com/united-states/ny/new-york-city/2023-10-01/visualisations/listings.csv

4) Main goal
- explore the pattern among "occupancy ~ price + number_reviews + neighborhood + room_type"
- We chose 'occupancy' as the target variable rather than 'price', because price has a significant linear relationship with neighborhood and room_type, which is common sense. we would like to dig out something valuable and highly concerned by the hosts - 'occupancy rate', the opposite of 'availability'. As the variable 'occupancy rate' is not explicitly given, we need to calculate based on relevant columns, such as ‘availability’. Occupancy rate is a key metric for ABNB listing. Here is a reference for the ABNB metrics. 
https://www.mashvisor.com/blog/airbnb-occupancy-rate/

5) Statistical methods
### Preparation
- use pairplot to observe correlation between numeric variables, e.g. price, number_reivews, availability;
- subset by categorical variables, e.g. neighborhood, room_type, see the difference among different groups
- perform EDA, select variable, drop null, drop outliers

### Method Selection
- perform forward stepwise regression analysis
- train_test_split
- start with linear regression first: availability ~ price, observe the shape of scatter plot, check R-squared, residual plot analysis;
- add a numeric variable "number_reviews", check R-squared, compare with above model
- one-hot-encoding, get dummies from categorical variable "neighborhood", use generalized linear model (GLM)
- add one more categorical variable "room_type", compare R-squared metric
- make a summary and write a short report
