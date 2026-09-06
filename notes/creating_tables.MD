# Creating Tables for Database

When creating the Data Definition Language for our bronze layer, what we do is that we create tables inside of a database using Microsoft SQL Server Management Studio. We create a table for every .csv file, and each table will contain the same contents using the header column of the csv file.

Example: 
csv file's first row contains: id,key,firstname,lastname,date
We will then transform this into a table: 

CREATE TABLE (schema_name).(csv_filename) (
id INT,
key NVARCHAR(50),
firstnane NVARCHAR(50),
lastname NVARCHAR(50),
date DATE
);

We have the csv file column names followed by the data type that the column contains.

## Observations

### TIME vs DATETIME

TIME: 
- HH:MM:SS
- Example time would look like: 14:30:00
- Used when specific hour of the dcay is relevent and calendar date is irrelevant
- Use cases: business hours, shift durations, daily recurring log schedules

DATETIME:
- YYYY-MM-DD HH:MM:SS
- Example time would look like: 2026-09-05 14:30:00
- Snapshot moment on the calendar
- Use cases: transaction logs, appointment schedules, project deadlines