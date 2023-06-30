# Crowdfunding_ETL

For the ETL mini project, we practiced building an ETL pipeline using Python, Pandas, and Python dictionary methods to extract and transform the data. After we transformed the data, we created four CSV files and used the CSV file data to create an ERD and a table schema. Finally, we uploaded the CSV file data into a Postgres database. Although we divided the work, it was essential to collaborate and communicate while working on different parts of the project. We made it a point to check in with each other regularly and offer support.

To help us get started, we downloaded the starter code and files provided to us by our BootCamp. The instructions for this mini project a divided into the following subsections:
    *Create the Category and Subcategory DataFrames
    *Create the Campaign DataFrame
    *Create the Contacts DataFrame
    *Create the Crowdfunding Database
    *Create the Category and Subcategory DataFrames

Our goal was to extract and transform the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns:
      *A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories
      *A "category" column that contains only the category titles

To do this, we exported the category DataFrame as category.csv and extracted and transformed the crowdfunding.xlsx Excel data. We used this daya to create a subcategory DataFrame that had the following columns:
    *A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories
    *A "subcategory" column that contains only the subcategory titles

![alt text](https://github.com/msryannhawkins/Crowdfunding_ETL/blob/main/Starter_Files/DF_Images/DF1.png
 "DF1")

After we exported the subcategory DataFrame as subcategory.csv, we extracted and transformed the crowdfunding.xlsx Excel data and created a campaign DataFrame has the following columns:
    *The "cf_id" column
    *The "contact_id" column
    *The "company_name" column
    *The "blurb" column, renamed to "description"
    *The "goal" column, converted to the float data type
    *The "pledged" column, converted to the float data type
    *The "outcome" column
    *The "backers_count" column
    *The "country" column
    *The "currency" column
    *The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format
    *The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
    *The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
    *The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame

![alt text](https://github.com/msryannhawkins/Crowdfunding_ETL/blob/main/Starter_Files/DF_Images/DF2.png
 "DF2")

Lastly, we needed to create the Contacts DataFrame. To do this, the following were the steps that we took to use Python dictionary.
    *Imported the contacts.xlsx file into a DataFrame.
    *Iterated through the DataFrame, converting each row to a dictionary.
    *Iterated through each dictionary, doing the following:
    *Extracted the dictionary values from the keys by using a Python list comprehension.
    *Added the values for each row to a new list.
    *Created a new DataFrame that contains the extracted data.
    *Split each "name" column value into a first and last name, and place each in a new column.
    *Clean and export the DataFrame as contacts.csv and saved it to your GitHub repository.

![alt text](https://github.com/msryannhawkins/Crowdfunding_ETL/blob/main/Starter_Files/DF_Images/DF3.png
 "DF3")

In our final portion of the project, we inspected the four CSV files, and then sketch an ERD of the tables by using QuickDBDLinks. We then used the information from the ERD to create a table schema for each CSV file. It was helpful to remember to specify the data types, primary keys, foreign keys, and other constraints.

![alt text](https://github.com/msryannhawkins/Crowdfunding_ETL/blob/main/Starter_Files/DBD%20Crowdfunding.png
 "ERD")

We saved the database schema as a Postgres file named crowdfunding_db_schema.sql, and saved it to our GitHub repository. We create a new Postgres database, named crowdfunding_db. Using the database schema, we were able to create the tables in the correct order to handle the foreign keys. We verified the table creation by running a SELECT statement for each table. We imported each CSV file into its corresponding SQL table and verified that each table had the correct data by running a SELECT statement for each.

We found it helpful to do the following throughout this project.
    *To split each "category & sub-category" column value into "category" and "subcategory" column values, use df[["new_column1","new_column2"]] = df["column"].str.split(). Make sure to pass the correct parameters to the split() function.
    
    *To get the unique category and subcategory values from the "category" and "subcategory" columns, create a NumPy array where the array length equals the number of unique categories and unique subcategories from each column. For information about how to do so, see numpy.arangeLinks to an external site. in the NumPy documentation.
    
    *To create the category and subcategory identification numbers, use a list comprehension to add the "cat" string or the "subcat" string to each number in the category or the subcategory array, respectively.

    *To convert the "goal" and "pledged" columns to the float data type, use the astype() method.
    
    *To convert the "launch_date" and "end_date" UTC times to the datetime format, see the Transform_Grocery_Orders_Solved.ipynb activity solution.
