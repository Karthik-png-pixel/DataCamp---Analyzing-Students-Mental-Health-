# Analyzing Students Mental Health

## Goal
Using SQL skills such as aggregating, filtering, grouping, and sorting, I drew insights into whether the data supported the claim that the longer students spent studying abroad, the more it would negatively affect their overall stress compared to domestic students. This was analyzed through performance on core mental health diagnostic exams.

## SQL Query
```sql
SELECT stay,
       COUNT(*) AS count_int,
       ROUND(AVG(todep), 2) AS average_phq,
       ROUND(AVG(tosc), 2) AS average_scs,
       ROUND(AVG(toas), 2) AS average_as
FROM public.students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```

## Results

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

## Analysis
The query groups international students by length of stay abroad and calculates their average scores across three mental health diagnostic tests. Students who stayed 8-10 years showed higher average PHQ scores (a measure of depression) compared to those in shorter stay categories. Notably, the 8 and 10-year groups had very small sample sizes (1 student each), so a natural next step would be expanding the dataset to draw more reliable conclusions.
