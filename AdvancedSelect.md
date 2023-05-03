### [Type of Triangle](https://www.hackerrank.com/challenges/what-type-of-triangle/problem)
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with  sides of equal length.
Isosceles: It's a triangle with  sides of equal length.
Scalene: It's a triangle with  sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

Input Format

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
```

