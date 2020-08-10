# Vote by Mail (VBM) States and Voter Turnout

### Group 11 Team Members
* Brock Vriesman
* Johnny Whitaker
* Kathy Gural

## Proposal and Hypotheses
* To conduct an exploration of a potential relationship between the introduction of Vote by Mail (VBM) options in specific states and changes in those states’ voter turnout for Midterm and Presidential election years.
* Null Hypothesis: A state’s introduction of Vote by Mail (VBM) options does not change voter turnout in the state

## Questions
* What is the current state of voter turnout nationally by state?
* How has voter turnout changed nationally overall? Nationally for states without VBM options? For states with VBM options?
* After a state’s introduction of VBM options, does the voter turnout proportion change significantly?
* Are there correlations between demographic characteristics of a state’s population and the proportion of voter turnout?
* What is the level of influence of subjective sociopolitical factors on the proportion of voter turnout nationally, and state-by-state?

## Datasets Used
* United States Elections Project Voter Turnout Data
    #### Organized by state; covering even-year election cycles from 1980 – 2016
    ** Placeholder for link
* Census API Data
    #### Demographic information by state for 2011 – 2017
    ** Placeholder for link

## Tasks
* Data exploration and cleanup
    ** Census API - Brock Vriesman, post data pull filtering by Johnny Whitaker and Kathy Gural
    ** United States Elections Project Voter Turnout Data - Johnny Whitaker and Kathy Gural
    ** Data Merge - Johnny Whitaker and Kathy Gural
* Data Analysis
    ** Brock Vriesman, Johnny Whitaker and Kathy Gural
* Regression Analysis
    ** Brock Vriesman
* Conclusions
    ** Brock Vriesman, Johnny Whitaker and Kathy Gural

## Task Details
### Data Exploration and Cleanup
    ** Placeholder for data cleansing screenshots and details

### Data Analysis
    

Joint Data
Combination of voter turnout data and census data, joined by state for the even-year election cycles 2012 - 2016

=======

# New line on brock_branch
>>>>>>> fc23df1a116f95bfb5a9e73fa3d7d3a9cf6d4f93

================================
## Regression Analysis write-up:

In addition, we analyzed possible areas of correlation with voter turnout
among key Census demographics. Picking several of the most pertinent demos
from the Datamade Census wrapper, we pulled Census data for the even election
years between 2012 and 2016, which the team then cleaned and merged.

After adding calculated rate fields to supplement the Census raw counts,
we ran a regression analysis on three groups: 1) All State/Year combinations (N=134),
2) All VBM (Vote by Mail) State/Years (n1=15), and 3) All Non-VBM State/Years (n2=119).

The results of the analysis revealed weak correlation between Census fields
and voter turnout. While disappointing, it did seem somewhat logical that
factors influencing voter turnout are more nuanced than the characteristics
found in the high-level Census demographic tables we were working with.

Despite the general weakness in the correlations, we did take a deeper look
at a factor we thought might be somewhat related and happened to have the
strongest correlation to voter turnout: Poverty Rate.

In the 'All States' group the r-value for Poverty Rate was about -0.26 meaning
as the Poverty Rate goes down, the voter turnout tends to go up. Our next step
was to pull the VBM and Non-VBM states into their own dataframes and run the
regression analysis again on both groups.

What we found was the Non-VBM states tended to look like the All States group,
which, due to the size of the Non-VBM states group, was not surprising. When
looking at the VBM states group, however, we did not find the same trend. The
r-value for Poverty Rate in the VBM group was 0.29. Instead of voter turnout
going down as Poverty Rate rose, it seemed to be going up.

It is possible we are seeing in the VBM states that allowing citizens to vote
by mail may benefit, or at least not limit voting based on that economic factor.
What this may mean is that voting by mail is the effect of enfrancising more
voters.

While not conclusive, it does provide an area to continue examination.
