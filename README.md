# Crowdfunding ETL
This project used data which tracked companies that attempted projects with crowdfunding. Some companies succeeded while others failed. The companies represented different categories and subcategories of projects with various financial goals. The goal of this project is to practice building an ETL pipeline using Python, Pandas, and Python dictionary methods to extract and transform the data. We created four CSV files and used the CSV file data to create an ERD and a table schema. Finally we uploaded the CSV file data into a Postgres database and ran simple queries to ensure proper table creation and file imports.

## Skills
Python
Pandas
PostgreSQL
List Comprehension
QuickDBD

## Process
### Extract The Data
Data was imported into Jupyter Notebook and made into dataframes to be easily read. 


### Create the Category and Subcategory DataFrames
We looked at the unique list of categories (9) and subcategories (24) and added “cat” or “scat” to their unique ids. Both the categories and subcategories were displayed in data frames and exported to CSV files.


### Create the Campaign DataFrame
We then created a Campaign dataframe with a list of required columns. We renamed the “blurb” column to “description” and the “launched_at” to “launch_date” and “deadline” to “end_date” to be more descriptive of the data.

The “goal” and “pledged” columns were cast to a float data type and the “launch_date” and “end_date” were cast to date time in the YYYY-MM-DD format.

We then merged the campaign_df with the category_df based on the subcategory column and dropped unnecessary columns such as “spotlight” etc. and exported the data to a new CSV file called “campaign.csv.”


### Extract the Contacts DataFrame
Data was imported into Jupyter Notebook and made into data frames to be easily read. 


### Create the Contact DataFrame using Pandas
First, we iterated through the “contact_info” dataframe and converted each row to a dictionary, then appended to an empty list. 

We labeled the columns “contact_id,” “name,” and “email” and added the data from the appended list in order to make a neater dataframe. 

We verified that they were the correct data types. 

We split the name column into “first_name” and “last_name” and dropped the original “name”. 

We re-ordered the columns and again verified the data types were as they should be. 

We exported the dataframe as a CSV file titled “contacts.csv”.


### Create the Crowdfunding Database
After the four CSV files were created, we used QuickDBD Tool to create a visual representation of our table schema and primary and foreign key relationships. 

We used the QuickDBD export function to obtain a PNG image file of our table schema, as well as a SQL file that we could import into PostGreSQL PgAdmin. 

We created a database titled “crowdfunding_db” using PgAdmin. 

We opened the exported file from QuickDBD and ran the portion of the SQL code to create the tables, column structure, primary key assignments, and data types. 

After creating the tables, we imported the four CSV files to the appropriate tables. 

We ran the SQL code to connect the primary key and foreign key relationships among the tables. 

Finally, we ran simple queries to ensure the CSV files and subsequent data were imported correctly.


###  Acknowledgements
Amanda Pigman and Barb Rupps completed this project. We would like to acknowledge my instructor and TAs for their guidance and assistance in this project: Othmane Benyoucef, Jacob Peroutek, and Isabella Taylor. In addition, we researched help with code on Stack Overflow, GeeksforGeeks, and Github.
