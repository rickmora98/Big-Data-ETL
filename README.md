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
 
