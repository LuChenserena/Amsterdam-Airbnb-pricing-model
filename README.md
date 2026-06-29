# Airbnb Pricing Determinants in Amsterdam

This project analyzes Airbnb listing prices in Amsterdam, North Holland, using multiple linear regression. The goal is to examine how property features, accommodation capacity, host responsiveness, and review metrics relate to listing prices.

## Project Overview

The analysis uses a cleaned Airbnb listings dataset for Amsterdam and focuses on whether host pricing decisions align with factors that consumers may value when choosing short-term accommodations.

Key predictors include room type, accommodation capacity, review metrics, host response rate, and host response time categories.

## Tools and Methods

* R
* Multiple linear regression
* Interaction terms
* Log transformation
* Stepwise model selection using `stepAIC`
* Nested ANOVA model comparison
* Variance Inflation Factor (VIF)
* Residual diagnostics
* Adjusted R-squared, AIC, and BIC model comparison

## Methodology

### 1. Data Preparation

The cleaned dataset contains 5,599 valid Airbnb listings in Amsterdam. The analysis uses listing price as the response variable and includes predictors related to property characteristics, host behavior, and review information.

### 2. Model Building

I built multiple linear regression models to estimate how listing characteristics are associated with price. The models included interaction terms such as:

* `Accommodates:Private_Room`
* `Accommodates:Shared_Room`
* `Number_of_Reviews:Review_Scores_Rating`

To improve model fit and address skewness, I also considered transformed variables, including log-transformed price and log-transformed number of reviews.

### 3. Model Selection

I compared alternative models using:

* Stepwise selection with `stepAIC`
* Nested ANOVA tests
* Adjusted R-squared
* AIC and BIC
* VIF checks for multicollinearity

Highly correlated or less useful predictors were reviewed and removed when necessary to improve model interpretability.

### 4. Model Diagnostics

I evaluated linear regression assumptions using:

* Residuals vs fitted plots
* Q-Q plots
* Scale-Location plots
* Residuals vs leverage plots
* Cook's distance
* Residual plots against key predictors

These diagnostics were used to assess linearity, normality, heteroscedasticity, influential observations, and overall model stability.

## Key Findings

* Accommodation capacity was strongly associated with higher listing prices.
* Entire-home listings were priced higher than private-room and shared-room listings.
* Interaction terms showed that the relationship between accommodation capacity and price differs by room type.
* Review-related variables had weaker effects than expected, suggesting that property features may play a larger role in pricing than review metrics.
* The final model still had limitations, including mild heteroscedasticity and missing factors such as neighborhood, seasonality, and host experience.

## Repository Structure

```text
airbnb-pricing-regression/
├── README.md
├── scripts/
│   └── airbnb_regression_analysis.R
├── report/
│   └── airbnb_pricing_report.pdf
├── figures/
│   └── diagnostic_plots.png
└── data/
    └── README.md
```

## Notes on Data

The dataset was originally derived from publicly available Airbnb listing information. If the full dataset cannot be redistributed, this repository will include data source information and analysis code rather than the raw data file.

## Academic Integrity Note

This project was completed as part of a university coursework assignment and is shared for personal portfolio purposes only. Please do not copy, submit, or reuse this work as your own academic assignment.

