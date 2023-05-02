###https://www.hackerrank.com/challenges/what-type-of-triangle/problem
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with  sides of equal length.
Isosceles: It's a triangle with  sides of equal length.
Scalene: It's a triangle with  sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

Input Format

The TRIANGLES table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235743862-961af14c-479f-4ebd-9bd8-aabdfd26d812.png)


Each row in the table denotes the lengths of each of a triangle's three sides.

Solution:
``` MySQL
SELECT CASE
WHEN A+B<=C OR B+C<=A OR A+C<=B THEN "Not A Triangle"
WHEN A=B AND B=C THEN "Equilateral"
WHEN A=B OR B=C OR A=C THEN "Isosceles"
ELSE "Scalene"
END
FROM TRIANGLES; 


