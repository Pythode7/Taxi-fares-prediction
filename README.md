# Predicting Taxi Fares and Gratuities in New York City

## Overview
The goal of the project was to create a multiple liniear regression to predict fare for each trip and a tree-based model to predict high rider gratuity or not. The 
purpose of these models is to find ways to generate more revenue for taxi cab drivers. This project utilized yellow taxi trips taken in New York City during 2017. A multiple 
linear regression model with an R-squared of 0.85 was built to predict fare for each trip. On average,the fare increases by approximate $2 for every 1 mile increase in distance. 
The final random forest model performed with 71% accuracy and 69% precision determining what features were most important in separating low tippers from high tippers. 
Based on the model, the VenderID, duration, distance, and cost of the trip were most influential in determining a generous tipper (>20%) vs a non-generous one (<20%). 

## Business Understanding 
According to salary.com the average salary for a New York Taxi Driver is around $45,000. This salary is significantly low compared to a median rent value of $6,500 per month. 
It is important to understand what factors encourage riders to leave tips in order to help drivers obtain a livable wage.

## Data Understanding
The NYC Taxi and Limousine Commission data came from NYC.gov. The data consisted of approximately 408k unique trips and 18 features. The features included information on 
trip duration and destination, vendor used, toll information, and payment type. The bar chart below shows the breakdown of how many generous tippers (>20%) versus 
non-generous tippers that exist in the data set.     

![image](https://github.com/user-attachments/assets/229cf931-edcb-4e1b-a90e-11ddcea5c952)


## Modeling and Evaluation 
**_Coefficients for multiple linear regression model_**
|**passenger_count**|	**mean_distance**|	**mean_duration**|	**rush_hour**|	**VendorID_2**|
|---|---|---|---|---|
|0.04667|	7.108085|	2.881468|	0.132942|	-0.04049|    

The model achieves an R-squared of 0.85, signifying that 85% of the variance in the target variable is explained by the model's features. This suggests a good fit between the model and the data.   

The coefficients reveal that mean_distance was the feature with the greatest effect on the model's prediction. Because the data used to train the model was standardized with 
StandardScaler() withs std of 3.566607, the modelbuil relinear regression model is interpreted as "With holding the other variables constant, for every 1 mile change in mean distance, 
the fare amount increases by a mean of $2 (7.13/3.566607).    

**_Metrics and feature importance of the random forest model_**    

A random forest model comprising 500 decision trees was used to determine feature importance in who would tip generously or not. The below plot shows that VenderID, the cost of a fare, trip distance, and duration were the Top 5 most important factors in determining a generous tipper from a non-generous one. The overall model performed with 71% accuracy and 69% precision.   

![image](https://github.com/user-attachments/assets/30dec3c1-b5fb-4655-899a-5076b425e87f)

The model's high predictive power of VendorID is unexpected.  To understand this, we should investigate the potential discrepancies in data collection between the two vendors.

## Conclusion
This model offers a two-fold benefit for taxi drivers. Firstly, it can estimate the fare for a trip. Secondly, it can potentially predict whether a rider is likely to tip generously. 
However, the model currently uses a parametric approach to determine the influence of different factors on tip amount. This approach might not capture the full picture.  In the future, incorporating information about a rider's past tipping behavior could significantly improve the model's ability to address the stakeholder's business needs.
