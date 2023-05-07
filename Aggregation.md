### [Average Population](https://www.hackerrank.com/challenges/average-population/problem)
Query the average population for all cities in CITY, rounded down to the nearest integer.

**Input Format**

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235843758-526699f1-d973-464a-a3f4-76044ed85c41.png)

**Solution:**
```MySQL
SELECT AVG(population) FROM CITY;
```

### [Japan Population](https://www.hackerrank.com/challenges/japan-population/problem)
Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

**Input Format**

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235844209-ba4f4cef-40d0-445c-bfea-315d8cd439cb.png)

**Solution:**
```MySQL
SELECT SUM(population) FROM CITY WHERE COUNTRYCODE='JPN';
```

### [Population Density Difference](https://www.hackerrank.com/challenges/population-density-difference/problem)

Query the difference between the maximum and minimum populations in CITY.

**Input Format**

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235844936-6db853d5-858d-44cb-9794-c7869c5b04b3.png)

**Solution:**
```MySQL
SELECT (MAX(POPULATION)-MIN(POPULATION)) FROM CITY;
```

### [The Blunder](www.hackerrank.com/challenges/the-blunder/problem)
amantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.

Write a query calculating the amount of error (i.e.:  average monthly salaries), and round it up to the next integer.

**Input Format**

The EMPLOYEES table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235845469-c419777b-7dbb-45ee-b90d-2b67401e72d8.png)

Note: Salary is per month.

**Constraints**
```  1000 < Salary <10⁵  ```

**Solution:**
```MySQL
SELECT CEIL(AVG(SALARY)-AVG(REPLACE(SALARY,'0',''))+1) FROM EMPLOYEES;
```

### [Revising Aggregations- The Count Function](www.hackerrank.com/challenges/revising-aggregations-the-count-function/problem)
Query a count of the number of cities in CITY having a Population larger than 100,000.

**Input Format**

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235898195-5d748aa6-73d7-49e8-8796-bbd0f4a86c5c.png)

**Solution:**
```MySQL
SELECT COUNT(NAME) FROM CITY WHERE POPULATION>100000;
```

### [Revising Aggregations- The Sum Function](www.hackerrank.com/challenges/revising-aggregations-the-sum-function/problem)
Query the total population of all cities in CITY where District is California.

**Input Format**

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235898921-91705a94-c2af-4b1b-b101-b35f0cec6236.png)

**Solution:**
```MySQL
SELECT SUM(POPULATION) FROM CITY WHERE DISTRICT='California';
```

### [Revising Aggregations- The Average Function](www.hackerrank.com/challenges/revising-aggregations-the-average-function/problem)
Query the average population of all cities in CITY where District is California.

**Input Format**

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235899277-dad1caa2-e30b-447f-86ce-f3b33475d04d.png)

**Solution:**
```MySQL
SELECT AVG(POPULATION) FROM CITY WHERE DISTRICT='California';
```

### [Top Earners](www.hackerrank.com/challenges/earnings-of-employees/problem)
We define an employee's total earnings to be their monthly *salary*x*months* worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.

**Input Format**

The Employee table containing employee data for a company is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235899867-da197edf-71e8-4ecc-9117-6c27f0e1599b.png)

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

**Solution:**
```MySQL
SELECT MAX(salary*months), COUNT(*) FROM EMPLOYEE WHERE (salary*months)>=(SELECT(MAX(months*salary)) FROM EMPLOYEE);
```

### [Weather Observation Station 2](www.hackerrank.com/challenges/weather-observation-station-2/problem)
Query the following two values from the STATION table:

The sum of all values in LAT_N rounded to a scale of  decimal places.
The sum of all values in LONG_W rounded to a scale of  decimal places.

**Input Format**

The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235901946-e81168db-22a9-42e3-84a4-d72338ef141f.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Output Format**

Your results must be in the form:
``` lat lon ```

where *lat* is the sum of all values in LAT_N and *lon* is the sum of all values in LONG_W. Both results must be rounded to a scale of  decimal places.

**Solution:**
```MySQL
SELECT ROUND(SUM(LAT_N),2), ROUND(SUM(LONG_W),2) FROM STATION;
```

### [Weather Observation Station-13](www.hackerrank.com/challenges/weather-observation-station-13/problem)
Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345. Truncate your answer to 4 decimal places.

**Input Format**

The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/236663891-d6e78762-baf4-4d7a-a819-cd994e14c07e.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution:**
```MySQL
SELECT ROUND(SUM(LAT_N), 4) FROM STATION WHERE LAT_N>38.7880 AND LAT_N<137.2345;
```

### [Weather Observation Station-14](https://www.hackerrank.com/challenges/weather-observation-station-14/problem)
Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.

**Input Format**

The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/236664132-18dc3e6b-60c9-4405-b94c-dd7648d953b7.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution:**
```MySQL
SELECT ROUND(MAX(LAT_N),4) FROM STATION WHERE LAT_N<137.2345;
```

### [Weather Observation Station-15](www.hackerrank.com/challenges/weather-observation-station-15/problem)
Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345. Round your answer to 4 decimal places.

**Input Format**

The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/236664611-b0fbdccf-3999-4de5-b90d-b587b4180754.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution:**
```MySQL
SELECT ROUND(LONG_W,4) FROM STATION WHERE LAT_N = (SELECT MAX(LAT_N) FROM STATION WHERE LAT_N<137.2345);
```
