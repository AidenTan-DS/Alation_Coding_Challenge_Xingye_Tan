# HR Agent - Answers to Questions

This document contains the answers to the three questions asked of the HR Agent.

## Question 1: Which Region(s) offer the highest salary to employees on average?

### Answer
**Illinois** offers the highest average salary to employees at **$94,400.11** per year.

### Detailed Results (sorted by average salary, descending):
- **Illinois**: $94,400.11
- **Texas**: $87,022.67
- **Florida**: $86,901.67
- **Nevada**: $81,318.67
- **New York**: $79,266.36
- **California**: $78,385.15

### Method
- Grouped data by Region
- Calculated mean salary for each region
- Sorted in descending order to identify the region(s) with highest average salary

### Visualization
See `q1_avg_salary_by_region.jpg` for visual representation.

---

## Question 2: Show me a list of top performers in each department?

### Answer
Top performers are defined as employees with Performance_Score == 'Excellent'. The list is organized by department:

| Department | First Name | Last Name |
|------------|------------|-----------|
| Admin | Heidi | Miller |
| Admin | Frank | Davis |
| Admin | Grace | Brown |
| Admin | Alice | Miller |
| Admin | Bob | Garcia |
| Cloud Tech | Alice | Smith |
| Cloud Tech | Charlie | Garcia |
| Cloud Tech | Charlie | Davis |
| DevOps | Grace | Miller |
| DevOps | Eva | Smith |
| DevOps | Bob | Smith |
| DevOps | Charlie | Johnson |
| Finance | Heidi | Johnson |
| Finance | David | Garcia |
| Finance | Bob | Johnson |
| Finance | Heidi | Garcia |
| Finance | Bob | Brown |
| HR | Bob | Miller |
| HR | Heidi | Williams |
| Sales | Bob | Williams |

**Total**: 20 top performers across all departments

### Method
- Filtered employees with Performance_Score == 'Excellent'
- Grouped by Department
- Selected First_Name, Last_Name, and Department columns
- Sorted by Department

### Visualization
See `q2_top_performers_by_department.jpg` for visual representation.

---

## Question 3: Show me a list of the most tenured employees in each department?

### Answer
The most tenured employee in each department (based on earliest Join_Date):

| Department | First Name | Last Name | Join Date |
|------------|------------|-----------|-----------|
| Admin | Charlie | Williams | 2020-01-02 |
| Cloud Tech | David | Miller | 2020-04-30 |
| DevOps | Eva | Miller | 2020-01-21 |
| Finance | Eva | Brown | 2020-07-08 |
| HR | Bob | Miller | 2021-05-08 |
| Sales | Alice | Garcia | 2020-06-10 |

### Method
- Converted Join_Date to datetime format
- Grouped by Department
- Found the employee with the minimum (earliest) Join_Date in each department
- Selected Department, First_Name, Last_Name, and Join_Date columns
- Sorted by Department

### Visualization
See `q3_most_tenured_by_department.jpg` for visual representation.

---

## Notes
- All answers are based on the cleaned dataset (`data/cleaned/employee_cleaned.csv`)
- Detailed calculations are available in the Jupyter notebook: `notebook/Part1.ipynb` (cells 27-29)
- For AI Agent implementation, these answers should be generated dynamically by the agent
- All calculations use the cleaned data after duplicate removal and data type conversions
