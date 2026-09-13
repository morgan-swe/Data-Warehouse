# Data Standardization

Map coded values into meaningful, user-friendly descriptions. 

Using data standardization we can make previous values and entries easier to read.

## Observations

### Standardization

A lot of the initial data can be transformed to become easier to interpret by using the following methods:

CASE 
    WHEN (column) = 'S' THEN 'Single'
    WHEN (column) = 'M' THEN 'Married'
    ELSE 'n/a'
END AS (column),

Here we are making the column value strings 'S' and 'M' easier to read by transforming them to 'Single' and 'Married' as well as empty values to be 'n/a'.