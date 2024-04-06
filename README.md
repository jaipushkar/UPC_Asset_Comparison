# UPC_Asset_Comparison

UPC Asset Comparison
This repository contains SQL queries for comparing ASIN (Amazon Standard Identification Number) data between two backup datasets of the Amazon UPC (Universal Product Code) database.

Overview
The SQL query provided in this repository compares the count of distinct ASINs between two backup datasets (backup_amazon_upc_11_12_2023 and backup_amazon_upc_11_02_2023) based on matching UPCs and ZIP codes.

SQL Query
_**SELECT COUNT(DISTINCT a.asin) 
FROM backup_amazon_upc_11_12_2023 AS a
LEFT JOIN backup_amazon_upc_11_02_2023 AS b
ON a.orig_upc = b.orig_upc AND a.zip = b.zip
WHERE a.asin <> b.asin;**_


Description
This query calculates the count of distinct ASINs from the latest backup (backup_amazon_upc_11_12_2023) where the ASINs do not match with the corresponding ASINs from the older backup (backup_amazon_upc_11_02_2023) for the same UPC and ZIP code combination.

How to Use
Clone this repository to your local machine.
Execute the provided SQL query in your SQL database environment, replacing the table names with your actual dataset names.
Analyze the result to identify discrepancies in ASIN counts between the two backups.
