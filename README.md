# Eat Safe, Love - MongoDB Homework
## nosql-challenge


## Introduction

This repository contains two Jupyter notebooks that demonstrate the use of MongoDB for data storage, querying, and analysis. The notebooks are divided into three main parts: database setup, updating the database, and exploratory analysis.

## Notebooks

### 1. Database and Jupyter Notebook Set Up

This notebook sets up the MongoDB database and collection, imports the dataset, and performs initial queries to verify the setup.

#### Steps:
1. **MongoDB Import Command**: Imports `establishments.json` into MongoDB.
    ```bash
    mongoimport --db uk_food --collection establishments --drop --file establishments.json --jsonArray
    ```
2. **Dependencies**: Imports necessary libraries.
3. **MongoClient Instance**: Creates an instance of MongoClient.
4. **Database Listing**: Lists all databases, including `uk_food`.
5. **Collection Listing**: Lists all collections in the `uk_food` database, which includes `establishments`.
6. **Find One Document**: Uses `find_one()` and `pprint` to display a document from the `establishments` collection.
7. **Assign Collection**: Assigns the `establishments` collection to a variable for further operations.

### 2. Update the Database

This notebook performs updates on the `establishments` collection to reflect new data and modify existing data.

#### Steps:
1. **Insert New Restaurant**: Adds the "Penang Flavours" restaurant to the `establishments` collection.
2. **Find BusinessTypeID**: Queries to find the `BusinessTypeID` for "Restaurant/Cafe/Canteen".
3. **Update BusinessTypeID**: Updates the "Penang Flavours" document with the correct `BusinessTypeID`.
4. **Delete Dover Documents**: Deletes all documents with `LocalAuthorityName` as "Dover".
5. **Verify Deletion**: Uses `count_documents()` before and after deletion to ensure documents were removed.
6. **Update Data Types**: Uses `update_many()` to convert latitude and longitude to decimal numbers and `RatingValue` to integers.

### 3. Exploratory Analysis

This notebook performs various queries to analyze the data in the `establishments` collection.

#### Questions:
1. **Hygiene Score 20**: Finds establishments with a hygiene score of 20, converts results to a DataFrame, and displays the first 10 rows.
2. **London RatingValue >= 4**: Finds establishments in London with a `RatingValue` of 4 or higher, uses `$regex` to locate London establishments, and converts results to a DataFrame.
3. **Top 5 Establishments Near "Penang Flavours"**: Finds the top 5 establishments with a `RatingValue` of 5, sorted by lowest hygiene score, near "Penang Flavours".
4. **Hygiene Score 0 by Local Authority**: Uses an aggregation pipeline to count establishments with a hygiene score of 0 by Local Authority, sorts results, and converts them to a DataFrame.

## Deployment and Submission

1. **GitHub Repository**: Clone this repository to your local machine.
2. **Command Line Usage**: Use the command line to add your files to the repository.
3. **Commit Messages**: Include appropriate commit messages for all your changes.

## Comments

The code is well-commented to provide clear explanations for each step, making it easy for other developers to understand.

## Setup

To run these notebooks, you need to have MongoDB installed and running on your local machine. You also need to install the necessary Python packages:

```bash
pip install pymongo pandas
