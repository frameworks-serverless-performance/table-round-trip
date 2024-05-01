# Table round trip

This repository contains a jupyter notebook for creating the table data for a "table round-trip". This can be used for performance testing that involes doing a lot of database queries. The notebook generates the data needed and uploads it to a AWS DynamoDB table.

Steps to perform the round trip:
- An initial primary key is given
- Query for the item with the initial primary key
- Look for the next primary key in the `next_primary_key` field
- Query for the item with the next primary key
- Repeat until the initial primary key is reached again

The number of queries needed to perform the round trip can be adjusted by changing the `ROUND_TRIP_LENGTH` variable.

A backup of the exact data used for testing in the thesis *Performance and price comparison of three popular backend frameworks and the AWS serverless stack* is also available. Note that the file is not in standard JSON format, but uses "JSON lines", a format where the JSON objects are separated by newlines.
