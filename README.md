# Project Name: Crowdfunding_ETL

This Python project is designed to process crowdfunding data and create a Crowdfunding Database. The project involves extracting data from Excel files, transforming and cleaning the data, and then exporting it as CSV files. Additionally, a Postgres database is created to store the processed data.

## Project Structure

The project is divided into the following sections:

1. Create the Category and Subcategory DataFrames
2. Create the Campaign DataFrame
3. Create the Contacts DataFrame
4. Create the Crowdfunding Database

## Instructions

### 1. Create the Category and Subcategory DataFrames

This section involves extracting and transforming data from the `crowdfunding.xlsx` Excel file to create the `category` and `subcategory` DataFrames. The `category` DataFrame should contain two columns: `category_id` and `category`. The `subcategory` DataFrame should contain two columns: `subcategory_id` and `subcategory`. Both DataFrames should be exported as CSV files named `category.csv` and `subcategory.csv` respectively.

### 2. Create the Campaign DataFrame

In this section, data from the `crowdfunding.xlsx` Excel file is extracted and transformed to create the `campaign` DataFrame. The DataFrame should contain the following columns:

- `cf_id`: Crowdfunding ID
- `contact_id`: Contact ID
- `company_name`: Company name
- `description`: Blurb column renamed to description
- `goal`: Converted to float data type
- `pledged`: Converted to float data type
- `outcome`: Outcome column
- `backers_count`: Number of backers
- `country`: Country
- `currency`: Currency
- `launch_date`: Launched date (UTC times converted to datetime format)
- `end_date`: Deadline (UTC times converted to datetime format)
- `category_id`: Unique identification numbers matching the `category_id` column in the `category` DataFrame
- `subcategory_id`: Unique identification numbers matching the `subcategory_id` column in the `subcategory` DataFrame

The resulting `campaign` DataFrame should be exported as a CSV file named `campaign.csv`.

### 3. Create the Contacts DataFrame

In this section, you have two options for extracting and transforming data from the `contacts.xlsx` Excel file:

Option 1: Use Python dictionary methods.
Option 2: Use regular expressions.

#### Option 1:

If you choose Option 1, complete the following steps:

- Import the `contacts.xlsx` file into a DataFrame.
- Iterate through the DataFrame, converting each row to a dictionary.
- Extract the dictionary values from the keys using a Python list comprehension.
- Create a new DataFrame containing the extracted data.
- Split each "name" column value into a first and last name and place each in a new column.
- Clean and export the DataFrame as `contacts.csv`.

#### Option 2:

If you choose Option 2, complete the following steps:

- Import the `contacts.xlsx` file into a DataFrame.
- Extract the "contact_id," "name," and "email" columns using regular expressions.
- Create a new DataFrame with the extracted data.
- Convert the "contact_id" column to the integer type.
- Split each "name" column value into a first and last name and place each in a new column.
- Clean and export the DataFrame as `contacts.csv`.

### 4. Create the Crowdfunding Database

In this section, the data from the four CSV files (`category.csv`, `subcategory.csv`, `campaign.csv`, and `contacts.csv`) will be used to create a Crowdfunding Database.

- Inspect the four CSV files and create an Entity Relationship Diagram (ERD) using a tool like QuickDBD.
- Use the information from the ERD to create a table
