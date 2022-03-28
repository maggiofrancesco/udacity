## The purpose of this database
The aim of this project is to design a PostgreSQL database in order to satisfy Sparkify needs. In particular, we need to find a database structure that allow us to execute the queries needed efficiently, also with a large amount of data. 
## Database design
We used the Star Schema, a typical data warehouses schema in which we have a fact table and more dimension tables. Using this schema we obtain a denormalized database which allows us to focus on the queries.
The fact table contains the IDs of the entities that are part of the business analysis (`user`, `song`, `artist`, `session`, `time`).
The dimension tables contain data that allow us to enrich the business analysis on our entities, with attributes related to users, songs and artists.

![sparkify_db drawio](https://user-images.githubusercontent.com/7735363/160462609-2a5ce2f6-c52e-49a3-b25f-f3dad87efef1.png)

## Python scripts and how to run it
- `create_tables.py`: need for database initialization. This script recreates all db tables using SQL queries in sql_queries.py;
- `sql_queries.py`: contains all about DDL and DML queries;
- `etl.ipynb`: Jupyter notebook that contains code used for playing with data using Pandas before implementing the complete pipeline;
- `etl.py`: script with the complete pipeline using all songs and log data loaded from the JSON files in the data folder;
- `test.ipynb`: Jupyter notebook in which we have code for testing the DB model correctness and the ETL pipeline.

In order to execute the ETL pipeline:
1. run create_tables.py
2. run etl.ipynb
3. run test.ipynb (optional)





