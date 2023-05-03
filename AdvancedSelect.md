### [Type of Triangle](https://www.hackerrank.com/challenges/what-type-of-triangle/problem)
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

- Equilateral: It's a triangle with  sides of equal length.                 
- Isosceles: It's a triangle with  sides of equal length.                         
- Scalene: It's a triangle with  sides of differing lengths.                             
- Not A Triangle: The given values of A, B, and C don't form a triangle.                       

**Input Format**                   
The TRIANGLES table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235743862-961af14c-479f-4ebd-9bd8-aabdfd26d812.png)


Each row in the table denotes the lengths of each of a triangle's three sides.

***Solution:***
```MySQL
SELECT CASE
WHEN A+B<=C OR B+C<=A OR A+C<=B THEN "Not A Triangle"
WHEN A=B AND B=C THEN "Equilateral"
WHEN A=B OR B=C OR A=C THEN "Isosceles"
ELSE "Scalene"
END
FROM TRIANGLES;
```

### [The PADS](https://www.hackerrank.com/challenges/the-pads/problem)
Generate the following two result sets:
1. Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
2. Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:              
``` There are a total of [occupation_count] [occupation]s. ```                                          
where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.

Note: There will be at least two entries in the table for each type of occupation.

Input Format                                    
The OCCUPATIONS table is described as follows:                                                                
![image](https://user-images.githubusercontent.com/104347305/235817923-ad6a87b3-d70c-4194-8beb-8ffb6bffd7b9.png)                                            
Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor. 

Sample Output
```
Ashely(P)
Christeen(P)
Jane(A)
Jenny(D)
Julia(A)
Ketty(P)
Maria(A)
Meera(S)
Priya(S)
Samantha(D)
There are a total of 2 doctors.
There are a total of 2 singers.
There are a total of 3 actors.
There are a total of 3 professors.
```

***Solution:***
```MySQL
SELECT (NAME|| '('|| SUBSTR(OCCUPATION,1,1) || ')' ) FROM OCCUPATIONS ORDER BY NAME;
SELECT ('There are a total of '|| COUNT(OCCUPATION)||' '|| LOWER(OCCUPATION)||'s.') FROM OCCUPATIONS GROUP BY OCCUPATIONS ORDER BY COUNT(OCCUPATION), OCCUPATION ASC;
```                               

### [Occupations](https://www.hackerrank.com/challenges/occupations/problem)
Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

Note: Print NULL when there are no more names corresponding to an occupation.

**Input Format**

The OCCUPATIONS table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235819352-a79f3fbe-2c03-47d2-99fb-66d5563169d0.png)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

Sample Input

![image](https://user-images.githubusercontent.com/104347305/235819366-bc163405-7f92-4230-bdb5-fbdf6c94e719.png)


Sample Output

``` 
Jenny    Ashley     Meera  Jane
Samantha Christeen  Priya  Julia
NULL     Ketty      NULL   Maria
```           
**Explanation**

The first column is an alphabetically ordered list of Doctor names.
The second column is an alphabetically ordered list of Professor names.
The third column is an alphabetically ordered list of Singer names.
The fourth column is an alphabetically ordered list of Actor names.
The empty cell data for columns with less than the maximum number of names per occupation (in this case, the Professor and Actor columns) are filled with **NULL** values.

***Solution***
```MySQL

```


