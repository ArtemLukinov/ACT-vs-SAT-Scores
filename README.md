# Project 1: Analyzing ACT and SAT data

# Problem Statement

The state of California has many school districts. This project aims to identify the districts that have the worst overall student performance on the SAT and ACT tests and the worst participation rates so that your organization can develop an optimal go-to-market strategy.

## Materials used:

-   [`act_2019_ca.csv`](https://git.generalassemb.ly/krosaf4eg/dsir-125/blob/master/projects/project-01-main/data/act_2019_ca.csv): 2019 ACT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/)  |  [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutact19.asp))

-   [`sat_2019_ca.csv`](https://git.generalassemb.ly/krosaf4eg/dsir-125/blob/master/projects/project-01-main/data/sat_2019_ca.csv): 2019 SAT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/)  |  [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutsat19.asp))			

## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|district_code|object|Aggregate|Unique code for school district, shared between ACT & SAT|
|record_type|object|Aggregate|record types: School, District, State|
|district_name|object|Aggregate|school district name|
|enrolled_num|float|Aggregate|number of students enrolled in 12th grade|
|num_takers|float|Aggregate|number of students taking either ACT or SAT test|
|pct_above_bm|float|Aggregate|percentage of students with results above benchmark for either ACT or SAT|
|pct_part|float|Aggregate|participation percentage|

## Summary of analysis

 1. ACT and SAT datasets were combined into one with concentration on
    two key data points: 
    
     - participation percentage,  	 	*calculated from number of enrolled 12th-graders and number of test takers*
     - percentage of results above the benchmark, 	 *for ACT scores - score above 21, for SAT scores - above benchmark set by US College
    Board - methodology can be found
    [here](https://collegereadiness.collegeboard.org/pdf/educator-benchmark-brief.pdf)*

    

 2. Some school districts participate in ACT or SAT programs and a few
    in both. ACT and SAT have different scoring systems. In order to
    standardize the metrics, scores were looked at as percentage over
    benchmark and the data was filtered to reflect that. For districts
    with both points of data, mean was used.
 3. Initialized EDA with determining correlation between data columns. Observed no unexpected findings: 
		 - number of test takers has direct correlation with number of enrolled students, 
		 - slight non-linear correlation between participation rates and test results. It appears higher participation rates cause a slight decline in test results.
4.  With few data outliers, the quartiles are almost identical in size, also proven by a histogram of percentages over benchmark distribution.

## Conclusions

Generated lists of 20 school districts with lowest scores compared to the benchmark and lowest participation rates to be used for priority business deployment. 

20 lowest scoring districts:

 1. Golden Plains Unified
 2. Inyo County Office of Education
 3. Williams Unified
 4. Tulelake Basin Joint Unified
 5. Firebaugh-Las Deltas Unified
 6. Reef - Sunset Unified
 7. Cloverdale Unified
 8. Ravenswood City Elementary
 9. SBE - Academia Avance Charter
 10. San Pasqual Valley Unified
 11. Mendota Unified
 12. Compton Unified
 13. SBE - The School of Arts and Enterprise
 14. Lindsay Unified
 15. Cutler-Orosi Joint Unified
 16. Borrego Springs Unified
 17. Le Grand Union High
 18. Farmersville Unified
 19. South Monterey County Joint Union High
 20. Gonzales Unified

20 lowest participation rates:

 1. Ravenswood City Elementary
2. Los Molinos  Unified
3. Nuview  Union
4. SBE - The School of Arts and Enterprise
5. Hawthorne
6. Lennox
7. Lawndale Elementary
8. Shoreline Unified
9. Modoc Joint Unified
10. Fontana Unified
11. Tulelake Basin Joint Unified
12.  SBE - Academia Avance  Charter
13.  Natomas Unified
14.  Bonsall Unified
15.  Reef-Sunset Unified
16.  Santa Ana Unified
17.  Covina-Valley Unified
18.  Norwalk-La Mirada Unified
19.  Scott Valley Unified
20.  Coronado Unified

