
## Sparkify Analytics Database

The team of sparkify wants to analyse the usage of their content by their users.
As they want to perform extensive analysis they need the usage data in an easily accessible manor.
Currently they are performing their analytics on log files and song files which are hard to handle.

Therefore this project holds an ETL to parse the data from the different files and stores them in a database. From the database the usage data is easily accessible and can be joined with meta data from songs, artists and users.

### Database-Schema

The applied table structure is a Star-Schema.
A fact table called **songs_played** holds information about when which songs was played by whom.

Different dimension tables supply the detailed meta data:

- **users** holds all the data about users like name and account type
- **songs** presents a dataset of all available songs with name, duration and the artist
- **artists** supplies detailed information about the artist such as name and location

The table **time** gives  information when songs where played. By storing the day, hour, weekday etc. in separat columns it gives an easy way to do detailed analytics on the timely usage.


### How-to run the scripts

Essentially there are two main functions that can be run.
- the **create_tables.py** deletes and (re-) creates all table of the database
- the **etl.py** is the pipeline parsing the files and storing the content to the database.

All SQL-queries to create, drop and fill the database tables are centrally stored in the file **sql_queries.py**.
For testing purposes there is a jupyter notebook called **test.ipynb**.
The jupyter notebook file **etl.ipynb** further describes the pipeline.

This branch holds a version compatible with newer Python.