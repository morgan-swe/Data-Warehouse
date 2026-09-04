# Analyzing Source Systems

In order to understand sources you would need to meet with the source systems expert, and ask them questions. 

## Common Questions
 
### Business Context & Ownership

- Who owns the data?
- What business process does this support?
- System & data documentation
- Data model & data catalog

### Architecture & Technology Stack

- How is the data stored? (SQL Server, Oracle, AWS, ...)
- What are the integration capabilities? (API, Kafka, File Extract, ...)

### Extract & Load

- Incremental load vs. full load
- Data scope & historical needs
- What is the expected size of the extracts?
- Are there any data volume limitations?
- How to avoid impacting the source system's performance?
- Authentication and authorization (Tokens, SSH keys, VPN, IP, ...)