# Project Description

This project's goal is to get familiar with data modeling in PostgreSQL and performing ETL jobs in Python. First, we define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

Imagine the following scenario:

*A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.*

*They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.*


## Data Model 

Below you can see the ERD diagram with star schema for this project. I created this picture using https://dbdiagram.io/ website for free. The file "ERD.txt" contains the instructions on how to recreate such a picture. 

- fact table: songplays

- dimension tables: time, artists, users, songs

The schema is optimized for queries on song play analysis.

![plot](./pictures/ERD.png)

## Structure of the project

- data: contains the raw data in .json format
- scripts: contains python and scripts 
- notebooks: jupyter notebooks with exploratory etl and tests to check the correctness of the project
- pictures: pictures used to describe the project better - ERD diagram

## Raw data



## SQL queries

In the scripts/python/sql_queries.py you will find the queries passed as a list to other scripts and notebooks through 'from sql_queries import \*' statement. The queries perform the following operations:

1) drop tables if they already exist
2) create the tables according to the schema defined above
3) populate the tables with data
4) search for the song_id and artist_id based on song_title, artist_name and duration passed from script/notebook 

## ETL Job

In the notebook "etl.ipynb" we perform an exploratory analysis in order to populate the tables according to the schema.
The script in scripts/python called "etl.py" contains the clean version of the notebook. Here we process the full dataset i.e. song_data and log_data.

## Quick start

1) Install Anaconda and create a new virtual environment:

2) Run the shell script "run_scripts.sh" to install the requirements and create the schema, tables, populate the tables with data. Open the terminal window (Linux) and run the following command: ./scripts/shell/run_scripts.sh

3) Go to notebooks directory and run the tests.ipynb jupyter notebook. Run the cells to test the correctness queries