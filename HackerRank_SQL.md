# Task 1
Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/7ccb33c7-a6a4-41cb-8f98-8dc01c92471f)

## Solution
SELECT * FROM city WHERE population > 100000 AND countrycode = 'USA''''

