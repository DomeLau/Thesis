# Master's Thesis Dominik Lauer

**The Impact of Transitory Income Shocks on Labor Supply Decisions: A Machine Learning Approach**

This GitHub Repository contains the files for my Master's thesis. Right here, I give an overview of the data and code files accompanying the thesis. Further, I include a description of the main variables used during the analysis. 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Python Code Files

## Data Cleaning

This file contains the first stage of the data cleaning process. I filter out households that, for example, report negative income values, are not observed in waves 1 or 2 or have less than 8 monthly observations. Comments in the code give further details.

## Final Code Household Data
 
This file contains the main analysis of the thesis at the household level. In the beginning I load the cleaned csv file that I produced in the Data Cleaning code file.                         I exclude further households based on income and family size (detailed description in the thesis PDF file and the code itself). Then I split the data set in two groups and set up the uplift modeling. In the following, I make estimations using the RandomForestRegressor algorithm and report results. The next sections contain further analysis in terms of feature importance, extrapolation and partial dependence plots.

## Final Code Individual Data

This file contains a shorter analysis of the data at individual level. Only Table 5.4, Figure 5.9, Tables A.8 and A.9 in the appendix as well as Figure B.7 in the appendix rely on this data. The structure is more or less identical to the structure in the Final Code Household Data file.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# DTA Files

## household.dta

This file contains the raw data at the household level. I use it in the Final Code Household Data Python file.

## individual.dta

This file contains the raw data at the individual level. I use it in the Final Code Individual Data Python file.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# PDF Files

## Master’s Thesis Dominik Lauer

This file contains the written thesis as PDF file. It includes background information, theoretical explanations and the analysis of the estimation results. It also contains a variety of tables and plots in the appendix section. 

## Supplementary Appendix

This file contains more graphical illustrations. 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Codebook for variables used in the main analysis (Final Code Household Data)
Variable descriptions from the SIPP 2008 Panel Waves 01-10 Core Data Dictionary

- tfearn

Reaggregated total family earned income in $US for relevant month of the reference period after topcoding amounts.

- spouse

Dummy variable, 1 if household’s head is married, 0 if not.

- flex

Describes the number of hourly workers in a household.

- tage

Household’s head age as of last birthday.

- famsize

Describes the number of people living in a household.

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

- reb_month_numerical

Numerical value for month of rebate payment. Values from 1 to 12.

- swave

Numerical value for observation’s wave. Values are 1 or 2. 

- year

Indicates the observation’s year. Values are 2008 or 2009.

-	srefmon_numerical

Numerical value for the reference month of the observation. Values from 1 to 4.

-	rebate_payment

Dummy variable, 1 if rebate payment occurs for observation, 0 otherwise.

- month_numerical

Numerical value for month of observation. Values from 1 to 12. 

- rebate_uplifting

Describes the size of the rebate payment in rebate months (rebate_payment == 1).

- rebate_uplifting_spend

Indicates whether the rebate received is used for increasing consumption spending (rebate_payment == 1).
0 .not in universe
1 .yes
2 .no

- rebate_uplifting_save

Indicates whether the rebate received is used for increasing savings (rebate_payment == 1).
0 .not in universe
1 .yes
2 .no

- rebate_uplifting_debt

Indicates whether the rebate received is used for paying off debt (rebate_payment == 1). 
0 .not in universe
1 .yes
2 .no

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Codebook for variables used in the secondary analysis (Final Code Individual Data)
Variable descriptions from the SIPP 2008 Panel Waves 01-10 Core Data Dictionary

- tpearn

personal earnings in $US for relevant month of the reference period

- epayhr1

Paid by the hour. 
-1 .not in universe
1 .yes (paid by the hour)
2 .no (set annual salary or other way) 

- ehrsall

Usual hours worked at all jobs during the reference period
-1 .not in universe
0 .not determined
1:99 .hours per week

- rmhrswk

Usual hours worked per week recode in month
-1 .Not in Universe 
0 .Did not work (did not have a job, or was absent without pay from a job all weeks in month) 
1 .All weeks 35+ 
2 .All weeks 1-34 hours 
3 .Some weeks 35+ and some weeks less than 35, all weeks equal to or greater than 1 hour 
4 .Some weeks 35+, some weeks 1-34 hours, some weeks 0 hours 
5 .At least 1 but not all weeks 35+ hours, all other weeks 0 hours 
6 .At least 1 week but not all weeks 1 to 34 hours, all other weeks 0 hours

- eptresn

Main reason for working less than 35 hours
-1 .Not in Universe 
1 .Could not find full-time job 
2 .Wanted to work part time 
3 .Temporarily unable to work full-time because of injury 
4 .Temporarily unable to work full-time because of illness
5 .Unable to work full-time because of chronic health condition/disability 
6 .Taking care of children/other persons 
7 .Full-time workweek is less than hours 
8 .Slack work or material shortage 
9 .Participated in a job sharing arrangement 
10 .On vacation 
11 .In school 
12 .Other

- eptwrk

Worked less than 35 hours some weeks
-1 .Not in Universe 
1 .Yes 
2 .No

- eawop

Had full-week unpaid absences from work
-1 .Not in Universe 
1 .Yes 
2 .No

- eabre

Main reason for being absent without pay
-1 .Not in Universe 
1 .On layoff (temporary or indefinite) 
2 .Slack work or business conditions 
3 .Own injury 
4 .Own illness/medical problems 
5 .Pregnancy/childbirth 
6 .Taking care of children 
7 .On vacation/personal days 
8 .Bad weather 
9 .Labor Dispute 
10 .New job to begin within 30 days 
11 .Participated in a job-sharing arrangement 
12 .Other

- tmlmsum

Amount of income from moonlighting or extra jobs in this month
0 .None or not in universe 
1:66666 .Dollars

- rmesr

Employment status recode for month
-1 .Not in Universe 
1 .With a job entire month, worked all weeks. 
2 .With a job entire month, absent from work without pay 1+ weeks, absence not due to layoff 
3 .With a job entire month, absent from work without pay 1+ weeks, absence due to layoff 
4 .With a job at least 1 but not all weeks, no time on layoff and no time looking for work 
5 .With a job at least 1 but not all weeks, remaining weeks on layoff or looking for work 
6 .No job all month, on layoff or looking for work all weeks. 
7 .No job all month, at least one but not all weeks on layoff or looking for work 
8 .No job all month, no time on layoff and no time looking for work. 

- rmwksab

Number of weeks absent without pay from job in month
-1 .Not in Universe 
0 .0 weeks (that is, did not have a job, or not absent without pay from a job) or not applicable 
1 .1 week 
2 .2 weeks 
3 .3 weeks 
4 .4 weeks 
5 .5 weeks (if applicable)

- rmwkwjb

Number of weeks with a job in month
-1 .Not in Universe 
0 .0 weeks (that is, did not look for work, and was not on layoff) or not applicable 
1 .1 week 
2 .2 weeks 
3 .3 weeks 
4 .4 weeks 
5 .5 weeks (if applicable)

- rwksperm

Number of weeks in this month
-1 .Not in Universe 
4 .Four weeks 
5 .Five weeks

- epdjbthn

Paid job during the reference period
-1 .Not in Universe
1 .Yes 
2 .No




