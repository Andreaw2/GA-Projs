# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis


### Problem Statement
 For this project, I will be taking a look at the SAT scores  and participation rate in the United States. As an employee of the College Board - the organization that administers the SAT - I am looking to review the participation rates as the new format for the SAT was released in March 2016. I will be analyzing the participation rates over 2017 - 2019 and seek to improve the participation rate of its exams and provide recommendations for the teams in improving participation rates. 

---

### Contents:
- [Background](#Background)
- [Data Import & Cleaning](#Data-Import-and-Cleaning)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)|
- [Data Visualization](#Visualize-the-Data)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

---
### Background:

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry. Lately, more and more schools are opting to drop the SAT/ACT requirement for their Fall 2021 applications ([*read more about this here*](https://www.cnn.com/2020/04/14/us/coronavirus-colleges-sat-act-test-trnd/index.html)).

---

### Datasets Used

These datasets were used for my analysis:

* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))

**Make sure you cross-reference your data with your data sources to eliminate any data collection or data entry issues.**

#### Additional sources 

These datasets were used for my analysis:
External Research Sources:

1) States that require the SAT

https://blog.prepscholar.com/which-states-require-the-sat

2) Florida’s SAT scores fall, following national trend as more take the test

https://www.orlandosentinel.com/news/education/os-ne-sat-scores-florida-20190924-2ycpuogc2ndkrkwzdrkrjgrg64-story.html

3) SAT scores drop for 2019 class, but participation rises through testing in schools

https://www.washingtonpost.com/local/education/sat-scores-drop-for-2019-class-but-participation-rises-through-testing-in-schools/2019/09/23/332fc4d0-de11-11e9-8dc8-498eabc129a0_story.html

4) States That Provide A Free ACT/ SAT Test

https://www.collegeraptor.com/getting-in/articles/act-sat/states-act-sat-given-free/

---

### Data Import and Cleaning 

sat_2017 = pd.read_csv('../data/sat_2017.csv')
sat_2018 = pd.read_csv('../data/sat_2018.csv')
sat_2019 = pd.read_csv('../data/sat_2019.csv')

### 1. Display the data. Print first 5 rows of each dataframe

sat_2017.head()

sat_2018.head()

sat_2019.head()

### 2. Check for missing values

sat_2017.isnull().sum()

sat_2018.isnull().sum()

sat_2019.isnull().sum()

There are no missing values for the sat 2017-2019 data. 

### 3. Check for any obvious issues

sat_2017.shape

sat_2018.shape

sat_2019.shape

sat_2017[sat_2017['State'].duplicated()]

sat_2018[sat_2018['State'].duplicated()]

sat_2019[sat_2019['State'].duplicated()]

min_ebrw_sat_2017 = sat_2017['Evidence-Based Reading and Writing'].min()
min_math_sat_2017 = sat_2017['Math'].min()

print(f'The minumum scores for the 2017 SAT were: English: {min_ebrw_sat_2017}; Math: {min_math_sat_2017}')

min_ebrw_sat_2018 = sat_2018['Evidence-Based Reading and Writing'].min()
min_math_sat_2018 = sat_2018['Math'].min()

print(f'The minumum scores for the 2018 SAT were: English: {min_ebrw_sat_2018}; Math: {min_math_sat_2018}')


min_ebrw_sat_2019 = sat_2019['EBRW'].min()
min_math_sat_2019 = sat_2019['Math'].min()

print(f'The minimum scores for the 2019 SAT were: English: {min_ebrw_sat_2019}; Math: {min_math_sat_2019}')

The minimum score for 2017 SAT Math is 52, which is too low. More indepth look at the data is required. 

max_ebrw_sat_2017 = sat_2017['Evidence-Based Reading and Writing'].max()
max_math_sat_2017 = sat_2017['Math'].max()

print(f'The maximum scores for the 2017 SAT were: English: {max_ebrw_sat_2017}; Math: {max_math_sat_2017}')

max_ebrw_sat_2018 = sat_2018['Evidence-Based Reading and Writing'].max()
max_math_sat_2018 = sat_2018['Math'].max()

print(f'The maximum scores for the 2018 SAT were: English: {max_ebrw_sat_2018}; Math: {max_math_sat_2018}')


max_ebrw_sat_2019 = sat_2019['EBRW'].max()
max_math_sat_2019 = sat_2019['Math'].max()

print(f'The maximum scores for the 2019 SAT were: English: {max_ebrw_sat_2019}; Math: {max_math_sat_2019}')

sat_2019['Participation Rate']

There are two inputs in 2019 sat data with '-' in them. They will need to be removed and replaced with an appropriate value. 

### 4. Fix errors identified in 2. and 3. 


sat_2017.loc[sat_2017['Math'] == 52]

#1060 - 536 = 524
sat_2017.loc[sat_2017['Math'] == 52, 'Math'] = 524

sat_2019.loc[sat_2019['Participation Rate'] == '—' ]


sat_2019.loc[sat_2019['Participation Rate'] == '—', 'Participation Rate' ] = '0%'

It is noted that the participation rate for Puerto Rico and Virgin Islands were '-'. The values have been replaced with 0%. 

### 5. Display datatypes

sat_2017.dtypes

sat_2018.dtypes

sat_2019.dtypes

The participation rates for the sat data for 2017, 2018 and 2019 will have to be converted from a string to a float.


### 6. Fix datatypes

#participation rate is an object instead of an int. Convert % 

sat_2017['Participation'] = sat_2017['Participation'].map(lambda x: float(x.replace('%','')) / 100)

sat_2017.head()

sat_2018['Participation'] = sat_2018['Participation'].map(lambda x: float(x.replace('%','')) / 100)

sat_2018.head()

sat_2019['Participation Rate'] = sat_2019['Participation Rate'].map(lambda x: float(x.replace('%','')) / 100)

sat_2019.head()

### 7. Rename Columns

sat_2017.columns

#rename columns for 2017 
sat_2017.rename(columns={'State': 'State', 'Participation': '2017_Participation', 
                        'Evidence-Based Reading and Writing': '2017_EBRW', 
                         'Math': '2017_Math', 'Total': '2017_Total'}, inplace=True)

sat_2017.head()

sat_2018.rename(columns={'State': 'State', 'Participation': '2018_Participation', 
                        'Evidence-Based Reading and Writing': '2018_EBRW', 
                         'Math': '2018_Math', 'Total': '2018_Total'}, inplace=True)

sat_2018.head()

sat_2019.rename(columns={'State': 'State', 'Participation Rate': '2019_Participation', 
                        'EBRW': '2019_EBRW', 
                         'Math': '2019_Math', 'Total': '2019_Total'}, inplace=True)

sat_2019.head()

sat_2017.shape

sat_2018.shape

sat_2019.shape

### 8. Drop unnecessary rows


Removing virgin islands and puerto rico from sat 2019. The participation rate is not available but there is data for 2019 sat scores. 

sat_2019.drop(sat_2019[(sat_2019["State"] == 'Puerto Rico')].index, inplace = True)

sat_2019.drop(sat_2019[(sat_2019["State"] == 'Virgin Islands')].index, inplace = True)

sat_2019.shape

### 9. Merge

sat_merge = pd.merge(sat_2017, sat_2018, on='State')

sat_merge.head()

sat_data = pd.merge(sat_merge, sat_2019, on='State')

sat_data.head()

### 10. Additional cleaning as required

#set index to start at 1 instead of 0
sat_data.index +=1
sat_data.head()

### 11. Save merged dataframes as csv

sat_data.to_csv('sat_data_threeyears.csv')


### Data Dictionary


|Feature|Type|Dataset|Description|
|---|---|---|---|
|**State**|*String*|SAT 2017, SAT 2018, SAT 2019|  List of states in USA| 
|**2017_Participation**|*float*|SAT 2017|Participation rate of each state for the SAT in 2017|
|**2017_EBRW**|*integer*|SAT 2017|Average score for the Evidence-Based Reading and Writing section of the SAT exam in 2017|
|**2017_Math**|*integer*|SAT 2017|Average score for the Math section of the SAT exam in 2017|
|**2017_Total**|*integer*|SAT 2017|Average total score for both sections of the SAT exam in 2017|
|**2018_Participation**|*float*|SAT 2018|Participation rate of each state for the SAT in 2018|
|**2018_EBRW**|*integer*|SAT 2018|Average score for the Evidence-Based Reading and Writing section of the SAT exam in 2018|
|**2018_Math**|*integer*|SAT 2018|Average score for the Math section of the SAT exam in 2018|
|**2018_Total**|*integer*|SAT 2018|Average total score for both sections of the SAT exam in 2018|
|**2019_Participation**|*float*|SAT 2019|Participation rate of each state for the SAT in 2019|
|**2019_EBRW**|*integer*|SAT 2019|Average score for the Evidence-Based Reading and Writing section of the SAT exam in 2019|
|**2019_Math**|*integer*|SAT 2019|Average score for the Math section of the SAT exam in 2019|
|**2019_Total**|*integer*|SAT 2019|Average total score for both sections of the SAT exam in 2019|

