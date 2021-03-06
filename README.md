# School_District_Analysis
Using Python and Pandas

## Overview 
 
The purpose of this project is to display information within a School District.  Due to academic dishonesty, however, I have replaced the math and reading scores for 9th grade at Thomas High School with NaNs, but keeping the rest of the data intact. After this data was cleaned, I performed an analysis of the school district to provide insights into the following:

1. Overview of district summary statistic
2. Overview of student statistics by school
3. High and low performing schools and their stats
4. Math and reading scores by grades
5. Score results by school spening
6. Score results by size
7. Score results by school type

## Results

I started with cleaning the data and replacing all 9th grade Thomas High School scores with "NaNs" so their names would be included in the analysis, but their score would not.  I did this by creating a series of all 9th grade Thomas High Students, and looping through the series to replace all the scores with "NaNs".  After confirming the all 9th grade Thomas scores were "NaNs", I proceded with the analysis. 

1. The first analysis I put together was the district overview.  The district overview shows the count of different schools, the total number of student across all districts, the average math and reading score across all students, the percentage of students passing reading, the percentage passing math, and the percentage passing both.  I had to made an altercation to the student count, by subtracting the total 9th grade Thomas Students by the previous student count.  Below is the output:

<img width="948" alt="District_Summary_After" src="https://user-images.githubusercontent.com/63257696/118317498-21e34980-b4c6-11eb-9294-8a5fcb3ad005.png">
 <br /> 
 This varies slightly from the first output that includes the Thomas 9th grade scores.  After exluding those scores, the value in each category (assides from the average reading scores) drops by .01 to .03.
 

2. The second analysis is the summary by school, which indexes the data by school to comparee statitics across school type, total students, total budget, per student budget,  the average scores, and the percentages of passing.  I had to replace the percentages passing for Thomas High by replacing the previous generated value with only students in 10th-12th grade.  After this, set the location of the percentages with the new values using the loc method.  Below is the output:

<img width="1014" alt="School_Summary_After" src="https://user-images.githubusercontent.com/63257696/118317522-2b6cb180-b4c6-11eb-9a1f-66a4f9f081e9.png">
 <br /> 

 The scores for Thomas High changed after we removed the 9th grade scores.  You can see that again, the values in each category dropped by a few percentage points. 
 
Making the altercation to only showing the percentage passing for 10th-12th grade is important because without this, the percentage passing would have shown much lower percentages due that the total count of students remained the same, the count of students with valid scores is lower.  The percentages would have been in the 60s range if we did not take into account this altercation.


3. From the school summary, I was able to get the top 5 and bottom 5 performing schools, by sorting through data frame.  Despite the changes in Thomas High, the school still remained in the second spot for top performing schools.

4.  I filtered through the school data and set it equal to new variables in order to get the avergae scores for both reading and math by grade.  

5. I put the school data in bins based off the amount of budgeting each school has.  I used the cut function to put the school data in these the "spending bins" and show the average score and percentages passing per each spending bin.  

6. I then put the school data in bins based off number of students each school has.  I used the cut function to put the school data in these the "size bins" and show the average score and percentages passing per each size bin.  

7. The analysis I performed was grouping the school data by the type of school, which shows the student metrics, average grades, and passing percentages by the two school types.  



## Summary

Changing the 9th grade Thomas High score data was a small, but important part of my analysis that changed the results.  Replacing the data was "Nans" changed how the average scores for math and reading were calculated for the district as a whole and for Thomas High.  It also altered how the percentages passing math and reading were calculated.   When working with nulled data, it is import to make the appropraite altercations for mathmatical calculation because the nulled data can affect the way metrics are calcuated.  We saw in the school summary that the passing percentages for Thomas High would have incorrectly been shown as lower perentages if we did not take into account that we were only looking for score data from 10th-12th grade.  The percentage calculation would have been done with the entire school count, including ninth graders.  Because the ninth grade data is invalid, it would not pull into the calculation, therefore providing inaccurate results. 

