# Spark-1
requirements
1. Data pipeline installation
Create a directory on HDFS for staging area called /user/[GROUP]/[YOUR NAME]/assignment2
where [GROUP] is the program. Ask the instructor if you don’t have it and [YOUR NAME] is a 
nickname of your choice with only lowercase letters.
Create a directory for each source table called /user/[GROUP]/[YOUR NAME]/assignment2/[TABLE 
NAME] where [TABLE NAME] is from the following list
• trips
• calendar_dates
• routes
Create a directory for the result: /user/[GROUP]/[YOUR NAME]/assignment2/enriched_trip

2. Extract data from STM to staging area
Download the data set of STM GTFS from http://stm.info/sites/default/files/gtfs/gtfs_stm.zip
Put extracted version into /user/[GROUP]/[YOUR NAME]/assignment2/[TABLE NAME] path on 
HDFS where [TABLE NAME] here is the name of file without extension.
We just need the following tables
• trips
• calendar_dates
• routes

3. Data pipeline
Enrich trips with calendar dates and routes and write it to the enriched_trip folder.
1. Read trips, calendar dates and routes into RDD
2. Convert each RDD to keyed RDDs
3. Use the ‘join’ API of RDD to first join trips with calendar dates on service ID and then join the 
result with routes on route ID4. Following the data model, write the result on HDFS. The result should be a valid CSV file
