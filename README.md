# big-data-ETL 

This project utilizes Amazon RDS, Google Colaboratory, and PySpark to illustrate the ETL process for very large data sets.
For each jupyter notebook in this repository, a large file containing customer reviews for products sold on Amazon is retrieved from the Amazon
Web Service and loaded into a PySpark dataframe.
The dataframe is then broken into subsequent dataframes that will fit the tables defined in the schema file.
The subsequent dataframes are cleaned and then loaded into an Amazon RDS database.<br>

To examine and/or run the code files, their locations are indicated in the tree below.

#### Files/Folders:

+ **"Code"** <br>
	- *"schema.sql"* (sets up the database tables, <b>RUN THIS FIRST</b>) <br>
	- *"amazon_reviews_1A.ipynb"* (performs ETL on Amazon reviews for Health & Personal Care products) <br>
	- *"amazon_reviews_1B.ipynb"* (performs ETL on Amazon reviews for Pet products) <br>
	
Please do not delete, move, rename, or alter any of these folders and/or files. <br>
Thank you. <br>

#### Note: <br>

Please run the schema file in PostgreSQL before running the jupyter notebooks to set up the tables in your RDS database. <br>
Also, you will need to supply your RDS endpoint, database name, and password in the jupyter notebooks before running them. <br>
Also, due to the large size of the Amazon files that are used, the jupyter notebooks should be run in Google Colaboratory. <br>

#### Submitted by: <br>
 Ricardo G. Mora, Jr.  02/26/2022
<br><br><br>

PostgreSQL schema file to set up database tables:
```
CREATE TABLE review_id_table (
  review_id TEXT PRIMARY KEY NOT NULL,
  customer_id INTEGER,
  product_id TEXT,
  product_parent INTEGER,
  review_date DATE -- this should be in the formate yyyy-mm-dd
);

-- This table will contain only unique values
CREATE TABLE products (
  product_id TEXT PRIMARY KEY NOT NULL UNIQUE,
  product_title TEXT
);

-- Customer table for first data set
CREATE TABLE customers (
  customer_id INT PRIMARY KEY NOT NULL UNIQUE,
  customer_count INT
);

-- vine table
CREATE TABLE vine_table (
  review_id TEXT PRIMARY KEY,
  star_rating INTEGER,
  helpful_votes INTEGER,
  total_votes INTEGER,
  vine TEXT
);
```

<img src=/Images/Extract.jpg width="100%">

<img src=/Images/Transform.jpg width="90%">

<img src=/Images/Load.jpg width="45%">
