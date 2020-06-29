# Master's Thesis Dominik Lauer

**The Impact of Transitory Income Shocks on Labor Supply Decisions: A Machine Learning Approach**


This GitHub Repository contains the files for my Master's thesis. Right here, I give an overview of the data and code files accompanying the thesis. Further, I include a description of the main variables used during the analysis. 

**Python Code Files**

- Data Cleaning

This file contains the first stage of the data cleaning process. I filter out households that, for example, report negative income values, are not observed in waves 1 or 2 or have less than 8 monthly observations. Comments in the code give further details.

- Final Code Household Data
This file contains the main analysis of the thesis at the household level. In the beginning I load the cleaned csv file that I produced in the Data Cleaning code file. I exclude further households based on income and family size (detailed description in the thesis PDF file and the code itself). Then I split the data set in two groups and set up the uplift modeling. In the following, I make estimations using the RandomForestRegressor algorithm and report results. The next sections contain further analysis in terms of feature importance, extrapolation and partial dependence plots.

