# Develop SQL Load Scripts

We can use bulk inserts to load the data from the source to the data warehouse. Bulk inserts is a method to load massive amounts of data very quickly from files directly into a database.

## Observations

### First row

Usually files first rows with start with a header column. That is why when we bulk insert this data we want to make the first row 2, or wherever the header columns are.
Example code: FIRSTROW = 2

### File Delimiters

We have to be careful about the file delimiter, different files can use different types. So we need to understand how the files are split.
File delimiters: , ; | # "

### Tablock

We want to lock the entire table while we are loading it.

### Quality check

After loading in the data into the tables we want to check if we have the correct data inside the correct columns. 

We can do a quality check by using the following methods:

SELECT * FROM (schema_name).(filename)
Using the SELECT method we can check if any of the values inside the columns are missing or wrong.

SELECT COUNT(*) FROM (schema_name).(filename)
Using the COUNT method we can compare the amount of rows we loaded to the amount of rows that we have inside of the original file.

### Duplicate Loading

If we run the query multiple times we will load the data over again, this will lead to us creating duplicate data entries. In order to avoid this we can truncate the table so that it refreshes the table everytime we run the query.

TRUNCATE TABLE (schema_name).(filename);

### Frequently used Scripts

When working with data there are some scripts that will be frequently used. We can save these scripts by storing them as procedures.

CREATE OR ALTER PROCEDURE (schema_name).(load_name) AS
BEGIN

    /*

    WRITTEN CODE

    */

END

The procedure will then be stored inside of the Programmability folder.
Now whenever we want to use this script to load data we can do:

EXEC (schema_name).(load_name)

### Errors

We can design different error messages inside of our script.

BRING TRY

    /*

    WRITTEN CODE

    */

END TRY

BEGIN CATCH

    */

    PRINT ERROR_MESSAGE();
    PRINT (different error message);

    */

END CATCH

### ETL Process Duration

To help us find errors, we can add more information to see which process is the bottleneck. 

DECLARE @start_time DATETIME, @end_time DATETIME, @batch_start_time DATETIME, @batch_end_time DATETIME; 

	SET @start_time = GETDATE();

    /*

    WRITTEN CODE

    */

	SET @end_time = GETDATE();

	PRINT '>> Load Duration: ' + CAST(DATEDIFF(second, @start_time, @end_time) AS NVARCHAR) + ' seconds';

This method can allow us to get the start and end time of each process, and print a message containing the speed of the process. Now we can track the speed of the ETL.