# Database Management and SQL Integration with Python (Healthcare Data)
Project Overview

This project demonstrates an end-to-end workflow for managing healthcare data using Python, Pandas, and SQLite, with a focus on integrating SQL queries directly into a Python data analysis pipeline. The notebook simulates a small healthcare database containing patient demographics and visit-level cost data, illustrating how relational databases support data persistence, querying, and analysis in healthcare and public health contexts.

The project emphasizes practical skills commonly used in data, health informatics, and analytics roles, including database creation, table persistence, SQL querying, joins, aggregations, and validation through Pandas.

Objectives

Load and manage structured healthcare data using Pandas

Create and persist a relational SQLite database

Execute SQL queries from within Python

Apply filtering, sorting, joins, and conditional logic in SQL

Perform aggregations and summaries using SQL and Pandas

Compare SQL-based analysis with Pandas-based analysis

Technologies Used

Python

Pandas (data loading, manipulation, validation)

SQLite (relational database management)

Jupyter Notebook / Google Colab

SQL (SELECT, WHERE, ORDER BY, JOIN, GROUP BY, HAVING, CASE)

Dataset Description
Patients Table (patients.csv)

Contains demographic and diagnostic information for patients.

id: Unique patient identifier

name: Patient name

age: Patient age

diagnosis: Primary diagnosis (may be NULL)

Visits Table (visits.csv)

Contains visit-level healthcare utilization and cost data.

visit_id: Unique visit identifier

patient_id: Foreign key referencing patients.id

visit_date: Date of visit

cost: Cost of visit

Database Setup

Google Drive is mounted to ensure database persistence across sessions.

A disk-based SQLite database (healthcare_demo.db) is created and stored in Drive.

CSV files are loaded into Pandas DataFrames and written to SQLite tables using to_sql().

This approach prevents data loss when Colab sessions reset and mirrors real-world workflows where databases persist independently of analysis scripts.

Key SQL Operations Demonstrated
Data Retrieval and Filtering

Selecting all columns vs. specific fields

Filtering using WHERE, OR, and comparison operators

Sorting results using ORDER BY

Limiting output using LIMIT

Conditional Logic

Creating derived variables using CASE WHEN (e.g., high-cost visit flag)

Calculating insurance-adjusted costs

Joins

INNER JOIN to match patients with visits

LEFT JOIN to retain all patients regardless of visit history

FULL OUTER JOIN (emulated) using UNION to return all records from both tables

Aggregations

Overall summaries using COUNT, AVG, SUM, MIN, and MAX

Grouped summaries by patient using GROUP BY and HAVING

Patient-Level Summary Table

A summarized table (patient_summary) is created and stored in the database, containing:

Total number of visits per patient

Average, total, minimum, and maximum visit cost

This table demonstrates how analytical results can be written back to a database for reuse in reporting or downstream analysis.

Pandas vs. SQL Comparison

To validate results and demonstrate flexibility, the same patient-level summaries are:

Computed using SQL queries

Reproduced using Pandas merge() and groupby() operations

This comparison highlights how SQL and Pandas can be used interchangeably depending on workflow needs.

Persistence and Reproducibility

The SQLite database can be reconnected after the session ends

All tables remain accessible without reloading raw CSV files

The notebook can be exported to HTML using jupyter nbconvert for portfolio or reporting purposes

Use Cases

Healthcare data analysis

Health informatics and EHR-style workflows

SQL practice within Python environments

Portfolio demonstration of database and analytics skills

File Structure

Healthcare Data.ipynb – Main analysis notebook

patients.csv – Patient demographic data

visits.csv – Visit and cost data

healthcare_demo.db – Persistent SQLite database
