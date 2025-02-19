# SQL Student Mental Health

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

Sorting the students by PHQ-9 depression severity levels will give a clearer picture of how widespread the issue is. With the five PHQ-9 test levels, we can sort the students into percentage ranges:

    SQL CODE 
    SELECT 
    CASE 
        WHEN todep >= 20 THEN 'Severe depression'
        WHEN todep BETWEEN 15 AND 19 THEN 'Moderately severe depression'
        WHEN todep BETWEEN 10 AND 14 THEN 'Moderate depression'
        WHEN todep BETWEEN 5 AND 9 THEN 'Mild depression'
        ELSE 'None or minimal depression'
    END AS "Depression Severity", 
    COUNT(inter_dom) 
    FROM students 
    GROUP BY "Depression Severity";
![Image](https://github.com/user-attachments/assets/f9b2c64d-7482-435a-bbbe-0a4ae5bdf0d1)

The data reveals a disconcerting pattern: while a majority of students fall in the mild and moderate depression categories, a significant percentage also have moderately severe or severe depression, demonstrating pervasive mental illness. Although there are students who report no or minimal depression, the overall pattern of the data suggests that depression is an overarching issue among the surveyed students, necessitating increased support for mental health on campus.

      SQL code 
      SELECT 
      CASE 
        WHEN todep >= 20 THEN 'Severe depression'
        WHEN todep BETWEEN 15 AND 19 THEN 'Moderately severe depression'
        WHEN todep BETWEEN 10 AND 14 THEN 'Moderate depression'
        WHEN todep BETWEEN 5 AND 9 THEN 'Mild depression'
        ELSE 'None or minimal depression'
    END AS "Depression Severity", 
    COUNT(CASE WHEN inter_dom = 'Dom' THEN 1 END) AS "Dom Count",
    COUNT(CASE WHEN inter_dom = 'Inter' THEN 1 END) AS "Inter Count",
    COUNT(CASE WHEN inter_dom NOT IN ('Dom', 'Inter') THEN 1 END) AS "Other Count"
    FROM students 
    GROUP BY 1


![Image](https://github.com/user-attachments/assets/423e375a-d3fc-4d4e-afdc-bbf4a7985ac9)


This chart again confirms that international students are more likely to experience higher rates of depression at every level of severity compared to domestic students. The graph shows that while mild and moderate depression are common among both groups, international students are very slightly over-represented in these categories. Notably, the "None or minimal depression" category consists mainly of an "Unknown" group, representing missing or unclassified data. This trend signifies the potential psychological problems that might confront international students, such as adaptation stress and isolation.

Deep Dive into the Data
---
The high levels of depression among students might be determined by language, race, and socioeconomic status. Language challenges may pose a problem to international students, resulting in loneliness and academic pressures, while domestic students face expectations from society. Cultural and social adjustment problems are also responsible because international students are usually faced with challenges adapting to new environments, which increase their feelings of loneliness and anxiety. In addition, economic pressure also plays a very important role since foreign students tend to have higher tuition fees and limited job opportunities compared to local students, who even have their own economic pressures. Racial and ethnic backgrounds can also influence mental health, with discrimination and lack of representation in schools contributing towards feelings of isolation. Establishing these relationships can help to inform support mechanisms that cater to the diverse needs of students.

Let's first analyze international students, as they lead in severe depression statistics. 

    



//TODO
--










     
