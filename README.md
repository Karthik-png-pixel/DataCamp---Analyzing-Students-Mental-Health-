# Analyzing-Students-Mental-Health

# Goal: Using SQL skills such as aggregating, filtering, grouping, and sorting, I drew insights into whether the data supported the claim that the longer the students spent studying abroad, it would negatively affect their overall stress as opposed to domestic students. This was analyzed through performance on core mental health diagnostic exams from "students" table.


```Select 
stay,
count(*) AS count_int,
round(avg(todep), 2) as average_phq,
round(avg(tosc), 2) as average_scs,
round(avg(toas), 2) as average_as

FROM public.students

WHERE
inter_dom = 'Inter'

GROUP BY
stay

ORDER BY 
stay DESC;
```

| stay | count_int | average_phq | average_scs | average_as |
|------|-----------|-------------|-------------|------------|
| 10   | 1         | 13.00       | 32.00       | 50.00      |
| 8    | 1         | 10.00       | 44.00       | 65.00      |
| 7    | 1         | 4.00        | 48.00       | 45.00      |
| 6    | 3         | 6.00        | 38.00       | 58.67      |
| 5    | 1         | 0.00        | 34.00       | 91.00      |
| 4    | 14        | 8.57        | 33.93       | 87.71      |
| 3    | 46        | 9.09        | 37.13       | 78.00      |
| 2    | 39        | 8.28        | 37.08       | 77.67      |
| 1    | 95        | 7.48        | 38.11       | 72.80      |


# Analysis: 
# The query output illustrates the full list of international students grouped by the length of their stay abroad represented in years. In the columns to the right are the average exam scores of 3 mental diagnostic exam scores testing for depression levels (listed as average_phq), social connectedness (average_scs), and acculturative stres (average_as).  


# Based on the analysis, it appears that the students who spent 8 and 10 years abroad had higher phq scores on average than students in the 5-7 year category (of the same sample sizes), hinting that length of the stay away from students' homes could be viewed as a factor to creating more isolation and depression.

# Future direction: To really substantiate the study's claim that students who spend more time in other countries experience more mental and psychological distress, we would need a larger representative sample size of the groups that make up the 5-10 year category, as there were enough responses from the 1-4 year grouping to draw a fait comparison to test our theory. 

