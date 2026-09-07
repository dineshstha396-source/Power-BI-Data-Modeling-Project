# Power BI Data Modeling Project

A practical Power BI data modeling project focused on building a clean, reliable, and analysis-ready semantic model from raw business data.

The goal of this project was not simply to load data into Power BI, but to understand the data, define the business grain, build appropriate dimension and fact tables, establish relationships, validate numbers, and apply security and modeling best practices.

---

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

The final model follows a dimensional/star-schema-oriented structure with separate dimension and fact tables.

---

## Modeling Workflow

The project was developed through four main stages:

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

**Principle: Understand the data before changing the data.**

---

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

---

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

---

### 4. Polish the Model & Apply RLS

The final stage focused on making the model cleaner, safer, and easier to use.

Activities included:

- Renaming columns
- Standardizing naming conventions
- Removing unnecessary columns
- Validating relationships
- Reviewing cardinality and filter directions
- Organizing the model
- Hiding technical fields where appropriate
- Creating measures
- Implementing Row-Level Security (RLS)
- Rechecking totals after transformations

---

# Modeling Principles

Throughout the project, I followed four core rules.

### 1. Build a proper schema

Tables should have a clear purpose and relationships should represent the underlying business logic.

### 2. Understand before making changes

I avoided transforming or deleting fields without first understanding what they represented and how they were being used.

### 3. Every column must earn its place

If a column does not contribute to analysis, relationships, calculations, filtering, or business understanding, it should be questioned rather than automatically kept.

> If it does not help the model or the report, why is it there?

### 4. Protect the numbers

Data modeling is ultimately about producing trustworthy numbers.

I repeatedly checked:

- Row counts
- Totals
- Relationships
- Aggregations
- Key matching
- Results before and after transformations

The objective was to make sure that cleaning and restructuring the data did not silently change the underlying business numbers.

---

# Naming Standards

Consistent naming conventions were applied throughout the model.

### Language

- English

### Tables

Dimension tables:

`dim_<entity>`

Examples:

```text
dim_customer
dim_product
dim_location
dim_date
