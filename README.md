# Airbnb Pricing Determinants in Amsterdam

This project analyzes Airbnb listing prices in Amsterdam, North Holland, using multiple linear regression. The goal is to examine how property features, accommodation capacity, host responsiveness, and review metrics relate to listing prices.

## Project Overview

The analysis uses a cleaned Airbnb listings dataset for Amsterdam and focuses on whether host pricing decisions align with factors that consumers may value when choosing short-term accommodations.

Key predictors include room type, accommodation capacity, review metrics, host response rate, and host response time categories. The project develops an initial regression model, evaluates its limitations, and then refines the model through transformations, model selection, and diagnostic checks.

## Project Workflow

This project was completed in two stages.

### Stage 1: Initial Statistical Report

The first-stage report develops the original multiple linear regression model for Airbnb listing prices in Amsterdam. It introduces the research question, describes the dataset, explains the selected predictors, fits the initial regression model, and evaluates preliminary model assumptions using diagnostic plots.

### Stage 2: Model Improvement Poster

The second-stage poster refines the initial model by addressing model limitations identified in the report. This stage applies log transformations, compares alternative models, checks multicollinearity using VIF, performs model selection with stepAIC and nested ANOVA tests, and evaluates the final model using adjusted R-squared, AIC, BIC, and diagnostic plots.

Together, the report and poster show the full statistical modeling process: starting from an interpretable baseline regression model, identifying its limitations, and improving the model through transformation, variable selection, and diagnostic evaluation.

## Tools and Methods

* R
* R Markdown
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

The cleaned dataset contains 5,599 valid Airbnb listings in Amsterdam. Listing price is used as the response variable, while the predictors describe property characteristics, host behavior, and review information.

### 2. Initial Model Building

The initial model estimates how Airbnb listing characteristics are associated with price. It includes predictors such as accommodation capacity, room type, review metrics, host response rate, and host response time.

The model also includes interaction terms, such as:

* `Accommodates:Private_Room`
* `Accommodates:Shared_Room`
* `Number_of_Reviews:Review_Scores_Rating`

These interaction terms help examine whether the effect of one predictor changes depending on another feature, such as whether accommodation capacity affects prices differently across room types.

### 3. Model Refinement

To improve the initial model, I considered transformed variables, including:

* log-transformed listing price
* log-transformed number of reviews
* squared review scores

I then compared alternative models using stepwise selection, nested ANOVA tests, adjusted R-squared, AIC, and BIC. I also checked multicollinearity using VIF and removed or reconsidered highly correlated predictors when necessary.

### 4. Model Diagnostics

The final model was evaluated using several diagnostic tools:

* Residuals vs fitted plots
* Q-Q plots
* Scale-Location plots
* Residuals vs leverage plots
* Cook's distance
* Residual plots against key predictors

These diagnostics were used to assess linearity, normality of residuals, heteroscedasticity, influential observations, and overall model stability.

## Key Findings

* Accommodation capacity was strongly associated with higher listing prices.
* Entire-home listings were priced higher than private-room and shared-room listings.
* The relationship between accommodation capacity and price differed by room type.
* Review-related variables had weaker effects than expected, suggesting that property features may play a larger role in pricing than review metrics.
* The final model still had limitations, including mild heteroscedasticity and missing factors such as neighborhood, seasonality, and host experience.

## Repository Structure

```text
Amsterdam-Airbnb-pricing-model/
├── README.md
├── airbnb_pricing_report.pdf
├── airbnb_pricing_report.Rmd
├── airbnb_model_improvement_poster.pdf
└── airbnb_model_improvement_poster.Rmd
```

* `airbnb_pricing_report.pdf`: First-stage statistical report presenting the research question, dataset, initial regression model, interaction terms, diagnostic plots, preliminary findings, ethics discussion, and project plan.
* `airbnb_pricing_report.Rmd`: R Markdown source file used to produce the first-stage statistical report.
* `airbnb_model_improvement_poster.pdf`: Second-stage model improvement poster summarizing transformations, stepAIC model selection, nested ANOVA tests, VIF checks, final model, diagnostic plots, key findings, and limitations.
* `airbnb_model_improvement_poster.Rmd`: R Markdown source file used to produce the model improvement poster.

## Notes on Data

The dataset was originally derived from publicly available Airbnb listing information. If the full dataset cannot be redistributed, this repository provides the analysis files, report, poster, and documentation rather than the raw data file.

## Academic Integrity Note

This project was completed as part of a university coursework assignment and is shared for personal portfolio purposes only. Please do not copy, submit, or reuse this work as your own academic assignment.
