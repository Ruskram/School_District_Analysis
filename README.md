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
THS_10_12 = school_data_complete_df.loc[(school_data_complete_df["grade"] != "9th") & (school_data_complete_df["school_name"] == "Thomas High School"),"Student ID"].count()"
```


* How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?



* How does replacing the ninth-grade scores affect the following:

    * Math and reading scores by grade

      

    * Scores by school spending

      

    * Scores by school size

      

    * Scores by school type      


## Summary


