# Project 2 - Ames Housing Data and Kaggle Challenge


## Contents:
- [Background](#Background)
- [Data Dictionary](#Data-Dictionary)
- [Summary](#Summary)


## Background

This project aims to create a regression model based on the Ames Housing dataset and to predict the final sales price of houses. <br>
The analysis would be useful for prospective buyers searching for houses in Ames, Iowa, as well as homeowners and real estate companies putting their properties out for sale. The top 5 predictors that influences the sales price will be identified.


## Data Dictionary

This data dictionary serves to explain the list of final 51 features used in the modelling process.

| Feature              | Type    | Description                                                       |
|----------------------|---------|-------------------------------------------------------------------|
| Lot Frontage         | float64 | Linear feet of street connected to property                       |
| Lot Area             | int64   | Lot size in square feet                                           |
| Overall Qual         | int64   | Rating of overall material and finish of the house                |
| Overall Cond         | int64   | Rating of overall condition of the house                          |
| Mas Vnr Area         | float64 | Masonry veneer area in square feet                                |
| Exter Qual           | int64   | Quality of the material on the exterior                           |
| Bsmt Qual            | int64   | Evaluation of height of the basement                              |
| BsmtFin Type 1       | int64   | Rating of basement finished area                                  |
| BsmtFin SF 1         | float64 | Basement Type 1 finished square feet                              |
| Total Bsmt SF        | float64 | Total square feet of basement area                                |
| Heating QC           | int64   | Heating quality and condition                                     |
| 2nd Flr SF           | int64   | Second floor square feet                                          |
| Gr Liv Area          | int64   | Above grade (ground) living area square feet                      |
| Full Bath            | int64   | Full bathrooms above grade                                        |
| Bedroom AbvGr        | int64   | Bedrooms above grade (does NOT include basement bedrooms)         |
| Kitchen Qual         | int64   | Kitchen quality                                                   |
| Fireplaces           | int64   | Number of fireplaces                                              |
| Garage Cars          | float64 | Size of garage in car capacity                                    |
| Wood Deck SF         | int64   | Wood deck area in square feet                                     |
| Open Porch SF        | int64   | Open porch area in square feet                                    |
| Enclosed Porch       | int64   | Enclosed porch area in square feet                                |
| Property Age         | int64   | Age of property since construction                                |
| Yrs Since Remod      | int64   | Number of years since the last remodification or alteration       |
| MS Zoning_FV         | int64   | Zoning Classification - Floating Village Residential              |
| MS Zoning_RL         | int64   | Zoning Classification - Residential Low Density                   |
| MS Zoning_RM         | int64   | Zoning Classification - Residential Medium Density                |
| Neighborhood_BrkSide | int64   | Brookside                                                         |
| Neighborhood_Edwards | int64   | Edwards                                                           |
| Neighborhood_IDOTRR  | int64   | Iowa DOT and Rail Road                                            |
| Neighborhood_MeadowV | int64   | Meadow Village                                                    |
| Neighborhood_NAmes   | int64   | North Ames                                                        |
| Neighborhood_NoRidge | int64   | Northridge                                                        |
| Neighborhood_NridgHt | int64   | Northridge Heights                                                |
| Neighborhood_OldTown | int64   | Old Town                                                          |
| Neighborhood_Sawyer  | int64   | Sawyer                                                            |
| Neighborhood_Somerst | int64   | Somerset                                                          |
| Neighborhood_StoneBr | int64   | Stone Brook                                                       |
| Neighborhood_Timber  | int64   | Timerland                                                         |
| House Style_2Story   | int64   | Two story type house                                              |
| Exterior 1st_CemntBd | int64   | Exterior covering on house - Cement Board                         |
| Exterior 1st_HdBoard | int64   | Exterior covering on house - Hard Board                           |
| Exterior 1st_MetalSd | int64   | Exterior covering on house - Metal Siding                         |
| Exterior 1st_VinylSd | int64   | Exterior covering on house - Vinyl Siding                         |
| Exterior 1st_Wd Sdng | int64   | Exterior covering on house - Wood Siding                          |
| Mas Vnr Type_BrkFace | int64   | Masonry veneer type - Brick Face                                  |
| Mas Vnr Type_None    | int64   | No masonry veneer                                                 |
| Mas Vnr Type_Stone   | int64   | Masonry veneer type - Stone                                       |
| Garage Type_Attchd   | int64   | Garage attached to home                                           |
| Garage Type_BuiltIn  | int64   | Built-In (Garage part of house - typically has room above garage) |
| Garage Type_Detchd   | int64   | Garage detached from home                                         |
| Garage Type_NA       | int64   | No Garage                                                         |

Data dictionary for the original train and test dataset can be found [here.](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)


## Summary

Results from the regression models are shown below. The Lasso model obtained the highest cross val score and chosen as the best performing model.

| Regression Model | Train   | Validation | Cross Val Score | RMSE  | $\alpha$ |
|------------------|---------|------------|-----------------|-------|----------|
| OLS              | 0.90275 | 0.87373    | 0.89046         | 26276 | ---      |
| Ridge            | 0.90239 | 0.87607    | 0.88884         | 26213 | 38.27    |
| LASSO            | 0.90203 | 0.87642    | 0.89077         | 26243 | 209.45   |

We have identified the top 5 predictors for housing sales price and created a regression model for prediction:
1. Gross Living Area
2. Overall Qualily
3. Finished Basement Area
4. Masonry Veneer Area
5. Exterior Quality

However, the analysis is only limited to Ames and may not be suitable for other cities. Also, the dataset available is based on the transactions from 2006 to 2010. The financial and housing market may have evolved since then and may not be able to capture the current market trends. More data such as locations of schools, amenities and neighborhood details could also be useful for further analysis or be used as housing price predictors. 