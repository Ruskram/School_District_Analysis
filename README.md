# School_District_Analysis

# PyCitySchools with Pandas

## Overview of Project

### Purpose

In this project we are helping Maria by doing analysis of all the reading and math tests by all the schools in her district. The analysis was done on the data she gave us from a csv file and was presented to her with a breakdown per school. Later on she found out that there was some academic dishonesty by the 9th grade class of Thomas High School. So she told us because of that we need to exclude all of the grades from the 9th grade of that high school in our analysis.

The purpose of this project is to learn how to manipulte a data set that we have worked with and rerun our analysis. This will provide more accurate data to the school board in the testing performance per school.

## Results

* How is the district summary affected?

By removing the math and reading scores of the 9th grade from Thomas High School in the district summary there was not a very big change in the percentages.

Before removing the 9th grade scores:

![image](https://user-images.githubusercontent.com/92827264/147897288-843c6acb-c245-460c-a1de-0ee24d53b261.png)

After removing the 9th grade scores:

![image](https://user-images.githubusercontent.com/92827264/147897265-46a9fdbb-cc1c-4640-9fac-b65da35b2e26.png)

Overall the district summary was not affected much by removing the 9th grade scores.

* How is the school summary affected?

By removing the math and reading scores of the 9th grade from Thomas High School in the school summary the changes were much more significant.

Before removing the 9th grade scores:

![image](https://user-images.githubusercontent.com/92827264/147897467-ba0d425f-53e1-423d-94e3-bb18ddb5dc70.png)

After removing the 9th grade scores:

![image](https://user-images.githubusercontent.com/92827264/147897570-a93c885f-6d79-49d7-abb5-9c89fe7659a0.png)

There is a huge drop after removing them. However, we found the number of 9th grade students and removed them from the total student counts. This was done to re-run the analysis to get a summary with only 10th-12th graders for Thomas High school. Using the Code below:

```
THS_10_12 = school_data_complete_df.loc[(school_data_complete_df["grade"] != "9th") & (school_data_complete_df["school_name"] == "Thomas High School"),"Student ID"].count()

THS_passing_math = school_data_complete_df.loc[(school_data_complete_df["math_score"] >= 70) & (school_data_complete_df["school_name"] == "Thomas High School"),"Student ID"].count()

THS_passing_reading = school_data_complete_df.loc[(school_data_complete_df["reading_score"] >= 70) & (school_data_complete_df["school_name"] == "Thomas High School"),"Student ID"].count()

THS_reading_math = school_data_complete_df.loc[(school_data_complete_df["reading_score"] >= 70) & (school_data_complete_df["math_score"] >= 70) & (school_data_complete_df["school_name"] == "Thomas High School"),"Student ID"].count()

pass_math_10_12 = THS_passing_math / THS_10_12 * 100

pass_read_10_12 = THS_passing_reading / THS_10_12 * 100

THS_overall_10_12 = THS_reading_math / THS_10_12 * 100

```
Then the averages were replaced with the 10th - 12th grade averages. This gave a much closer result to the original summary.

![image](https://user-images.githubusercontent.com/92827264/147897894-8737c118-1504-4d05-a45d-1ad30b7fe476.png)

* How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?

It doesn't affect it much when you average based on an adjusted total withouth the 9th graders, but when the 9th graders where accounted in the total students it looked very bad for the school.

![image](https://user-images.githubusercontent.com/92827264/147899068-9e4ead1c-47fe-460b-98d6-5ff37d72e2ed.png)

* How does replacing the ninth-grade scores affect the following:

    * Math and reading scores by grade

      Before removing the 9th grade scores:
      
      Math
      ![image](https://user-images.githubusercontent.com/92827264/147898668-8386301a-da09-4561-a383-ee110f9aad1a.png)
      
      Reading      
      ![image](https://user-images.githubusercontent.com/92827264/147898687-37203efb-5e00-4f84-91fd-04e7d75359b6.png)

      After removing the 9th grade scores:
      
      Math
      ![image](https://user-images.githubusercontent.com/92827264/147898719-caaacaee-8c59-49cc-860e-675e0e2d86cd.png)
      
      Reading
      ![image](https://user-images.githubusercontent.com/92827264/147898703-2cc1d9ed-0cd4-4575-af6e-3bf3e9448fe2.png)

    * Scores by school spending

      Before removing the 9th grade scores:
      
      ![image](https://user-images.githubusercontent.com/92827264/147898766-0cbda16f-a0c2-47d0-be28-b3e909d07f0b.png)

      After removing the 9th grade scores:
      
      ![image](https://user-images.githubusercontent.com/92827264/147898804-c581e12b-c1dd-4de2-ba19-c39156c7b225.png)


    * Scores by school size

      Before removing the 9th grade scores:
      
      ![image](https://user-images.githubusercontent.com/92827264/147898811-56450a92-e4cd-450c-80b6-7616c7e2fbe6.png)

      After removing the 9th grade scores:
      
      ![image](https://user-images.githubusercontent.com/92827264/147898821-2ab9aaee-fad5-4f61-afe2-4c1703c47f07.png)

    * Scores by school type      

      Before removing the 9th grade scores:
      
      ![image](https://user-images.githubusercontent.com/92827264/147898838-e21e4c94-3503-4702-9e0c-9bf3fb54e170.png)

      After removing the 9th grade scores:
      
      ![image](https://user-images.githubusercontent.com/92827264/147898852-6b985305-7e13-4fba-9506-888cf3efc52e.png)
      
## Summary

After replacing the math and reading scores for the ninth grade class of Thomas High School there were the following changes. First, change was the % that passed math. This number went from  93.3% to 66.9%. The second change was the % that passed reading. This number went from 97.3% to 69.6%. Third change was the overall passing %. This went from 90.9% to 65.0%. The last change was the new total that had to be used to get better passing percentages for Thomas High School. To correct the changes that were stated before I had to used a new student total without the 9th graders. The total student changed from 1635 to 1174.
