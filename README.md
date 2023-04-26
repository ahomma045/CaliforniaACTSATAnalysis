# CaliforniaACTSATAnalysis

---

## Overview & Problem Statement 

The SAT and ACT are important standardized tests used in the college admissions process throughout the United States. In California, the Department of Education and College Board provide 2019 performance data on these tests at various levels, including schools, districts, counties, and the state as a whole.

The aim of this project is to analyze this data to identify the California counties with the lowest performance on the SAT and ACT exams, and to determine which subject areas require the most attention to improve student performance. Additionally, we will incorporate external data from the US Census to consider the income levels of each county.

Through this analysis, we hope to provide recommendations to the state government on how to allocate additional resources to these low-performing counties, with the goal of improving academic performance and providing students with the necessary tools to succeed. Ultimately, our project aims to make a positive impact on the academic outcomes of students in California.

---

## Data
This project uses two datasets, act_2019_ca and sat_2019_ca. They are available in CSV format. 
* [`act_2019_ca.csv`](data/act_2019_ca.csv): 2019 ACT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://web.archive.org/web/20210831222336/https://www.cde.ca.gov/ds/sp/ai/reclayoutact19.asp))

* [`sat_2019_ca.csv`](data/sat_2019_ca.csv): 2019 SAT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://web.archive.org/web/20210831212915/https://www.cde.ca.gov/ds/sp/ai/reclayoutsat19.asp))

Also, median income data was collected from US Census 
* [`median_income_2019_ca.csv`](data/median_income_2019_ca.csv): US Census, American Community Survey, S1903: Median Income in the past 12 months (in 2019 inflation-adjusted dollars ([source](https://data.census.gov/table?t=Income+(Households,+Families,+Individuals)&g=040XX00US06$0500000&y=2019&tid=ACSST1Y2019.S1903&moe=false))

--- 

## Executive Summary 
The research process for each dataset (SAT/ ACT/ US Census) involved importing and cleaning the data, followed by exploratory data analysis. 

For the SAT dataset, we handled missing values, removed special characters and outliers, fixed incorrect data types, renamed columns, and dropped unnecessary columns. We created a geographical chart to show county coverage, identified counties with the highest and lowest mean test scores, and displayed the ten lowest performing counties on the SAT exam in 2019. We also created scatter charts to show the correlation between the percentage of students meeting the benchmark and two subjects, and grouped bar charts to compare average test scores by subject between the state of California and the 10 low performing counties. Our findings showed that improving math scores would be particularly beneficial for increasing the percentage of students exceeding the benchmark.

Similarly, for the ACT dataset, we imported and cleaned the data, identified the counties with the highest and lowest mean test scores, and created bar charts to display the 10 counties with the lowest percentage of test-takers achieving an ACT composite score of 21 or higher. We also created scatter charts to show the correlation between four subjects and the percentage of students achieving ACT scores of 21 or higher, and grouped bar charts to compare average test scores by subject between the state of California and the 10 low performing counties. Our findings showed that improving scores in English and math would be particularly beneficial for these counties.

Finally, we imported US Census data on median household income in California counties for 2019, and cleaned the data by removing irrelevant columns and simplifying column names. We created a geographical chart to show county coverage, and a bar chart to display counties with low household median income in 2019, which included Lake, Fresno, and Tulare counties among the 10 low performing counties in the ACT and SAT exams. We also created a heatmap to examine the correlation between exam performance and income levels, which showed some correlation between exam scores and household median income, with correlation coefficients ranging from 0.29 to 0.35.

Here is a link to [a geographical chart in Tableau](https://public.tableau.com/views/CaliforniaACTSATAnalysis/D_California_SAT_Scores_Coverage?:language=en-US&:display_count=n&:origin=viz_share_link).

---

## Conclusion & Recommendations

Based on our analysis, we recommend that the state government prioritize additional teaching resources and exam preparation resources to the ten counties with the lowest SAT and ACT exam scores in 2019, particularly Colusa, Glenn, Merced, Madera, Los Angeles, Fresno, Tulare, San Bernardino, Lake, and Monterey.
We suggest that the state government focus on improving Math scores in these counties, as this section has the strongest correlation with overall SAT score performance. Additionally, we recommend improving scores in English and Math for the ACT exam. Providing additional exam preparation resources could be beneficial, especially in counties with a high number of schools such as Monterey, Tulare, and Fresno.
It is worth noting that while income level is not the largest factor in exam performance, there appears to be some correlation between exam performance and income levels in California. Therefore, we recommend targeting resources to the counties with particularly low median household incomes, such as Lake, Fresno, and Tulare.
By implementing these recommendations, we believe that the state government can help improve the academic performance of students in these low-performing counties and provide them with the necessary resources to succeed academically.

---

## Data Dictionary


|Feature|Type|Dataset|Description|
|-------|----|-------|-----------|
|school|object|ACT|School Name|
|district|object|ACT|District Name|
|county|object|ACT|County Name|
|num_of_testtakers|float|ACT|Number of Test Takers|
|avg_score_reading|float|ACT|Average ACT Reading Score|
|avg_score_english|float|ACT|Average ACT English Score|
|avg_score_math|float|ACT|Average ACT Math Score|
|avg_score_science|float|ACT|Average ACT Science Score|
|num_testtakers_compositescr_21_and_up|float|ACT|Number of Test Takers Whose ACT Composite Scores Are Greater or Equal to 21|
|pct_testtakers_compositescr_21_and_up|float|ACT|Percent of Test Takers Whose ACT Composite Scores Are Greater or Equal to 21|
|school|object|SAT|School Name|
|district|object|SAT|District/LEA Name|
|county|object|SAT|County Name|
|num_of_testtakers|float|SAT|Number of Test Takers Grade 12|
|num_benchmark_reading_writing|float|SAT|The number meeting the Evidence-Based Reading & Writing (ERW) benchmark established by the College Board based on the New 2016 SAT test format as of March 2016 for Grade 12|
|pct_benchmark_reading_writing|float|SAT|The percent of students who met or exceeded the benchmark for Evidence-Based Reading & Writing (ERW) test for Grade 12|
|num_benchmark_math|float|SAT|The number of students who met or exceeded the benchmark for the New SAT Math test format as of March 2016 for Grade 12|
|pct_benchmark_math|float|SAT|The percent of students who met or exceeded the benchmark for SAT Math test for Grade 12|
|num_benchmark_both|float|SAT|The total number of students who met the benchmark of both Evidence-Based Reading & Writing (ERW) and Math Grade 12|
|pct_benchmark_both|float|SAT|The percent of students who met the benchmark of both Evidence-Based Reading & Writing (ERW) and Math Grade 12|
|county|object|US Census|County Name|
|household_median_income_2019|int64|US Census|Household Median Income by California County (2019)|