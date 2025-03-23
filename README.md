---
editor_options: 
  markdown: 
    wrap: 72
---

# DAS-Group-29

Data Analysis Skills – Group Project 2

##  1. Project background 

Based on 1994 US Census data, the project aims to explore which
socioeconomic characteristics affect individual income, and in
particular to determine which factors increase the probability that an
individual will earn more than \$50K a year.

## 2. Data description

-   Source: United States 1994 Census Database
-   Variable:
-   **Age** : Age (continuous variable)
-   **Education** : Level of education (divided into categories such as
    10th, HS-grad, Bachelors, etc.)
-   **Marital_Status** : Marital status (e.g. Married-civ-spouse,
    Never-married, etc.)
-   **Occupation** : Occupation category (contains multiple specific
    occupations)
-   **Sex** : Gender (Male/Female)
-   **Hours_PW** : Hours worked per week (continuous variable)
-   **Nationality** : Nationality by birth
-   **Income** : Income category (binary variable, \<=50K and \>50K)

## 3. Exploratory Data Analysis (EDA)

-   **Descriptive Statistics** : Basic statistical description of each
    variable, histograms and box plots are drawn to observe the
    distribution of variables.
-   **Correlation analysis** : Correlation tests are carried out on
    numerical variables to explore the relationship between variables.
-   **Chi-square test** : A Chi-square test was conducted on the
    correlation between categorical variables (such as Education,
    Marital_Status, Occupation, Sex, Nationality) and income, and the
    results showed that variables except Nationality had a significant
    impact on income.

## 4. Model construction and selection

### 4.1 Full model construction

-   **Method** : Using a binary logistic regression model in the
    Generalized linear model (GLM), the target variable is Income (\>50K
    and \<=50K).
-   **Variables** : The initial model contains all candidate variables
    (Age, Education, Sex, Hours_PW, Marital_Status, Occupation,
    Nationality).
-   **Problem detection** : Complete separation of data is detected in
    the whole model, and some variables are estimated to be infinite,
    affecting the stability of the model.

### 4.2 Model optimization (Stepwise AIC selection)

-   **Step** : Forward - backward stepwise regression was adopted, model
    selection was carried out using AIC, and variables that contributed
    little to the income forecast were eliminated.
-   **Result** : The variables retained mainly include Age, Education,
    Hours_PW, Marital_Status, and Occupation. Sex and Nationality are
    excluded from the AIC selection process, indicating that they have
    little impact on the predicted income.

### 4.3 Category merge processing

To solve the problem of complete separation and improve the stability of
the model, some explanatory variables were combined: - **Level of
Education** : The original multiple categories of education are combined
into "low education" (1st - 12th) and "high education" (including
Associate, Bachelor, Master, Doctorate, HS-grad, Prof-school, and Some
college). **Marital status** : combined as "married" and "unmarried"
(including Divorced, Separated, Never-married, Widowed). - **Occupation
Category** : - Attempts were made to group occupations according to
**manual and mental Labour**, **PRC Occupational Classification** and
**ISCO-08 International Occupational Classification**. - Model
comparison shows that the method using ISCO-08 classification is more
balanced in explanatory power and model fitting.

## 5. Model inspection and evaluation

-   **Model diagnosis** : Evaluate the performance of the model by
    checking the residual deviance and AIC values of each model and the
    ability to explain the deviation after gradually increasing the
    variables.
-   **Analysis of Odds Ratio** : OR charts of different models
    (including mental-physical model, PRC model and ISCO-08 model after
    combining variables) were drawn to visually show the direction and
    magnitude of each variable's influence on income forecast.
-   **Results** : The model shows that the likelihood of an individual
    earning a high income increases with age and the number of hours
    worked per week; High education level and married status have
    significant positive effects on income. There are significant
    differences between different occupational categories, with brain
    work (or high-skilled occupations) significantly more likely to lead
    to higher incomes.

## 6. Conclusion

-   After preliminary model construction and gradual optimization, the
    final model shows that age, education level, weekly working hours,
    marital status and occupation category are important factors
    affecting income.
-   The problem of complete separation of data is somewhat mitigated by
    merging categories (especially education and occupation), making the
    model more robust. The use of **PRC Occupational Classification** of
    Occupations can better capture the impact of occupations on income
    and provide a strong basis for subsequent policy recommendations and
    economic planning.
