# Exploratory Data Analysis (EDA) Summary

## Overview
This document summarizes the exploratory data analysis performed on the cleaned employee HR dataset.

## Descriptive Statistics

### Key Metrics
- **Total Employees**: After removing duplicates based on email, the dataset contains 64 unique employees
- **Columns Analyzed**: All columns in the dataset were analyzed for descriptive statistics

### Summary Statistics
The following statistics were calculated for all applicable columns:
- Mean, median, standard deviation for numerical columns
- Count, unique values, mode for categorical columns
- Full statistics available in the notebook: `notebook/Part1.ipynb`

## Aggregate Metrics

### 1. Total Salary by Department
- **Purpose**: Understand the total compensation cost per department
- **Method**: Grouped by Department and summed Salary values
- **Visualization**: See `total_salary_by_department.png` (generated in notebook cell 23)
- **Key Insights**: 
  - **Admin** has the highest total salary: **$1,101,877**
  - **Finance** follows with: **$1,038,823**
  - **Cloud Tech**: **$936,323**
  - **Sales**: **$933,188**
  - **DevOps**: **$737,864**
  - **HR** has the lowest total salary: **$516,494**

### 2. Distribution of Performance by Department
- **Purpose**: Analyze performance score distribution across different departments
- **Method**: Grouped by Department and counted Performance_Score values
- **Visualization**: See `performance_distribution_by_department.png` (generated in notebook cell 24)
- **Key Insights**: 
  
  **Admin Department:**
  - Good: 7 employees
  - Excellent: 5 employees
  - Poor: 1 employee
  - Average: 1 employee
  
  **Cloud Tech Department:**
  - Average: 5 employees
  - Excellent: 3 employees
  - Poor: 2 employees
  - Good: 1 employee
  
  **DevOps Department:**
  - Excellent: 4 employees
  - Poor: 2 employees
  - Average: 2 employees
  - Good: 1 employee
  
  **Finance Department:**
  - Excellent: 5 employees
  - Average: 5 employees
  - Good: 3 employees
  
  **HR Department:**
  - Poor: 2 employees
  - Excellent: 2 employees
  - Average: 1 employee
  - Good: 1 employee
  
  **Sales Department:**
  - Average: 5 employees
  - Good: 3 employees
  - Poor: 2 employees
  - Excellent: 1 employee

### 3. Distribution of Employees by Region
- **Purpose**: Understand the geographic distribution of employees
- **Method**: Counted employees grouped by Region
- **Visualization**: See `employees_by_region.png` (generated in notebook cell 25)
- **Key Insights**: 
  - **Nevada** has the most employees: **15 employees**
  - **California**: **14 employees**
  - **New York**: **11 employees**
  - **Florida**: **9 employees**
  - **Illinois**: **9 employees**
  - **Texas** has the fewest employees: **6 employees**

## Notes
- All visualizations are generated from the cleaned dataset
- Detailed code and results are available in the Jupyter notebook: `notebook/Part1.ipynb`
- Statistics are calculated after data cleaning operations (duplicate removal, data type conversions, etc.)
- Total number of employees: 64 (after removing duplicates based on email)
