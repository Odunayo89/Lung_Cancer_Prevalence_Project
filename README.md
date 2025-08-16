## Aim of the project

The aim of this project is to model lung cancer prevalence and to discern features that are strongly associated with lung cancer.


## Project, motivation

Investigating lung cancer cases is crucial due to its public health implications. This work is motivated to obtain insights about the underlying drivers of lung prevalence. 


## Data

We used data reported by  https://github.com/indranil09/VA_LungCancer_INLA. The data are obtained from the features 


1. Demographics: Gender (F, M), Race (Black, White, Other), Ethnicity (Hispanic, Latino, Not Hispanic or Latino), Age

               That is,  Percentage of males, Percentage of Blacks, Percentage of Whites, Percentage of Hispanics

               The impact of race, specifically Black or White, on the prevalence of Lung cancer was measured against the category ‘Other’, which includes Asian, Native Hawaiians and Other Pacific Islanders (NHPI), American Indian and Alaska Natives, some other race alone, and two or more races

                The effect of age will be incorporated into the model through the variable such as percentage of population with age ≥ 65

2. Prevalence of Binge Drinking, Smoking, and Obesity

3. Percent Population below Poverty

4. Social Deprivation Index (SDI): 

              It quantify the socioeconomic variation in health outcomes

              It is a deprivation based on seven demographic characteristics

              The seven demographic characteristics include:

                        * Percent living in poverty
                        * Percent with less than 12 years of education
                        * Percent single-parent households
                        * Percent living in rented housing units
                        * Percent living in overcrowded housing units
                        * Percent of households without a car and
                        * Percent unemployed adults under 65 years of age
              Its value range from 1 to 100, with higher values reflecting greater deprivation

5. Average Daily Air Quality PM2.5 Concentration: Particulate matter with a diameter of 2.5 micrometers or less


## Modelling

If we define the number of cases  𝑌 in terms of the population  𝑁 with a given intensity (or incidence rate)  𝜆, we assume that cases  𝑌
arise as a Poisson process with rate  𝜆, which represents the expected number of cases per individual in the population  𝑁. Thus, we can use generalized linear model with regularization to select features and obtain insight
the data. We also used XGBoost Poisson Regression to model the prevalence lung cancer using the selected features and to learn the relative importance of features that are associated with lung cancer prevalence.


## Result

The study result suggests that features such as  

    * Pct_BelowPoverty_18andOver  (Below poverty level of residents of age 18 and above (%))
    * Pct_White_65andOver (White race residents of age 65 and above (%))
    * BINGE_CrudePrev (Binge drinking prevalence of residents) 
    * CSMOKING_CrudePrevOBESITY_CrudePrev (Smoking and Obesity Prevalence of residents)    
    * Median_Household_Income  (Median household income of residents) 
    * ZCTA_pm2_5  (Average daily air quality PM2.5 concentration)
    * sdi_score (Social deprivation index )
    * Pct_White_Male_Between18and65 (White male race residents of age between 18 and 65 (%)) 
    * Pct_White_Female_Between18and65 (White female race residents of age between 18 and 65 (%)) 
    * Pct_Black_Female_Between18and65 (Black female race residents of age between 18 and 65 (%)) 
    * Pct_Black_Male_Between18and65 (Black male race residents of age between 18 and 65 (%))
    * Pct_Hisp_Male_Between18and65 (Hispanic male race residents of age between 18 and 65 (%))
    * Pct_Hisp_Female_Between18and65 (Hispanic female race residents of age between 18 and 65 (%))
 are strong association with lung cancer prevalence


## Executive summary

This study analyzes and models lung cancer prevalence using a combination of demographic, behavioural, and socioeconomic features. The primary objective is to identify key featuress associated with lung cancer incidence. 
The dataset includes demographic features such as gender, race (Black, White, Other), ethnicity, and age distribution—particularly the percentage of the population aged 65 and older. Behavioural risk features include the prevalence of smoking, binge drinking, and obesity. 
Socioeconomic indicators include the percentage of the population living below the poverty line and the Social Deprivation Index, a composite metric based on features related to education, employment, and housing. 
Data preprocessing is performed using standard Python libraries (Pandas, NumPy, Scikit-learn) to clean and transform the dataset. Exploratory data analysis is conducted to assess the relationship between lung cancer cases and individual features and to examine correlations among features. 
Heatmaps revealed notable correlations, indicating potential multicollinearity and motivating the use of regularization techniques for feature selection. 
We have used a generalized linear model with elastic net regularization to identify key features influencing lung cancer prevalence. All features are transformed and standardized to ensure they are on a similar scale. 
We have also implemented an XGBoost model using a custom Poisson loss function tailored to our count-based response variable to further enhance model performance and interpretability. 
This approach has outperformed the generalized linear model, achieving a 10.184% reduction in mean absolute error. In general, the results highlight strong associations between lung cancer prevalence and several factors such as age (particularly older populations), smoking prevalence, poverty, and the social deprivation index. 
These findings underscore the importance of addressing behavioural risks and socioeconomic disparities in public health initiatives. Interventions aimed at smoking cessation, poverty reduction, and mitigating social deprivation could significantly contribute to lowering lung cancer incidence.


## Future work
This work can be extended by incorporating spatial information into the model. This approach may help us better understand the drivers of lung cancer prevalence and visualize the spatial distribution of lung cancer incidence in the study area.




