# Student-Performance-Analysis
## Table Of Contents
- [Project overview](#project-overview)
- [Data Sources](#data-sources)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results of Findings](#results-of-findings)
- [Recommendations](#recommendations)
- [Limitations](limitations)

### Project Overview
  This Data Analysis Project aims to provide insights into student performance, demographic factors, and academic trends. By analyzing various aspects of student data, this project seeks to identify patterns, make data-driven recommendations, and gain a deeper understanding of factors influencing student success. This project was of personal interest as I was interested in seeing how factors such as parental educational level and socio-economic status affects a student's performance. I also wanted to recognize the trends in student performance overtime, which would allow for certain decisions to be made or certain policies put in place to improve students' grades and their quality of learning.

[Dashboard](performance.png)

![image](https://github.com/ChrisAnn609/Student-Performance-Analysis/assets/173093556/dfd55e7e-34cf-4bd8-b294-071e2dae50a3)


![image](https://github.com/ChrisAnn609/Student-Performance-Analysis/assets/173093556/34a1245b-2f82-4b80-a3d6-39646dcc06e4)


![image](https://github.com/ChrisAnn609/Student-Performance-Analysis/assets/173093556/c69b977e-1da0-479e-9aeb-fca1bdc60f67)


![image](https://github.com/ChrisAnn609/Student-Performance-Analysis/assets/173093556/8d64cd54-9ab8-4a7a-8c12-805b053cd8f4)

  

### Data Sources
  The Primary Data set used for this analysis is the "Student Performance Analysis.xlsx" file containing detailed information about
  - Student Details
  - Study Performance
  - Attendance Summary
  - Course Averages
  - Daily Attendance
  - Course Details
  - Race Ethnicity
    
#### The tools used were:
  - Excel- Data Entry and Collection
- Power BI- Data Cleaning, transformation and Visualization

### Data Cleaning and Preparation
In the initial data preparation phase, the following tasks were performed:
- Data loading and inspection
- Handling missing and duplicate values
- Data cleaning and formatting

### Exploratory Data Analysis
  Exploratory Data Analysis involved exploring the Student Performance Data Analysis data to answer key questions such as:
-What are the trends in test scores over time and by subject?
- Which students have the highest performance and what are their demographic characteristics?
-Are there correlations between Test preparation course completion, lunch( free/reduced or standard) and test scores?
-Are there correlations between attendance and test scores?
- Are there correlations between Parental level of education and student's academic performance?
    
The visualizations used to answer this question included: Slicers, cards, Line charts, Bar charts, World Map, Scatter Plots and Pie Charts.
 
### Data Analysis
The following metrics were calculated using DAX formulas:
  
1- Total Number of males and females and percentage of each gender
  
2- Total Days Present, absent and late
  
3- Average Scores
  
The formula used to calculate total and percentage of students per Gender is as follows:
```
Total female students = 
CALCULATE(
    COUNTROWS('Study Performance'),
    'Study Performance'[Gender] = "Female"
)

% females = Divide([Total female students],[Total # of students],0)

Total Male students = 
CALCULATE(
    COUNTROWS('Study Performance'),
    'Study Performance'[Gender] = "male"
)

% males = Divide([Total male students],[Total # of students],0)
```

The formula used to calculate the Total Days Present is as follows:

```
Total Days Present = SUM('Attendance Summary'[# of Days Present])
```
The formula used to calculate the Total Days late is as follows:
```
Total Days Late = SUM('Attendance Summary'[# of Days Late])
```

The formula used to calculate the Total Days absent is as follows:
```
Total Days Absent = SUM('Attendance Summary'[# of Days Absent])
```
The formula used to calculate the Total number of students is as follows:
```
Total # of students = COUNTROWS('Student Details')
```
The formula used to calculate Average Scores is:
```
Average scores = 
AVERAGEX(
  'Study Performance',  
  [BI2024 Grade in %] + 
  [CH2024 Grade in %] + 
  [MA2024 Grade in %] + 
  [PH2024 Grade in %] + 
  [RE2024 Grade in %] + 
  [WR2024 Grade in %]
) / 6
```
### Results Of Findings

- Attendance had little to no impact on the performance of the Students. In the case of one of the students- Daniel Garcia; he achieved the highest average in the class, however, was ironically absent for 30 out of the 40 days in the semester.
- There were more Male students than Female students. Majority of the students were from Kingston, Jamaica.
- The overall class average was 62.95% or Grade C.
- Majority of the students were of Indian descent.
- 


### Recommendations
Based on the analysis, the following actions are recommended:
- Try to get the Parents more involved in their Child/children's education- Students tend to achieve higher test scores where parents are greatly involved in the education process, as this encourages children to put more effort into their studies.
- Offer incentives to get students to take a greater interest in their studies: When there are tangible rewards to strive for, students are often more likely to put in the necessary effort and time to ensure they achieve good grades in the different subject areas. This will also improve student-teacher relationship and for collaboration between all parties to ensure effective learning and teaching.
- Offer compulsory remedial classes: Remedial classes offer more personalized attention, allowing educators to tailor instruction to the specific needs of each student, which will allow for any learning issues to be addressed. These classes will also boost the confidence of the students', thus they'll have a more positive attitude towards school and learning in general.
  

### Limitations
  Some records had to be excluded, as the accuracy of the analysis conclusion would have been affected.
