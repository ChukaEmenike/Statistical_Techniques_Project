# Statistical_Techniques_Project

### 1.0.    INTRODUCTION
This portfolio aims is to employ statistical hypothesis tests and concepts to investigate and answer some typical world problems as well as outline ethical consequences of process. 


All hypothesis tests covered will take three parts:\
A.	Two competing claims about a population (The null hypothesis or H~O~ and the alternative hypothesis or H~1~)\
B.	The Test Statistic Part to evaluate the statistical merits of the two claims.\
C.	The Decision Part to reach a conclusion following observations from statistical analysis\
\

###  GAMING DATASET:  
This dataset is the result of a questionnaire for psychology study of Gamers worldwide to investigate if playing digital games has an impact on mental health and ultimately reduces life satisfaction. The Dataset has a dimension of 13464 observations and 55 variables that correspond to every question asked in the questionnaire.

#### ATTRIBUTES DESCRIPTION
- Age: Age of individual candidates in the survey
- Gender: Gender of individual candidates in the survey
- Hours: Number of hours in a week spent gaming
- GAD_T: Sum of all GAD (General Anxiety Disorder) score variables
- SWL_T: Sum of all SWL (Satisfaction with Life) score variables
- SPIN_T: Sum of all SPIN (Social Phobia Inventory) score variables
- GADE: Difficulty level showing affect of gaming in work
- Streams: Proportion of streaming games activity
- Narcissism: Interest scale in the game

### 2.1.   ONE SAMPLE T.TEST
#### QUESTION 1: An online website [Datapronet](https://dataprot.net/statistics/gamer-demographics/) stipulated in an article that the average age of gamers worldwide is 35 years, is the claim true or false?

#### OBJECTIVE
To carry out a one sample test using the gaimg survey data in order to test the hypothesis claim of mean age 35 at a significant confidence interval

#### EDA:
The visual analysis of the Age distribution using qq plot, histogram and box plots shows a right skewed distribution with a skewness coefficient of 2.11. And as expected a higher mean value of 20.93 compared to the mean value of 20.

#### TEST BASIS: 
- Null hypothesis (H~O~): The mean gaming age is equal to 35 ($\mu$ = 35)
- Alternative hypothesis (H~1~): The mean age is not equal to 35 ($\mu$ ≠ 35)

#### ASSUMPTIONS FOR TEST: 
- Given the large sample size (n = 13464) CLT holds hence sample normality distribution can be ignored and treated as normal.
- Random sampling.
- Individual observations are independent.


Ignoring normality assumption due to sample size and proceeding to check for normality of sample. The Anderson-Darling test for normal distribution calculates a P-value far lower than the significant level of 0.05 therefore we conclude that the sample does not come follow a normal distribution. Hence, we proceed to a non - parametric test for abnormal distribution.


#### TEST OBSERVATIONS
With the t- statistic beyond the critical values of ±1.96014 and P-value significantly less than 0.05 for both the T.test and the Wilcoxon Signed Rank Test for independent sample we have strong evidence to reject the Null hypothesis (H~O~) of mean gamers age of 35 and therefore conclude that there is a significant difference between the mean age of the people that took part in the survey and the Datapronet reported age.
\


### 2.2. CHI SQUARE TEST
#### QUESTION 2: Is the General Anxiety Disorder (GADE) which represents the impact of gaming on work life similar across genders?\

#### OBJECTIVE
To test if there is an association between the categorical variables and in order words compare actual results against expected results in a random occurrence

#### TEST BASIS:
- Null hypothesis (H~O~): There is no relationship between the two categorical variables Gender and GADE meaning the events would occur as it would in a random distribution
- Alternative hypothesis (H~1~): The distribution of GADE across Genders shows a significant association between Gender and GADE  


#### OBSERVATIONS:
With an X^2^-statistic value well on the right side, in the critical region and a P-value less than the significant level 0.01, the Null Hypothesis is rejected and we can conclude there is an existence of a relationship between the Genders and General Anxiety disorder.
\


### 2.3. LOGISTIC REGRESSION
#### Question 3: Find a method using the Dataset to predict presence of GAD using some measured attributes


#### OBJECTIVE
Create a model to predict the possibility of an individual that performs Digital Gaming activities to develop General Anxiety Disorder\

#### CONCLUSION: 
From the model, Hours, Streams, Narcissism and SPIN_T show to be positively significant at 5% significance level.\
Keeping all other predictors constant, then one degree increase in each of the variables respectively represents a 0.0032, 0.0066, 0.01384 and 0.0521 increase in General Anxiety Disorder (GAD).\
In terms of Gender being Male present a lesser chance of having GAD with a -0.6155 decrease in the log odds of the response variable compared to the Female category.\
The estimated log odds of the GAD when all predictor variables are zero is an intercept of 0.4961.\

A prediction test for new attribute values (Hours = 30, streams = 7, Narcissism = 4,  Gender = "Female", Age = 27, SWL_T = 6, SPIN_T = 4) show a positive indication of GAD is expected.
\


### 2.4. ANOVA
#### QUESTION 4: Is the mean Age the significantly same for Gamers residing in UK, Germany and Canada 

#### OBJECTIVE
To check if there is significant difference between the mean Ages of Gamers in the Countries of interest.

#### TEST BASIS:
- Null hypothesis (H~O~): The mean Age of Gamers in the countries is equal
- Alternative hypothesis (H~1~): At least one country has a different mean Age  

#### CONDITION FOR TEST: 
- Equal variances: Bartlett test of homogeneity of variances with a P-value (0.001024) greater than the significance level 0.05 indicates there is not enough evidence to conclude that the variance of groups are significantly different.

#### ASSUMPTIONS FOR TEST:
- The populations from which the samples are drawn are normally distributed.
- Observations are independent within and between groups.

#### OBSERVATIONS:
Following the One Way Analysis of Variance test, with a P-value of 0.001024 which is less than the significance level of 0.01, I conclude there is significant difference(s) in the means of the groups. Which ultimate shows that the mean Age for Gamers residing in UK, Germany and Canada is different.

Pairwise comparison shows significant difference between the mean Age for comparisons between UK and Cananda as well as for UK and Germany, with Canada and Germany having similar Age distributions.
\


### 2.5. MULTIPLE LINEAR REGRESSION
### US BASKETBALL PLAYERS DATASET
This dataset contains player per-game data for the NBA's 2022-23 season with player salary data, creating a resource for understanding the relationship between performance and financial aspects of professional basketball players in the United States. This dataset has a dimension of 467 observations and 32 variables.

#### ATTRIBUTES DESCRIPTION
- Salary: Salary in US Dollars
- Position: Position of Player
- Age: Age of players listed in records
- GS: Games started
- BLK: Blocks per game 
- TOV: Turn overs per game
- PF: Personal Fouls per Game

#### Question 3: Create a method using the Dataset to predict would be player salary using game perfromance data.

#### OBJECTIVE
To check for relationship between dependent variable "Salary" and independent predictor variables of game play stats and hence predict the salary of an NBA player using game performance

#### CONDITIONS FOR LINEAR MODEL:
-  Multicollinearity: To achieve this the independent variables for the final model were of significantly low collinearity.

#### ASSUMPTIONS FOR LINEAR MODEL:
- Linearity
- Independence of observations: Residuals followed no clear pattern or trend signifying random distribution.
- Homoscedasticity: residual plot versus fitted values plot showed significant spread along horizontal axis.
- Normality of residuals: Residuals QQplot are assumed to be normally distributed 

#### CONCLUSION

Model highlights use of Age, GS, BLK, TOV and PF variables as having the best relationship to predict player salary. All predictors are significant at 0.05 level. With P- value of < 0.01 there is enough evidence to conclude that the independent variables have a significant effect on the dependent variable. And up to 61.68% of the variability in Salary can be explained by the model.\
Coefficients of the model highlighted that Age had an personal unexpected presentation as older players seemed to earn more, at an estimated Salary increases of approximately $918,069 for each increase in Age. Further explained by a predicted Salary increase of $110,688 for each additional game started (GS). Each additional block (BLK) an increase of $3,848,133, $6,617,493 for an additional Turn Over (TOV) and each added Personal Foul (PF) leads to a salary decrease of $2,184,653.

Consequently, the model at 95% prediction interval of salary for predictor variables (Age = 40, GS = 30, BLK = 0.5, TOV = 1.5, PF = 1.1) is between 13044009 and 40204634 USD.\

### 3.0. ETHICAL CONSEQUNCES OF TECHNIQUES
- One Sample T.test and ANOVA: If the observations in the data is not a representation of the population the conclusion reached from the hypothesis testing may be inaccurate due to bias and lead to false claims.
- Chi Square Test: Given the broadened definitions of gender, the binary approach may be an improper categorization and may be an unintentional manipulation of categories to achieve desired results.
- Linear and Logistic Models: Insufficient detail of limitations and error margin of models may lead to wrongful decisions if made purely from predictive outcomes.\
\
\

### 4.0. REFERENCES
-	Center for Open Science collected as a part of a survey by the original authors Marian Sauter and Dejan Draschkow.’Online Gaming Anxiety Data’ 2020. Accessed in 2023 at Kaggle: https://www.kaggle.com/datasets/divyansh22/online-gaming-anxiety-data
-	WELSH J. ODC Attribution License (ODC-By). ‘NBA Player Salaries (2022-23 Season)’ Accessed in 2023 at Kaggle: https://www.kaggle.com/datasets/jamiewelsh2/nba-player-salaries-2022-23-season/data
-	Stephens, M.A. (1986): Tests based on EDF statistics. In: D’Agostino, R.B. and Stephens, M.A., eds.: Goodness-of-Fit Techniques. Marcel Dekker, New York. Accessed in 2023 at https://www.hep.uniovi.es/sscruz/Goodness-of-Fit-Techniques.pdf
