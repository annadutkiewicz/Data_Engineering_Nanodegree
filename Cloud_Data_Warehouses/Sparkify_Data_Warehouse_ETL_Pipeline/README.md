# Sparkify Data Warehouse ETL Pipeline
## Introduction
A ficticious music streaming startup, Sparkify, has grown their user base and song database and want to move their processes and data onto the cloud. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

In this project there will be built ETL pipeline that extracts the data from S3, stages them in Redshift, and transforms data into a set of dimensional tables for analytics team to continue finding insights in what songs their users are listening to.

## Schema for Song Play Analysis
### Fact Table
1. **songplays** - records in event data associated with song plays i.e. records with page NextSong
- ```songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent```
### Dimension Tables
2. **users** - users in the app
- ```user_id, first_name, last_name, gender, level```
3. **songs** - songs in music database
- ```song_id, title, artist_id, year, duration```
4. **artists** - artists in music database
- ```artist_id, name, location, lattitude, longitude```
5. **time** - timestamps of records in songplays broken down into specific units
- ```start_time, hour, day, week, month, year, weekday```

## File Description
The project includes four files:
- ```create_table.py``` is where fact and dimension tables for the star schema in Redshift will be created
- ```etl.py``` is where data will be loaded from S3 into staging tables on Redshift and then process that data into your analytics tables on Redshift
- ```sql_queries.py``` is where SQL statements will be created, which will be then imported into the two other files above
- ```README.md``` is where ETL pipeline process is described
