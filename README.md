# Data-Modeling-With-Postgres<h2>Introduction</h2>
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. <strong>This project creates ETL pipeline and a Postgres database with tables designed to optimize queries for the Sparkify's analysis.</strong>
(---------------------------------)
<h2>Database Star Schema Design</h2>
<h4>Fact Table:</h4>
<ol>
<li>songplays - records in log data associated with song plays</li>
<ul>
<li>songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent</li>
</ul>
</ol>

<h4>Dimension Tables:</h4>
<ol>
<li>users - users in the app</li>
<ul>
<li>user_id, first_name, last_name, gender, level</li>
</ul>
<li>songs - songs in music database</li>
<ul>
<li>song_id, title, artist_id, year, duration</li>
</ul>
<li>artists - artists in music database</li>
<ul>
<li>artist_id, name, location, latitude, longitude</li>
</ul>
<li>time - timestamps of records in songplays broken down into specific units</li>
<ul>
<li>start_time, hour, day, week, month, year, weekday</li>
</ul>
</ol>
(---------------------------------)
<h2>ETL Pipeline</h2>
The song dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song.<br>
The log dataset consists of log files in JSON format generated by this [event simulator](https://github.com/Interana/eventsim) based on the songs in the dataset above. <br>
The etl.py script will automate the ETL process by getting JSON files mentioned above, loading and proccessing data features in pandas dataframe, applying SQL queries implemented in sql_queries.py to insert data into tables.
(---------------------------------)
<h2>Running Instruction</h2>
<ol>
<li>Run create_tables.py to drop tables(if existed) and create tables</li>
<li>Run etl.py to do the ETL process</li>
<li>Run test.ipynb to see the results or write your queries to play around with the tables</li>
</ol>
NOTE: You will not be able to run test.ipynb, etl.ipynb, or etl.py until you have run create_tables.py at least once to create the sparkifydb database, which these other files connect to.
(---------------------------------)
<h2>Queries and Results Examples</h2>
![Examples of getting songplays and users table data](Postgres Example.png)
