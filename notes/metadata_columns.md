# Metadata Columns

Metadata columns are extra columns added by data engineers that do not originate from the source data.

Engineers will use this to provide exta information for each record. 
Example:
We can add 
create_date: The record's load timestamp
update_date: The record's last update timestamp
source_system: The origin system of the record
file_location: The file source of the record

You can use these as tools to help track any issues you might find while working with the data.

