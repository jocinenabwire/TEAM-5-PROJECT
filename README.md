# MISSING MIGRANTS PROJECT 

## Business Understanding
The International Organization for Migration (IOM)’s Missing Migrants Project records incidents in which migrants, including refugees and asylum-seekers, have died at state borders or in the process of migrating to an international destination. It was developed in response to disparate reports of people dying or disappearing along migratory routes around the world.The data is used to inform the Sustainable Development Goals Indicator 10.7.3 on the “[n]number of people who died or disappeared in the process of migration towards an international destination.”

More than 40,000 people have lost their lives during unsafe migration journeys since 2014. The data collected by the Missing Migrants Project bear witness to one of the great political failures of modern times. IOM calls for immediate safe, humane and legal routes for migration. Better data can help inform policies to end migrant deaths and address the needs of families left behind.

## Business problem
Every year, hundreds of thousands of people leave their homes in search of a better life. In the process, many are injured or killed. Thus, we came up with the Missing Migrants Project to track deaths of migrants and those who have gone missing along migratory routes across the globe.
### Objective
To find the leading cause of death and the factors that may add/influence it.
### Research Questions
What was the leading cause of death?
Which migrants’ region of origin had the highest number of dead people?
Which migrants’ region of origin had the highest number of missing people?
What was the most affected nationality?
Which incident region had the highest number of dead people?
Which incident region had the highest number of missing people?
## Business impact
To assist IOM to identify ways of curbing death among migrants and understand the background of those who are most at risk to lose their life during migration.

## Assessing the Situation
### Resource Inventory
#### Datasets
Missing Migrants 
#### Software
Python-pandas
Google Collaboratory
GitHub
#### Assumptions
The data provided is correct.
#### Constraints
There are no constraints.

## Data Understanding
### Data Understanding Overview
We have one dataset which is:
Missing Migrants Project
### Data Description
The dataset has 12 columns which are as explained below:

1. Web ID-An automatically generated number used to identify each unique entry in the dataset.
2. Region of incident-The region in which an incident took place. 
3. Reported date-Estimated date of death. In cases where the exact date of death is not known, this variable indicates the date in which the body or bodies were found. In cases where data are drawn from surviving migrants, witnesses or other interviews, this variable is entered as the date of the death as reported by the interviewee.  At a minimum, the month and the year of death is recorded. In some cases, official statistics are not disaggregated by the incident, meaning that data is reported as a total number of deaths occurring during a certain time period. In such cases the entry is marked as a “cumulative total,” and the latest date of the range is recorded, with the full dates recorded in the comments.
4. Reported year-The year in which the incident occurred.
5. Reported month-The month in which the incident occurred.
6. Number dead-The total number of people confirmed dead in one incident, i.e. the number of bodies recovered.  If migrants are missing and presumed dead, such as in cases of shipwrecks, leave blank.
7. Number missing-The total number of those who are missing and are thus assumed to be dead.  This variable is generally recorded in incidents involving shipwrecks.  The number of missing is calculated by subtracting the number of bodies recovered from a shipwreck and the number of survivors from the total number of migrants reported to have been on the boat.  This number may be reported by surviving migrants or witnesses.  If no missing persons are reported, it is left blank.
8. Affected Nationality-Country of birth of the decedent. If unknown, the entry will be marked “unknown”.
9. Region of origin-Region of origin of the deceased(s). In some incidents, the region of origin may be marked as “Presumed” or “(P)” if migrants travelling through that location are known to hail from a certain region. If unknown, the entry will be marked “unknown”.
10. Cause of death-The determination of conditions resulting in the migrant's death i.e. the circumstances of the event that produced the fatal injury. If unknown, the reason why is included where possible.  For example, “Unknown – skeletal remains only”, is used in cases in which only the skeleton of the deceased was found.
11. Location coordinate-I.e lat and lon.Place where the death(s) occurred or where the body or bodies were found. In many regions, most notably the Mediterranean, geographic coordinates are estimated as precise locations are not often known. 
12. Information source-Name of source of information for each incident. Multiple sources may be listed.
13. Source quality /reliability-Incidents are ranked on a scale from 1-5 based on the source(s) of information available. If an incident is between 1-2 its described as partially verified but if it's from 3-5 then its recorded as verified
## Data Preparation
The following steps were followed.
Loading Data
Imported pandas and numpy.
Loaded the datasets using the links then previewed them, head and tail respectively as shown:
## Data Understanding
Checked for the information. There are three datatypes in our dataframe. Mainly; integers, objects and floats
###   Column                Non-Null Count  Dtype  
---  ------                --------------  -----  
 0   id                    2420 non-null   int64  
 1   cause_of_death        2217 non-null   object 
 2   region_origin         1977 non-null   object 
 3   affected_nationality  845 non-null    object 
 4   missing               271 non-null    float64
 5   dead                  2318 non-null   float64
 6   incident_region       2410 non-null   object 
 7   date                  2411 non-null   object 
 8   source                2413 non-null   object 
 9   reliability           2096 non-null   object 
 10  lat                   2416 non-null   float64
 11  lon                   2416 non-null   float64
Described the dataframe and got the basic statistical information as show below:
Checked the shape- it has 2420 rows and 12 columns.
Checked for duplicates-it had no duplicates
## Data Cleaning
### Validity
Irrelevant Data: Dropped columns which were not necessary: source, latitude and longitude. Remaining with 9 columns.
Outliers: Checked for outliers in the missing migrant and dead migrants columns
### Completeness
Missing values
Each column has missing values apart from the id column.
We replaced the missing values from both the missing and dead columns with 0 rather than dropping them or replacing them with the mean/median because of how biased the data would be. We cannot assume/force the no of fatalities that take place because this will hinder the  sincerity of the results.
We replaced missing values in columns { cause_of_death, region_origin, affected_nationality, incident_region, reliability } with unknown
### Consistency
Duplicates: no duplicates were present in the dataset
### Uniformity
Date conversion: changing the date column data type from an object to date_time data type
## Data Analysis
Most of the migrants lost their lives through drowning.
The migrant’s region of origin that had the highest number of deaths is unknown. This was then followed by the presumed Horn of Africa region.
The region of origin with the highest number of missing people is unknown, followed by people of mixed race and closely followed by the people of the Sub-Saharan region.
The most affected nationality was unknown, then followed by Mexico.
Most death incidents occurred in the Mediterranean region.
The incident region with the highest number of missing people was also the Mediterranean region.
## Recommendations
Since most deaths are due to drowning,security patrols should be increased along the water routes especially in the Mediterranean region.
More emphasis should be put on orderly and humane management of migration to avoid deaths.
Provide humanitarian assistance to migrants in need, including refugees and internally displaced people.

The analysis above was done using Google collab.
