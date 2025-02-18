# SQL_Student_Mental_Health

Introduction
--
Studying in a foreign country is simultaneously thrilling and demanding. What factors, precisely, are responsible for the appeal of this project? To find the main aspects that influence the mental health of international students, I will examine the data provided by a Japanese university. Through data manipulation, I plan to see the patterns and trends that point to the most influential factors in students' mental health. By looking at the factors like academic pressure, social integration, financial stress, and cultural adjustment, I believe that insights into what exactly affects their mental health will be gained. Let's take a deep look into the data, and try to find some answers!
![Image](https://github.com/user-attachments/assets/3915a9ae-89fe-42b3-9a1b-2b986ab2bc5a)

Overview
--
Studying abroad is both exciting and challenging, but what exactly contributes to this experience? To uncover the key factors affecting international students' mental health, I’ll be analyzing data from a study conducted by a Japanese international university. Using data manipulation techniques, I aim to identify patterns and trends that reveal the greatest influences on students' well-being. By exploring variables such as academic pressure, social integration, financial stress, and cultural adjustment, I hope to gain insights into what plays the most significant role in shaping their mental health. Let’s dive into the data and find some answers!

In our analysis, we are focusing on mental health, so let’s start by examining how severe the situation is for students across Japan. Using key metrics such as depression levels (PHQ-9 test), social connectedness (SCS test), and acculturative stress (ASISS test), we can gain a clearer picture of the overall well-being of students.

By analyzing depression scores (todep), we can assess how widespread mental health struggles are. Social connectedness scores (tosc) will help us understand whether students feel isolated or supported, while acculturative stress scores (toas) will shed light on the difficulties international students face when adapting to a new culture.

First Insights into Mental Health Challenges Among Students in Japan
--
     SELECT 
         count(inter_dom) as students,
	       round(avg(todep)::numeric,1)
     FROM students
     WHERE inter_dom is not NULL
![Image](https://github.com/user-attachments/assets/fe56c30f-0eb9-41f3-9b02-76fcaec08b2a)

More than half of students are actually experiencing mild or moderate depression, which in turn is alarmingly high. The PHQ-9 score scale version has a 27-point maximum score and the average score of 8.2 indicates mild depression on average, but it also implies a substantial proportion of students are likely to be in the moderate to severe category.

A trend such as this implies that mental health issues are not just due to individual cases but are rather a common frequented problem effecting not only a group but also a bigger weight of the students. Further investigation is necessary to figure out the distribution of each severity category and the features that might explain the high depression rates.














     
