# Revising the Select Query I
Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/7ccb33c7-a6a4-41cb-8f98-8dc01c92471f)

## Solution
SELECT * FROM city WHERE population > 100000 AND countrycode = 'USA';

# Revising the Select Query II
Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

## Solution
SELECT name FROM city WHERE countrycode = 'USA' AND population > 120000;

# Query all columns (attributes) for every row in the CITY table.

Query all columns (attributes) for every row in the CITY table.

## Solution
SELECT * FROM city;

# Select By ID
Query all columns for a city in CITY with the ID 1661.

## Solution
SELECT * FROM city WHERE id = "1661";

# Japanese Cities' Attributes
Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

## Solution
SELECT * FROM city WHERE countrycode = 'JPN';

# Japanese Cities' Names
Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

## Solution
SELECT name FROM city WHERE countrycode = "JPN";

# Weather Observation Station 1
Query a list of CITY and STATE from the STATION table.

The STATION table is described as follows:

![1449345840-5f0a551030-Station](https://github.com/user-attachments/assets/c049e934-8f74-4ac4-a6dc-fc668b7c48c3)

## Solution
SELECT city, state FROM station;

# Weather Observation Station 3
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

## Solution
SELECT DISTINCT city FROM station WHERE (ID % 2 = 0);

# Weather Observation Station 4
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

## Solution
SELECT COUNT(city) - COUNT(DISTINCT(city)) FROM station;

# Weather Observation Station 5

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

## Solution
//find shortest city name
SET @MinCityLen = (SELECT MIN(CHAR_LENGTH(city)) FROM STATION);
//find longest city name
SET @MaxCityLen = (SELECT MAX(CHAR_LENGTH(city)) FROM STATION);
SELECT
    city,
    CHAR_LENGTH(city)
FROM
    STATION
WHERE
    //find shortest city name sorted alphabetically
    city = (
        SELECT
            city
        FROM STATION
        WHERE CHAR_LENGTH(city) = @MinCityLen
        ORDER BY city ASC
        LIMIT 1
    )
    //find longest city name sorted alphabetically
    OR city = (
        SELECT
            city
        FROM STATION
        WHERE CHAR_LENGTH(city) = @MaxCityLen
        ORDER BY city ASC
        LIMIT 1
    )




