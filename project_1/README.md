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

---

## Conclusions and Recommendations

The key takeaways from the data for the SAT from 2017 - 2019 are: 

1) Strong negative correlation between the participation rate and the overall average SAT scores. states that had low participation rate and high scores had students that are well-prepared for the SAT. While states with high participation rates have more students than ever took the exam, many of them from low-income families or from families with no history of college attendance. Those students typically do not score as well on the exam as teenagers from wealthier families and with parents who are college graduates. Despite relatively high variance on the SAT among states below 40% participation, a linear relationship can still be intepreted between participation and state average.

2) More states are seeing 100% SAT participations from 4 states in 2017 to 5 states in 2018 and 8 states in 2019. 

2017 - Connecticut, Delaware, District of Columbia and Michigan

2018 - Connecticut, Delaware, Colorado, Idaho and Michigan 

2019 - Colorado, Connecticut, Delaware, Florida, Idaho, Illinois, Michigan and Rhode island 

We are able to see an increasing trend in states taking the SAT test as more states are making this tests mandatory, resulting in 100% participation rates in the SAT tests. Certain states are also offering SAT for free for all juniors. e.g. Illinois, Idaho, Michigan, Connecticut, Colorado (for jumiors only),Delaware, District of Columbia (Juniors & Seniors), Rhode Island (Juniors). There is greater accessibility to SAT tests for students in these states.

Source: https://www.collegeraptor.com/getting-in/articles/act-sat/states-act-sat-given-free/


3) SAT Participation rates have been growing consistently from 2017 - 2019. Through the boxplot, we are able to notice that the  median for the participation has increased gradually from 2017 - 2019.There are also positive correlations in the participation rates from 2017 -2019 with more than 0.8.



Recommendations in improving the SAT participation rates would include the following:

1) The College Board can increase efforts in working with states, collaborating with states to increase participation rates. Work with states to require SAT in their education system. In supporting this decision, the college board will have to work with educators to ensure that the SAT is fair in measuring a high school student's readiness for college. 

2) The College Board can also offer subsidies for taking the SAT tests to support students with financial difficulties, increasing accessibility for students to take the test while removing the financial burden for these students.

3) Implementing online testing will ensure that SAT is more widely available internationally and also to reduce the risk during the covid pandemic. 

4) States with less than 50% participation rate and average test scores lower than 25% quartile will require more support (Oklahoma, West Virginia, Utah). The college board will be able to step in and offer these states support by collaborating with the Board of Education to improve participation rates as well as test scores. This is inline with the College Board's mission to connect students to college success and opportunity. Additionally, the college board is also able to offer subsidies for students who are unable to participate in the tests due to financial concerns. The college board can offer more resources for higher education, test taking and teaching materials to encourage students to take on the SAT tests, increasing participation rate for these states. 

Oklahoma has appeared on the lists for both 2017 and 2019. Participation rate has increased gradually from 7% to 22% from 2017 - 2019. More attention is required from the college board to help support the education system at Oklahoma.Support is required at Utah as participation rate has remained relatively the same from 2017-2019 at 3-4%. The college board will need to partner with the states to help increase SAT participation rates, collaborating with the state to increase access to the SAT test. The college board can offer subsidies for students who are unable to participate in the tests due to financial concerns and work with the state on making the SAT test mandatory. 

West Virginia on the other hand has 99% participation rate in 2019 as all juniors must take the SAT unless taking the West Virginia Alternative Summer Assessment. However the sat scores for the state was below the 25% quartile for 2018 and 2019. The college board will be able to partner with the state to offer materials to help polish the student's test taking skills. 