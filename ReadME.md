**Exploratory data analysis of student's participation and performance in ACT and SAT Examination**

- The participation percentage and average marks secured by various states in United States at SAT and ACT Examination for year 2017 and   2018 is given to us. <br />
- We have to analyse, <br />
     1. whether SAT or ACT have maximum participation?<br />
     2. Does the participation rates changes with year? If it changes, why it changes?<br />
     3. What are the trend of their scores in subtest and in the composite?<br /> 
     4. Which are the states that shows interesting trends? Why there is difference in trend?<br />
     5. How can we improve our particiation percentage atleast in 1 of the states with lesser participation?<br />

- Steps involved in the project:<br />

   1. Libraries imported.<br />
   2. sat_2017.csv, act_2017.csv are read from csv file with pd.read_csv()<br />
   3. with .info() data type informations of the 2 data frames are obtained.<br />
   4. Cleaning<br />
         a. Planned to convert states into string and numeric data into float.<br />
         b. strip % with .apply(lambda x: x.strip('x'))<br />
         c. converted data types using pd.to_numeric(), .astype(float)<br />
         d. 2 typos in datas are directly changed in the csv file.<br />
         e. .rename(columns={},inplace = True) is used to rename columns<br />
         f. unnecessary rows are dropped with .drop()<br />
    
    
   5. Variables used in the project ACT_SAT_2017_2018

      |Feature|Type|Dataset|Description|
      |---|---|---|---|
      |states_participating|object|SAT|States participating in SAT 2017 Examination|
      |sat_2017_participation|Float|SAT|percentage of students participating in SAT 2017 Examination|
      |sat_2017_evidence_based_reading_writing|Float|SAT|Marks got by students in SAT 2017 evidence_based_reading_writing|
      |sat_2017_math|Float|SAT|Marks got by students in SAT 2017 Math Examination|
      |sat_2017_total|Float|SAT|Total Marks got by students in SAT 2017 Examination|
      |act_2017_participation|Float|ACT|percentage of students participating in ACT 2017 Examination|
      |act_2017_english|Float|ACT|Marks got by students in ACT 2017 english|
      |act_2017_math|Float|ACT|Marks got by students in ACT 2017 Math Examination|
      |act_2017_science|Float|ACT|Total Marks got by students in SAT 2017 Examination|
      |act_2017_reading|Float|ACT|Marks got by students in ACT 2017 reading|
      |act_2017_composite|Float|ACT|Average Marks of all subjects got by students in ACT 2017 Examination|
      |sat_2018_participation|Float|SAT|percentage of students participating in SAT 2018 Examination|
      |sat_2018_evidence_based_reading_writing|Float|SAT|Marks got by students in SAT 2018 evidence_based_reading_writing|
      |sat_2018_math|Float|SAT|Marks got by students in SAT 2018 Math Examination|
      |sat_2017_total|Float|SAT|Total Marks got by students in SAT 2018 Examination|
      |act_2018_participation|Float|ACT|percentage of students participating in ACT 2018 Examination|
      |act_2018_english|Float|ACT|Marks got by students in ACT 2018 english|
      |act_2018_math|Float|ACT|Marks got by students in ACT 2018 Math Examination|
      |act_2018_science|Float|ACT|Total Marks got by students in SAT 2018 Examination|
      |act_2018_reading|Float|ACT|Marks got by students in ACT 2018 reading|
      |act_2018_composite|Float|ACT|Average Marks of all subjects got by students in ACT 2018 Examination|

 
   6. Then datas are merged with pd.merge()<br />
   7. Repeated the steps for ACT, SAT 2018 and merged all files together.<br />
   8. describe() is used to obtain the statistical information.<br />
   9. got the states participated lesser and most and the max and min marks based on states with masking, filtering and .sort_values() <br />                   a. North dakota, Mississippi, lowa are the states with least participation in 'sat_2017_participation' Connecticut,Delaware,   District of Columbia and Michigan are the states with maximum participation in 'sat_2017_participation'<br />
               b. Maine is the states with least participation in 'act_2017_participation'<br />
               c. South Carolina, Utah, Tennessee, Alabama, Missouri, North Carolina, Nevada, Montana, Wisconsin, Mississippi, Minnesota,Louisiana,Kentucky, Colorado, Arkansas, Oklahoma and Wyoming have the maximum participation rate for act_2017_participation.<br />
               d. Colorado, Connecticut, Delaware, Michigan, Idaho has the highest participation rates for 2018 SAT North Dakota has least participation rate for SAT 2018.<br />
               e. Maine is the states with least participation in 'act_2018_participation'<br />
               f. Wyoming,Oklahoma,Arkansas,Kentucky,Louisiana,Mississippi,Wisconsin,Montana,Nevada,Nebraska,North Carolina,Ohio,Missouri, Alabama,Tennessee,Utah,South Carolina has the maximum participation in ACT 2018 Examination.<br />
               g. District of Columbia has least mean total/composite scores for the SAT 2017 <br />
               h. Minnesota has highest mean total/composite scores for the SAT 2017 <br />
               i. Nevada has the lowest mean total/composite scores for the ACT 2017 <br />
               j. Connecticut has the highest mean total/composite scores for the ACT 2017 <br />
               k. West Virginia has the highest mean total/composite scores for the SAT 2018 <br />
               l. Minnesota has highest mean total/composite scores for the SAT 2018 <br />
               m. Nevada has the lowest mean total/composite scores for the ACT 2018 <br />
               n. Connecticut has the highest mean total/composite scores for the ACT 2018 <br />
               o. Colarado with 11% participation in SAT 2017 has increased tremendously to 100% in SAT 2018. Also, Colarado with 100% participation in ACT 2017 has reduced tremendously to 30% in ACT 2018. Ohio participation has increased from 75% in ACT 2017 to 100% in ACT 2018. <br />
               p. Florida, Georgia and Hawaii have the participation of more than 50% on both tests either year <br />
          
   10. SNS heat map is plotted to find relationship among various variables.Based on heatmap, SAT and ACT Participation have negative     correlation. <br />
          **Observation** : <br />
                        SAT 2017 and SAT 2018, ACT 2017 and ACT 2018 have a positive correlation.
         
   11. Histogram is plotted to find Participation rates for SAT & ACT, Math scores for SAT & ACT,Reading/verbal scores for SAT & ACT<br />
          **Observation** :<br />
                        a. ACT has more states with 100% participation while SAT have more states with lesser participation.<br /> 
                        b. MATH marks was higher for SAT in 2017 compared to 2018.<br />
                        c. Students score higher marks by states in SAT reading compared to ACT reading examination.<br />
         
   12. Scatter plot is plotted for SAT vs. ACT math scores for 2017, SAT vs. ACT verbal/reading scores for 2017, SAT vs. ACT                       total/composite scores for 2017, Total scores for SAT 2017 vs. 2018, Composite scores for ACT 2017 vs. 2018<br />
            **Observation** : <br />
                          a. SAT math scores for 2017 is comparitively higher than act math scores in 2017.<br />
                          b. This reading and writing marks have a approximate negative linear relationship between act 2017 and sat 2017                                scores. SAT reading and writing are generally higher than ACT english marks.<br />
                          c. Total scores for SAT 2017 vs. 2018 have positive linear relationship with few outliers.<br />
                          d. composite scores for ACT 2017 vs. 2018 have positive linear relationship with few outliers.<br />
                          
   13. box plox is plotted to get the statistical data.<br />
            **Observation**:<br /> 
                          a. ACT have more states with 100% participation compared to SAT. SAT 2018 participation is higher than SAT 2017.<br />
                          b. The trend is similar for SAT 2017 and SAT 2018 total.<br />
                          c. The trend is similar for ACT 2017 and SAT 2018 composite.<br />
                          d. The SAT marks are around the same for both subjects and for both years.<br />
                          e. English mark by states have higher standard deviation while maths and science have lower standard deviation.Reading marks are higher than any other subject marks.<br />
         
   14. barh plot for participation versus states are plotted.<br />
             **Observation**: <br />
             Rhode Island, Illinois and colorodo ACT has shown decrease in participation in 2018 while increase in SAT participation in 2018.Ohio participation increased in 2018. Generally based on this chart we could say if SAT participation is more in a particular state then ACT participation is lesser in the state. If ACT participation is higher then SAT is lower in the state.<br />
             **Outside research**: <br />
             Colorado, Illinois and Rhode Island is my states of interest. The increase in SAT 2018 and decrease in ACT 2018 is due to the change in the state policy in 2017. So from 2018 Colorado, Illinois and Rhode Island require SAT examination scores for enrolling in the college. Ohio is another state where they can accept either ACT or SAT scores for college admission. So, the participation raised in 2018 for both ACT and SAT.<br />
             
   15. **Conclusion**:<br />
            Based on the studies, found that the states with maximum participation in one exam participated lesser in the other exam. This is because of their state policies. Certain states accept SAT and certain states accept ACT. While some other states accept both the examination. In 2017 there was a change in state policy, So in 2018 some of the state moved to SATS examination. The marks secured by ACT and SAT have a approximate negative linear relationship. SAT marks are comparatively higher than ACT marks. SAT 2017 and 2018 marks have a linear relationship. ACT 2017 and 2018 marks also have a linear relationship. <br />
   If in a state with least participation like alaska where SAT examination is accepted, then the college board might start campaign and speak about the positives of taking the examination and the exam board can offer some discounts in the examination fee for the students. SAT Examination board can also sign a contract with the college board and ask the colleges to encourage the students to take SAT examination.