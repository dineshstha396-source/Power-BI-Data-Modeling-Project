# Power BI Data Modeling Project

A practical Power BI data modeling project focused on building a clean, reliable, and analysis-ready semantic model from raw business data.

The goal of this project was not simply to load data into Power BI, but to understand the data, define the business grain, build appropriate dimension and fact tables, establish relationships, validate numbers, and apply security and modeling best practices.

## Project Overview

This project demonstrates the process of transforming raw business data into a structured Power BI semantic model suitable for reporting and analysis.

The model covers multiple business areas including:

- Sales
- Customers
- Products
- Locations
- Inventory
- Orders
- Campaigns
- Promotions
- Sales Targets
- Order Processing

The final model follows a dimensional modeling approach with separate dimension and fact tables.

## Modeling Workflow

The project was developed through four main stages.

### 1. Prepare & Explore

Before making transformations, I first focused on understanding the source data.

Key activities:

- Explored all source tables
- Reviewed columns and data types
- Identified relationships between datasets
- Checked duplicates and missing values
- Investigated the meaning of fields
- Identified potential dimensions and facts
- Considered the business grain of each table

**Principle: Understand before making changes.**

### 2. Build Dimensions

After understanding the source data, dimension tables were created and refined.

Examples include:

- `dim_customer`
- `dim_product`
- `dim_location`
- `dim_date`
- `dim_order_flag`
- `dim_campaign`

Dimension tables provide descriptive attributes used to filter, group, and analyze business events.

### 3. Build Fact Tables

Fact tables were created around measurable business events and processes.

Examples include:

- `fact_sales`
- `fact_inventory`
- `fact_order_process`
- `fact_campaign_spend`
- `fact_promotion_coverage`
- `fact_sales_target`

Each fact table was designed around a defined business grain and connected to relevant dimensions through keys.

### 4. Polish the Model & Apply RLS

The final stage focused on making the model cleaner, safer, and easier to use.

Activities included:

- Renaming columns
- Standardizing naming conventions
- Removing unnecessary columns
- Validating relationships
- Reviewing cardinality and filter directions
- Organizing the model
- Creating measures
- Implementing Row-Level Security (RLS)
- Rechecking totals after transformations

## Modeling Principles

Throughout the project, I followed four core rules.

### 1. Build a Proper Schema

Tables should have a clear purpose, and relationships should represent the underlying business logic.

### 2. Understand Before Making Changes

I avoided transforming or deleting fields without first understanding what they represented and how they were being used.

### 3. Every Column Must Earn Its Place

If a column does not contribute to analysis, relationships, calculations, filtering, or business understanding, it should be questioned rather than automatically kept.

> If it does not help the model or the report, why is it there?

### 4. Protect the Numbers

Data modeling is ultimately about producing trustworthy numbers.

I repeatedly checked:

- Row counts
- Totals
- Relationships
- Aggregations
- Key matching
- Results before and after transformations

The objective was to make sure that cleaning and restructuring the data did not silently change the underlying business numbers.

## Naming Standards

Consistent naming conventions were applied throughout the model.

### Language

- English

### Table Naming

Dimension tables use:

`dim_<entity>`

Examples:

- `dim_customer`
- `dim_product`
- `dim_location`
- `dim_date`

Fact tables use:

`fact_<business_process>`

Examples:

- `fact_sales`
- `fact_inventory`
- `fact_order_process`

### Column Naming

Columns follow consistent snake_case naming.

Examples:

- `customer_id`
- `customer_name`
- `product_key`
- `product_name`
- `campaign_key`
- `order_id`

The naming convention makes it easier to understand the role of fields and relationships.

## Model Structure

The final semantic model contains separate dimensions, facts, and supporting tables.

### Dimension Tables

- `dim_customer`
- `dim_product`
- `dim_location`
- `dim_date`
- `dim_order_flag`
- `dim_campaign`

### Fact Tables

- `fact_sales`
- `fact_inventory`
- `fact_order_process`
- `fact_campaign_spend`
- `fact_promotion_coverage`
- `fact_sales_target`

### Supporting Tables

- `Measure`
- `secure`

The model is designed so that dimensions provide business context while fact tables contain transactional or measurable business events.

## Row-Level Security

Row-Level Security (RLS) was implemented to control which rows users can access based on their assigned context.

The security design was treated as part of the data model rather than something added only at the end.

RLS was also reviewed against the model relationships to ensure that filters propagate correctly.

## Key Concepts Practiced

Through this project, I practiced:

- Dimensional modeling
- Star schema design
- Fact and dimension identification
- Grain definition
- Primary and foreign keys
- Relationships
- Cardinality
- Filter propagation
- Power Query transformations
- Data cleaning
- Data validation
- DAX measures
- Semantic model organization
- Row-Level Security
- Naming conventions
- Data quality checks
- Model documentation

## Tools Used

- Power BI Desktop
- Power Query
- DAX
- Excel
- Dimensional Modeling concepts

## What I Learned

The biggest lesson from this project was that Power BI modeling is not mainly about creating relationships between tables.

It is about understanding the business.

A good model should answer questions such as:

- What does each row represent?
- What is the grain of this table?
- Which tables describe the business?
- Which tables record business events?
- Which columns are keys?
- How should filters propagate?
- Can the same business number be reproduced after transformation?
- Does every field have a reason to exist?
- Can another analyst understand the model without asking the original developer?

The model is the foundation of the report.

If the foundation is wrong, even a visually impressive dashboard can produce misleading results.

## Project Structure

- `Data Modeling Project.pbix`
- `dataset.xlsx`
- `Screenshot (183).png`
- `README.md`

## Reference

This project follows core Power BI dimensional modeling principles, including the separation of fact and dimension tables and relationship-driven filter propagation.

Microsoft Learn:  
https://learn.microsoft.com/power-bi/guidance/star-schema
