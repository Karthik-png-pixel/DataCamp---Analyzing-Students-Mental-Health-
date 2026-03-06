# Analyzing-Students-Mental-Health

# Goal: Using SQL skills such as aggregating, filtering, grouping, and sorting, I drew insights into whether the data supported that the longer students spent studying abroad if that negatively affected their their overall stress less as opposed to domestic students. This was analyzed through performance on core mental health diagnostic exams.


Select 
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
