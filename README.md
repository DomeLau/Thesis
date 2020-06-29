# Master's Thesis Dominik Lauer

**The Impact of Transitory Income Shocks on Labor Supply Decisions: A Machine Learning Approach**


This GitHub Repository contains the files for my Master's thesis. Right here, I give an overview of the data and code files accompanying the thesis. Further, I include a description of the main variables used during the analysis. 

**Python Code Files**

- Data Cleaning

This file contains the first stage of the data cleaning process. I filter out households that, for example, report negative income values, are not observed in waves 1 or 2 or have less than 8 monthly observations. Comments in the code give further details.

- Final Code Household Data
 
This file contains the main analysis of the thesis at the household level. In the beginning I load the cleaned csv file that I produced in the Data Cleaning code file.                         I exclude further households based on income and family size (detailed description in the thesis PDF file and the code itself). Then I split the data set in two groups and set up the uplift modeling. In the following, I make estimations using the RandomForestRegressor algorithm and report results. The next sections contain further analysis in terms of feature importance, extrapolation and partial dependence plots.

- Final Code Individual Data

This file contains a shorter analysis of the data at individual level. Only Table 5.4, Figure 5.9, Tables A.8 and A.9 in the appendix as well as Figure B.7 in the appendix rely on this data. The structure is more or less identical to the structure in the Final Code Household Data file.

**DTA Files**

- household.dta

This file contains the raw data at the household level. I use it in the Final Code Household Data Python file.

- individual.dta

This file contains the raw data at the individual level. I use it in the Final Code Individual Data Python file.

**PDF Files**

- Master’s Thesis Dominik Lauer

This file contains the written thesis as PDF file. It includes background information, theoretical explanations and the analysis of the estimation results. It also contains a variety of tables and plots in the appendix section. 

- Supplementary Appendix

This file contains more graphical illustrations. 

**Codebook for variables used in the main analysis (Final Code Household Data)**
Variable descriptions from the SIPP 2008 Panel Waves 01-10 Core Data Dictionary

- tfearn

Reaggregated total family earned income in $US for relevant month of the reference period after topcoding amounts

- spouse

Dummy variable, 1 if household’s head is married, 0 if not

- flex

Describes the number of hourly workers in a household

- tage

Household’s head age as of last birthday

- famsize

Describes the number of people living in a household

- selfemp

Indicator whether household’s head is a self employed worker: 
0 .not in universe 
1 .yes
2 .no

- moonlit

Describes if household’s head does work outside of her regular job, such as freelancing, consulting, or moonlighting. 
0 .not in universe
1 .yes
2 .no

- 
