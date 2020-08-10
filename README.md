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
    ** http://www.electproject.org/home/voter-turnout/voter-turnout-data
* Census API Data
    #### Demographic information by state for 2011 – 2017
    ** https://www.census.gov/data/api.html

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
* Voter Data
We examained the data structure and evaluated the volume of missing values. The only Vote by Mail state which was missing any data was Colorado, which had two years not included.
Additionally, less than 15% of the entries had missing values, so we dropped all incomplete rows and ended up with a cleaned dataset which we believed to be of acceptable strength to continue our analyses. Additionally, we added in the state abbreviation category to interact easily with API wrappers and packages. The final dataset was saved into csv format as voter_data.

* Census Data
Utilizing the Census and US wrappers, we retrieved demographic information from the Census API including factors around age, gender, ethnicity, public infrastructure strength, etc.
We then organized the data into an aggregate dataframe containing all demographic fields, for all states, for 2012, 2014, and 2016. Encoding of variables was done to increase the legibility and ease of interaction with the API calls. The dataset was saved into csv format as census_data_12_to_16. 

* Joint Data
To incoporate the demographic information from the census data into the voter turnout data, we then proceeded to create a joint dataset featuring all fields for both datasets covering 2012, 2014, 2016. The merge was conducted using state name as the common field, and an inner join was used so as to not create rows with missing values. The joint dataset was then saveed into csv format as joint_data_12_to_16.
Next, several fields from the data featured formatting which needed to be removed so as to conduct mathematical operations with the data. Dollar values had to have dollar signs, commas, and extraneous 0s removed, then be encoded as integers. Percentagees had to have percent signs removed, then be encoded as float values. These changes were implemented and saved into a new dataframe which was saved into csv format as joint_data_12_to_16_noformatting.
Both dataset were kept so that if we wished to display any values with the dollar or percentage formatting, we could easily do so.

### Data Analysis:

We began our analysis by creating dataframes for each of the individual Vote by Mail states, so as to be able to look at their individual trends in voter turnout graphically. After assembling datasets for Oregon, Washington, Colorado, Utah, and Hawaii, we generated two visualizations for each state. The first examines changes in population and gross voter turnout from 1980 - 2016; for Oregon, Washington, & Colorado this shows a most linear and positive correlation. Utah and Hawaii however, display generally negative trends over time in voter turnout, with Hawaii having the largest reduction in voter turnout of any Vote by Mail state. All states display noticeably lower turnouts in non Presidential election years. The second visualization shows proportional voter turnout and displays much less linearly; the plots are defined by steep peaks and valleys of voter turnout, which more explictly exhibit the significantly lower voter turnout in non Presidential election years. On all of the visualizations for the individual Vote by Mail states, the year of the introduction of the Vote by Mail option is highlighted with a vertical golden line, though visually it is difficult to discern if there is any significant change in voter turnout after the introduction of Vote by Mail.
Building off of the state-by-state visualizations, we generated a table which examines the average voter turnout in Vote by Mail states before and after the introduction of the option. That figure was then compared to the averages of All Vote by Mail states, all Non Vote by Mail states, and all states together. Correlating to previous findings via the visualizations; Oregon, Washington, and Colorado were all above the national average before and after introduction of Vote by Mail, while Utah and Hawaii were below the national average and both states also have an overall decline in voter turnout from 1980 to 2016.
Cumulatively these findings do not indicate that there is any signficant increase in voter turnout after the introduction of a Vote by Mail option; trends before the introduction appear through both visual and statistical analysis, to continue on very similarly despite introduction of Vote by Mail option.
    

=======


================================
## Regression Analysis write-up:

We analyzed possible areas of correlation with voter turnout
among key Census demographics. Picking several of the most pertinent demos
from the Datamade Census wrapper, we pulled Census data for the even election
years between 2012 and 2016, which the team then cleaned and merged.

After adding calculated rate fields to supplement the Census raw counts,
we ran a regression analysis on three groups: 1) All State/Year combinations,
2) All VBM (Vote by Mail) State/Years, and 3) All Non-VBM State/Years.

The results of the analysis revealed weak correlation between Census fields
and voter turnout. While disappointing, it did seem somewhat logical that
factors influencing voter turnout are more nuanced than the characteristics
found in the high-level Census demographic tables we were working with.

Despite the general weakness in the correlations, we did take a deeper look
at a factor we thought might be somewhat related and happened to have the
strongest correlation to voter turnout: Poverty Rate.

In the 'All States' group the r-value for Poverty Rate was about -0.26 meaning
as the Poverty Rate goes down, the voter turnout tends to go up. Our next step
was to the regression analysis on the VBM and Non-VBM groups.

What we found was the Non-VBM group tended to look like the All States group,
which, due to the size of the Non-VBM group, was not surprising. When
looking at the VBM group, however, we did not find the same trend. The
r-value for the VBM group was 0.29. Instead of voter turnout
going down as the Poverty Rate rose, it seemed to be going up.

Further analysis is needed to understand the potential impact voting by mail may have
on voters at or below the poverty line in these states. If these results were to
persist with more data, that would be an indication of the positive impact of the
VBM system on voter enfranchisement.
