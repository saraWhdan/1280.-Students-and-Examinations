# 1280.-Students-and-Examinations
Problem Link:https://leetcode.com/problems/employee-bonus/description/?envType=study-plan-v2&envId=top-sql-50

## Solution

```sql

SELECT 
  s.student_id
  ,s.student_name
  ,b.subject_name
  ,ISNULL(count(e.subject_name),0) attended_exams
FROM
  Students s CROSS JOIN subjects b 
  LEFT JOIN Examinations e ON s.student_id=e.student_id
  AND b.subject_name = e.subject_name
GROUP BY 
  s.student_id
  ,s.student_name
  ,b.subject_name
ORDER BY 
   s.student_id
  ,s.student_name
