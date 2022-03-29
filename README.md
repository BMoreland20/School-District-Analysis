Overview school district analysis:

In this analysis we aimed to explore the math and reading scores of high school students.  During the analysis we broke down the data by grade, school, school size, school budget, and school type.  This work was to determine which schools performed the best and had the best passing performance based on size, budget, and type.

School District Analysis Results:

•	The overall district summary after replacing the Thomas High Schools 9th graders with NaN the effect on the data is not easily seen in the data frame as seen by these images. 
Challenge result: ![This is an image]( https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Challenge_District_Results.png)

Original Result: ![This is an image]( https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Original_District_Results.png)

•	The school summary, however, was indeed affected.  With the removal of the 9th graders from the data set you can see that the overall passing percentage for math and reading drops by roughly three tenths of a percent.  The math reading percentage decreases by almost by two tenths of a percent.  While reading had an almost three tenths of a percent drop as well.  The student count also decreased when we were asked to remove the 9th graders from the data frame causing the budget per student to also increase as well.  This is best shown in the following images:
Challenge result: ![This is an image]( https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Thomas_High_Summary_Challenge.png)
Original Result: ![This is an image]( https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Thomas_High_Summary_Original.png)
•	As mentioned above removing the 9th grader data negatively affects the percentage of passing students in both reading and math, as well as overall passing students.  It does also negatively affect the average grade score for both math and reading.  However, it affects the reading by very little.
•	How were scores affected:
o	The Math and reading scores by grade were only affected in the Thomas section where it shows NaN in its data spot. (See photos)
Math: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Challenge_Math_by_Grade_Results.png)
Reading: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Challenge_Reading_by_Grade_Results.png)
o	Due to the change in number of students that counted towards the total for Thomas High School; Thomas High went from tier 3 `$631-645` to tier 4 `$646-675`.  To clarify their per student spending went from $638 per student to $888.53.  This change caused the `$631-645` range to lose in the average and percentage scores when looking at all the schools combined.  While all of the others remained the same.  (See photos)
Challenge: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Challenge_Spending_Results.png)
Original: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Original_Spending_Results.png)
o	Surprisingly the scores by school size did not change at all.  At least the way that my code pulled all of the data there was no change in the scores after removing the 9th graders from Thomas High.  (See photos)

Challenge: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Challenge_School_Size_Results.png)

Original: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Original_School_Size_Results.png)

o	In a similar conclusion to the scores by school size the results by school type did not change either.  This could be due to the formatting code that I did in earlier steps that causes the small changes i.e. tenths or even thousandths of a percent from being seen in the results data frame.  (See photos)

Challenge: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Challenge_School_Type_Results.png)

Original: ![This is an image](https://github.com/BMoreland20/School-District-Analysis/blob/main/Resources/Original_School_Type_Results.png)

School District Analysis Summary:

We can conclude that there were at least two confirmed changes in the results when examining scores by grade and by spending where the addition of NaNs for the Thomas High School student by using the following lines of code `student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"), 'reading_score'] = np.nan` and `student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"), 'math_score'] = np.nan` affected the overall results when examined.
When considering looking at the school type and school size where we had no detectable change it is highly possible that due to the data frame formatting (see code here for example) `["Average Math Score"].map("{:.1f}".format)` that took place any detectable change would be missed as most of the data had a small variance within tenths or even thousandths of a percent would not be seen as the numbers returned were whole integers and had no decimals.
As noted in my previous two paragraphs the removal of the 9th grade students from one High School was not enough to massively sway the results when looking at school type or school size.  But when naturally when looking at just the school itself it can sway/change the analytical results by nearly half a percentage point, and largely change the spending by student when the 9th graders are removed for missing data.  This however, can be misleading when data is presented as some would have the opinion that Thomas High has the best budget spending per student at $888.53 from the actual or original $638 per student.  Finally one last change that has been mentioned throughout was the total number of students that were counted towards the total for Thomas High school.  Thomas High originally had a total count of 1,635 students but 461 of those were the 9th graders that artifically had their reading and math scores zeroed out.  This caused the overall total to drop to 1,174 students that counted towards the student count for Thomas High School.