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
SELECT SUM(population) FROM CITY WHERE COUNTRYCODE = "JPN";
```
