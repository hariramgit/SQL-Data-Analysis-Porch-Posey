# Project Title: Advanced SQL Analysis for Business Insights Porch & Porsey Data

## Overview
This project involves performing advanced SQL queries and analysis on a business dataset for Parch & Posey, a company involved in paper sales. The dataset includes tables such as orders, accounts, web_events, and sales_reps. The goal is to extract valuable insights through a variety of SQL techniques, including filtering, sorting, joining, aggregating, window functions, and more.
This project demonstrates the power of SQL in analyzing business data and extracting actionable insights. By leveraging various SQL techniques, from simple retrieval to advanced window functions and joins, analysts can uncover patterns and trends to inform strategic decisions.

## Project Description
The project associated with this script appears to be for setting up a database for a company or organization named Parch and Posey. This company likely needs a system to manage data related to their sales operations, accounts, orders, sales representatives, regions, and web events. The database serves as a centralized repository for storing and managing this data, which is essential for various business processes like order tracking, sales analysis, and customer relationship management.

Here’s a summary of what each table represents in the context of the business:
**accounts**: Represents clients or businesses that are customers of Parch and Posey.
**orders**: Stores information about product orders made by each account, including details like quantities and amounts.
**region**: Provides a categorization of geographical areas, which could be used to analyze sales performance or assign sales representatives.
**sales_reps**: Contains data about sales representatives, who are responsible for managing accounts within specific regions.
**web_events**: Logs events on the company’s website related to accounts, such as visits or interactions, which can be useful for marketing analysis and customer engagement strategies.


## Use Case and Purpose
The database is designed to support various business functions, such as:

****Sales Management:** Tracking orders, sales representatives, and their associated regions helps manage and optimize sales efforts.
**Customer Relationship Management (CRM):** Storing account information and web events allows for better understanding and engagement with customers.
**Data Analysis: **The structured storage of orders, web events, and sales data enables reporting and analysis to drive business decisions, such as identifying high-performing regions or sales reps and understanding customer behavior

## Steps Involves:

### Database Setup:

The script begins by dropping any existing parch_and_posey database (DROP DATABASE parch_and_posey;) and then creates a new one with the same name. The CREATE DATABASE statement specifies the use of the template0 template and sets the character encoding to UTF8 with specific locale settings (LC_COLLATE and LC_CTYPE).

### Connection and Configuration:

After creating the database, the script connects to the parch_and_posey database (\connect parch_and_posey) and sets various configuration options, such as timeouts, encoding, and client messages. These configurations ensure that the database operates with specific settings suited for the application or environment.

### Table Creation:

The script then creates several tables within the public schema:
**accounts**: Stores information about different accounts, including fields like id, name, website, latitude (lat), longitude (long), primary_poc (Point of Contact), and sales_rep_id.
**orders**: Tracks orders made by accounts, containing fields like id, account_id, occurred_at (timestamp of the order), quantities of different products (standard_qty, gloss_qty, poster_qty), and corresponding amounts in USD.
**region**: Contains information about different regions with id and name.
**sales_reps**: Lists sales representatives, with fields for id, name, and region_id.
**web_events**: Records web events associated with accounts, with fields for id, account_id, occurred_at (timestamp of the event), and channel (source of the event).

### Constraints and Relationships:

The script establishes primary keys for each table to ensure unique identification of records. For example:
**Primary Keys**: id fields in each table are set as primary keys (accounts_pkey, orders_pkey, region_pkey, sales_reps_pkey, web_events_pkey).
**Foreign Keys**: The script also defines foreign key constraints to maintain referential integrity:
**accounts_sales_rep_id_fkey**: Links the sales_rep_id in accounts to the id in sales_reps.
**orders_account_id_fkey**: Links the account_id in orders to the id in accounts.
**sales_reps_region_id_fkey**: Links the region_id in sales_reps to the id in region.
**web_events_account_id_fkey**: Links the account_id in web_events to the id in accounts.

**ON DELETE CASCADE**: This clause ensures that deleting a record in a parent table will also delete all related records in child tables, preventing orphaned records.

## SQL Functions and Queries Used in This Project
**Cleaning and Analysing**

### Basic SQL Queries:

**SELECT**: Retrieve specific columns from a table.
**LIMIT**: Restrict the number of rows returned in a query.
**ORDER** **BY**: Sort results by one or more columns.
**WHERE**: Filter records based on specific conditions.
**BETWEEN**: Filter results within a range of values.

### Advanced Filtering and Pattern Matching:

**IN**: Filter results based on a list of values.
**LIKE**: Perform pattern matching with wildcards.
**NOT IN and NOT LIKE**: Exclude results based on specific conditions.

### Aggregate Functions and Window Functions:

**SUM():** Calculate the sum of a numeric column.
**AVG():** Compute the average value of a numeric column.
**MIN() and MAX():** Find the minimum and maximum values in a column.
**COUNT():** Count the number of rows that match a specific condition.
**WINDOW FUNCTIONS:** Use functions like SUM(), COUNT(), AVG(), MIN(), and MAX() with the OVER clause to perform calculations across a set of table rows related to the current row.
**RANK() and DENSE_RANK():** Assign a rank to each row within a partition.
**NTILE():** Divide rows into a specified number of groups and assign a group number to each row.

### Join Operations:

**INNER JOIN**: Combine rows from two tables based on a related column.
**LEFT JOIN**: Return all records from the left table and matched records from the right table.
**FULL OUTER JOIN**: Return all records when there is a match in either left or right table records.
**LEFT JOIN with Inequality Comparison**: Use inequality operators in join conditions.

### Subqueries and Common Table Expressions (CTEs):

Subqueries: Use queries within other queries to perform operations in multiple steps.
Common Table Expressions (WITH clause): Define temporary result sets that can be referenced within a SELECT, INSERT, UPDATE, or DELETE statement.

### Performance Tuning and Optimization:

**EXPLAIN:** Analyze query execution plans to optimize performance.
**INDEXING:** Although not directly shown in the queries, understanding the importance of indexing is crucial for performance optimization in large datasets.

### LEAD and LAG Functions:

**LEAD():** Access data from subsequent rows in the result set.
**LAG():** Access data from preceding rows in the result set.

###UNION and UNION ALL:

**UNION**: Combine the result sets of two or more queries, removing duplicates.
**UNION ALL**: Combine the result sets of two or more queries, including duplicates.

### Date and Time Functions:

**DATE_TRUNC():** Truncate a date or timestamp to a specified precision.

### Custom Calculations:

**Derived Columns**: Create new columns in the SELECT statement based on calculations (e.g., unit price calculation, percentage calculations).

### Triggers, CTE, Normalization, Stored Procedures and soo,..

