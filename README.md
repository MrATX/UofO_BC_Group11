# UofO_BC_Group11
Project 1 repo for Group 11
<<<<<<< HEAD
Made a change.
=======
<<<<<<< HEAD
#BRANCH EDIT TESTERZ
=======

# New line on brock_branch
>>>>>>> brock_branch
>>>>>>> fc23df1a116f95bfb5a9e73fa3d7d3a9cf6d4f93

================================
Regression Analysis write-up:

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
