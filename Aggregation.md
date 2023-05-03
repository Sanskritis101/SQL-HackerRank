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

### [The Count Function](www.hackerrank.com/challenges/revising-aggregations-the-count-function/problem)
Query a count of the number of cities in CITY having a Population larger than 100,000.

Input Format

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/104347305/235898195-5d748aa6-73d7-49e8-8796-bbd0f4a86c5c.png)

**Solution**
```MySQL
SELECT COUNT(NAME) FROM CITY WHERE POPULATION>100000;
```



