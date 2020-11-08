# Project 1: SAT & ACT Analysis

## Problem Statement
As the new format for the SAT was released in March 2016, the College Board wants to track the statewide participation to analyze in which states require more budget in order to increase the SAT participation rates and tracking the scores by participants would allow us to evaluate and find out how are the participants performing with the change in format of the SAT.

We'll seek to identify trends in the data and combine our data analysis with outside research to identify likely factors influencing participation rates and scores in various states

## Executive Summary

If you want to, it's great to use relative links to direct your audience to various sections of a notebook. **HERE'S A DEMONSTRATION WITH THE CURRENT SECTION HEADERS**:

### Contents:
- [2017 Data Import & Cleaning](#Data-Import-and-Cleaning)
- [2018 Data Import and Cleaning](#2018-Data-Import-and-Cleaning)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Visualization](#Visualize-the-data)
- [Descriptive and Inferential Statistics](#Descriptive-and-Inferential-Statistics)
- [Outside Research](#Outside-Research)
- [Sources](#Sources)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

#### Data Dictionary for 2017
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|act_2017<br>sat_2017|The states in which the participation rates and scores are being recorded for.|
<br>
|**act17_par_percentage**|*float*|act_2017|Average 2017 ACT percentage rate for each State.|
|**act17_english**|*float*|act_2017|Average 2017 ACT English scaled score for each State.|
|**act17_math**|*float*|act_2017|Average 2017 ACT Math scaled score for each State.|
|**act17_reading**|*float*|act_2017|Average 2017 ACT scaled Reading score for each State.|
|**act17_science**|*float*|act_2017|Average 2017 ACT scaled Science score for each State.|
|**act17_composite**|*float*|act_2017|Average 2017 ACT scaled Composite score, which is the average of all individual subject score for each State.|
<br>
|**sat17_par_percentage**|*float*|sat_2017|Average 2017 SAT percentage rate for each State.|
|**sat17_erw**|*integer*|sat_2017|Average 2017 SAT English-based Reading and Writing score for each State.|
|**sat17_math**|*integer*|sat_2017|Average 2017 SAT Math score for each State.|
|**sat17_total**|*integer*|sat_2017|Average 2017 SAT total score for both subjects for each State.|

#### Data Dictionary for 2018
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|act_2018<br>sat_2018|The states in which the 2018 ACT and SAT participation rates and scores are being recorded for.|
<br>
|**act18_par_percentage**|*float*|act_2018|Average 2018 ACT percentage rate for each State.|
|**act18_english**|*float*|act_2018|Average 2018 ACT English scaled score for each State.|
|**act18_math**|*float*|act_2018|Average 2018 ACT Math scaled score for each State.|
|**act18_reading**|*float*|act_2018|Average 2018 ACT scaled Reading score for each State.|
|**act18_science**|*float*|act_2018|Average 2018 ACT scaled Science score for each State.|
|**act18_composite**|*float*|act_2018|Average 2018 ACT scaled Composite score, which is the average of all individual subject score for each State.|
<br>
|**sat18_par_percentage**|*float*|sat_2018|Average 2018 SAT percentage rate for each State.|
|**sat18_erw**|*integer*|sat_2018|Average 2018 SAT English-based Reading and Writing score for each State.|
|**sat18_math**|*integer*|sat_2018|Average 2018 SAT Math score for each State.|
|**sat18_total**|*integer*|sat_2018|Average 2018 SAT total score for both subjects for each State.|

## Conclusions and Recommendations
We are unable to use the ACT and SAT scores for proper comparison as they follow a different scoring system which explains why the ACT and SAT scores have a negative correlation. The ACT follows a scaled scoring system with a small range of 1-36, whereas the SAT follows a wider ranged scaled scoring system of 200-800 per section which would total to 400-1600 as a total score for the exam. This may give the illusion to the public that it is easier to score better for ACT as the scores do not vary as much, especially when you see the statistical information. For example, as seen above, the composite score for the ACT in 2017 has a mean of 21.5, standard deviation of 2, minimum score fo 17.8 and maximum score of 25.5, whereas, the SAT total score in 2017 has a mean of 1126, standard deviation of 92, a minimum score of 950 and maximum score of 1295. With such numbers, it may seem that the risk of scoring lower in SAT is higher as it varies from the mean greater than the ACT scores. We may then want to consider changing the SAT scoring system to ensure scores from varying too much.

We have also found out that all the sample data do not follow a normal distribution. It is normal to see the graph skewed to one side for scores as there is always a chance that most of the students will fall in a particular range of scores, depending where that range is, that will be the mode which is also the peak of the distribution. As all the sample data do not follow a normal distribution, a confidence interval testing should be done.

From 2017 to 2018, we have seen a slight increase in participation rates for SAT, although statistically students are showing more preference to the ACT exam still. After the introduction of the new SAT format in 2016, there is definitely an increase in participation rate of the SAT exam, this may be the reason why the state of Colorado and Illinois showed a change from an extremely high ACT and low SAT participation rate to the opposite, with a low ACT and high SAT participation rate. We should then consider if revising the SAT format to maybe include a science section which is lacking in the SAT in comparison to the ACT. We could also revise the number of sections in the SAT by splitting them up into more sections, which will lessen the importance of each section on the total score. This may be one of the reason why students would choose the ACT, because if a section was done badly, it would pull down the total score of the SAT more than it would for the ACT.

From my findings, we can see that when the state made the SAT exam free and a mandatory requirement, the participation rate was extremely high. However, states where both ACT or SAT is acceptable but the state does not provide either of them to be taken for free, the participation rate is high for ACT and not for SAT. From this, we can say that students in most states would prefer taking the ACT rather than the SAT, and this may also be the case because as of now, there are more states providing the ACT exam for free rather than the SAT, which may be the reason why the ACT participation rates are still higher than SAT.

As we have seen a trend whereby states with high ACT participation would usually have a low SAT participation, this is because both exams are acceptable my almost all Colleges/Universities. Therefore the deciding or we can say the sway factor to either exam could be due to both the exam format and the states policies and requirements in regards to the exams. If we look at Nebraska, which has and increasing trend in ACT participation rate from 84% in 2017 to 100% in 2018, whereas the SAT participation rate was stagnant at 3%. Nebraska does not have any mandatory requirements for either exams and does not provide any of the exams for free to students.

We may want to consider revising the exam format so that it may appeal to students who prefer the ACT to SAT now. For example instead of only 2 sections, to split these sections into more sections to reduce the importance of each section score on its total score, this may help to increase nation wide participation rate. However, from my findings, state policies and requirements on standardized tests. To dramatically shift the particiapation rates in favor of SAT, we need to look into specific states policies on standardized tests. In this case, looking into Nebraska, we may want to discuss with and convince the state of Nebraska to make the SAT exam compulsory for all junior students or provide the exam for free or both.

## Sources

Author’s name, ***Western Interstate
Commission for Higher Education***. Title of Document, ***Average ACT Scores by State
 Graduating Class 2017***. Title of Website, ***ACT***. Sponsor of Website, ***Knocking at the College Door - Projections of High
School Graduates***. Date of Document, ***December 2016***. Date of Access, ***November 3, 2020***. URL, https://www.act.org/content/dam/act/unsecured/documents/cccr2017/ACT_2017-Average_Scores_by_State.pdf

Author’s name, ***Prep Zone Academy***. Title of Document, ***SHOULD I TAKE THE SAT OR ACT?***. Title of Website, ***Prep Zone Academy|SAT***. Sponsor of Website, ***Prep Zone Academy***. Date of Document, ***Year 2020***. Date of Access, ***November 3, 2020***. URL, https://sat.edu.sg/sat-vs-act/?utm_source=google&utm_medium=cpc&utm_campaign=SAT-generic&utm_keyword=sat%20and%20act&matchtype=p&device=c&adposition=&adgroupid=107972716251&gclid=EAIaIQobChMIs765vq7t7AIVgWkqCh1w6Qx3EAAYASAAEgIY0_D_BwE

Author’s name, ***Halle Edwards***. Title of Document, ***SAT / ACT Prep Online Guides and Tips
How Is the SAT Scored? Scoring Charts***. Title of Website, ***PrepScholar New SAT***. Sponsor of Website, ***SAT College board***. Date of Document, ***January 2, 2020***. Date of Access, ***November 3, 2020***. URL, https://blog.prepscholar.com/how-is-the-sat-scored-scoring-charts

Author’s name, ***Hannah Muniz***. Title of Document, ***SACT vs SAT: 11 Key Differences to Help You Pick the Right Test***. Title of Website, ***PrepScholar New SAT***. Sponsor of Website, ***PrepScholar***. Date of Document, ***August 16 2020***. Date of Access, November 7, 2020. URL, https://blog.prepscholar.com/act-vs-sat

Author’s name, ***Allison Wignall***. Title of Document, ***Preference of the ACT or SAT by State (Infographic)***. Title of Website, ***College Raptor***. Sponsor of Website, ***NCES, ACT, College Board***. Date of Document, ***August 19 2020***. Date of Access, November 7, 2020. URL, https://www.collegeraptor.com/getting-in/articles/act-sat/preference-act-sat-state-infographic/

Author’s name, ***Alex Heimbach***. Title of Document, ***SAT / ACT Prep Online Guides and Tips
Which States Require the SAT? Complete List***. Title of Website, ***PrepScholar New SAT***. Sponsor of Website, ***PrepScholar***. Date of Document, ***October 11 2020***. Date of Access, November 7, 2020. URL, https://blog.prepscholar.com/which-states-require-the-sat

Author’s name, ***Alex Heimbach***. Title of Document, ***SAT / ACT Prep Online Guides and Tips
Which States Require the ACT? Full List and Advice***. Title of Website, ***PrepScholar New SAT***. Sponsor of Website, ***PrepScholar***. Date of Document, ***August 3 2020***. Date of Access, November 7, 2020. URL, https://blog.prepscholar.com/which-states-require-the-act-full-list-and-advice

Author’s name, ***RACHEL KAPELKE-DALE***. Title of Document, ***States that Require the ACT or SAT***. Title of Website, ***Magoosh***. Sponsor of Website, ***EducationWeek***. Date of Document, ***October 24 2018***. Date of Access, November 7, 2020. URL, https://magoosh.com/hs/act/2017/states-that-require-the-act-or-sat/

Author’s name, ***College Raptor Staff***. Title of Document, ***States That Provide A Free ACT/ SAT Test***. Title of Website, ***College Raptor***. Sponsor of Website, ***College Raptor***. Date of Document, ***October 22 2020***. Date of Access, November 7, 2020. URL, https://www.collegeraptor.com/getting-in/articles/act-sat/states-act-sat-given-free/
