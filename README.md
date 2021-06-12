# MechaCar Statistical Analysis using R

## Overview 

In this project we will use R to conduct statistical analysis to help AutoRUs’ upper management to review the production data of AutoRUs’ newest prototype, MechaCar, for insights that help the manufacturing team to resolving the production troubles. we conducted the following analysis to help the data analytics team to better understanding about the production data and finding solutions:
-	Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes
-	Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
-	Run t-tests to determine if the manufacturing lots are statistically different from the mean population
-	Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. 

## Linear Regression to Predict MPG

In this linear regression model, used all six variables from the data to predict the mpg of MechaCar prototypes. 

   ![inst1](https://user-images.githubusercontent.com/79289806/121786699-a68dba00-cb8f-11eb-882e-dfd6fc564b0f.png)

1.	In the summary output, each Pr(>|t|) value represents the probability that each coefficient contributes a random amount of variance to the linear model. From the table           above, vehicle_length and ground_clearance (as well as intercept) has a significant impact on mpg that provided non-random amount of variance to the mpg values in the           dataset. 

2.	The null hypotheses of this analysis could be the slope of the linear model is zero. If there is no significant linear relationship, each dependent value would be determined     by random chance error. Therefore, our linear model would be a flat line with a slope of 0.
 
    We will use r-squared value and p-value metrics to determine whether or not the slope of our leaner model is zero. For our linear regression model, the r-squared value is       0.7149, which means that approximately 71% of the variability of our depend variable is explained using this linear model. In addition, the p-value of our linear regression     analysis is 5.33 x 10-11, which is smaller than the assumed significance level of 0.05%. 

    In conclusion, the slope of our linear model is not zero.    
    
3.	From the analysis outputs above, we could see that approximately 71% of the variability of our depend variable is explained using this linear model, which could consider as     effective model. 

    However, in this analysis, the intercept is statistically significant (with Pr(>|t|) value of 5.08 x 10-8). Depending our dataset, this could mean that the significant           features (such as vehicle_length and ground_clearance) may need scaling or transforming to help improve the predictive power of the model. Additionally, across all six           independent variables in the model, only two of them have significant impact on the depend variable. The lack of significant variables is evidence of overfitting. For future     analysis, transform the independent variables and re-evaluate the coefficients and significance might help to improve the effectiveness of the model. 

## Summary Statistics on Suspension Coils

From the given data, we could calculate the suspension coil summary statistics:

1.	PSI across all manufacturing lots (total summary):

    ![inst2](https://user-images.githubusercontent.com/79289806/121786700-a7265080-cb8f-11eb-8cbf-9a73ed6630c7.png)
    
2.	PSI metrics for each lot (lot summary):

    ![inst3](https://user-images.githubusercontent.com/79289806/121786701-a7265080-cb8f-11eb-99b5-73e71c878305.png)

    From the summary statistics metrics above, the variance across all manufacturing lots (total summary) is 62.29356, which is smaller than 100 pounds per square inch. This         means that the current manufacturing data cross all lots meet the design specification.

    There are total of three manufacturing lots. Lot1 and lot2 both have variance smaller that 100 (variance for lot1 is approximately 0.98, the variance for lot2 is                 approximately 7.47) that meet the design specification. However, lot3 has variance of approximately 170.29, which is larger than the design specification. In other word,         lot3 does not meet the design specification. 

## T-Tests on Suspension Coils

In order to determine if the manufacturing lots are statistically different from the population means of 1,500 pounds per square inch, conducted the one sample T-Test for the current manufacturing data cross all lots, and for each lots respectively. Used the common 0.05 percent as the significance level for our analysis. 

1.	One sample T-Test across all lots:

    ![inst4](https://user-images.githubusercontent.com/79289806/121786702-a7265080-cb8f-11eb-94fd-d68baa396b0c.png)

    From the output above, the p-value from the T-Test across all manufacturing lots is 0.06028, which is above the significance level. Therefore, we do not have sufficient         evidence to reject the null hypothesis, and we could state that the mean across all manufacturing lots is statistically similar as the population means of 1,500 pounds per       square inch. 

2.	One sample T-Test for lot1:

    ![inst5](https://user-images.githubusercontent.com/79289806/121786703-a7265080-cb8f-11eb-9858-8d6991f65aef.png)

    The p-value of the one sample T-Test for manufacturing lot1 is 1, which is above the significance level. we could state that the mean of manufacturing lot1 is statistically     similar as the population means of 1,500 pounds per square inch. 
 
3.	One sample T-Test for lot2: 
 
    ![inst6](https://user-images.githubusercontent.com/79289806/121786704-a7265080-cb8f-11eb-886d-78bdb1ffcf8b.png)  

    Similar as lot1, the p-value of the one sample T-Test for manufacturing lot2 is 0.6072, which is above the significance level. We could state that the mean of manufacturing     lot2 is statistically similar as the population means of 1,500 pounds per square inch. 

4.	One sample T-Test for lot3:

    ![inst7](https://user-images.githubusercontent.com/79289806/121786697-a68dba00-cb8f-11eb-9a8f-7038843a33c7.png)    

    The p-value of the one sample T-Test for manufacturing lot3 is 0.04168, which is lower that the significance level. We have the evidence to reject the null hypothesis and we     could state that the mean of manufacturing lot3 is statistically not equal to the population means of 1,500 pounds per square inch.

## Study Design: MechaCar vs Competition

There will be a lot of features for a consumer to consider when purchasing a vehicle. For this specific statistical analysis, we are going to focus on cost, hours power and city fuel efficiency between MechaCar and competitions.  

Here are the null hypothesis and alternative hypothesis:

H0: There is no significant difference of means between MechaCar and Competition among cost, hours power or city fuel efficiency.

Ha: At least one of the means is not equal to others between MechaCar and Competition on cost, hours power or city fuel efficiency.

For this particular analysis, we could use one-way analysis of variance (ANOVA) to identify the difference of means between MechaCar and Competitions for variety of the elements. 

In order to conduct the analysis, we need to collect the information of cost, hours power and city fuel efficiency from both MechaCar and the competitions. Load the data into R as dataframe with each of the metrics as a column. Each metrics consider as one group. Combine the data from MechaCar and competition together into one dataframe, then use R to conduct the analysis with p-value. Compare the p-value to the significance level to determine if we will reject the null hypothesis or accept it. 

For better interpreting the data to answer the analysis question, we could also use box plots to present the summary statistics outcomes. 
