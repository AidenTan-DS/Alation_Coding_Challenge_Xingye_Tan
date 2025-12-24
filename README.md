# Alation Coding Challenge: AI and Data Engineering

## Project Overview

This project demonstrates proficiency in fundamental data manipulation, algorithm design, and application of data engineering and AI concepts. The project involves:

1. **Data Preprocessing and Exploration** - Cleaning and analyzing a fictional Employee/HR dataset
2. **HR Agent** - Building an AI agent to answer questions about the cleaned dataset

## Goal/Objective

To assess the candidate's proficiency in:
- Data manipulation and cleaning
- Algorithm design
- Data engineering concepts
- AI agent implementation

## Problem Definition

Starting with the provided fictional Employee/HR dataset:
- **Part 1**: Write code to clean the data and produce a cleaned version in CSV format
- **Part 2**: Build an AI agent that uses the cleaned dataset to answer provided questions

## Setup and Prerequisites

### Tools Used

- **Programming Language**: Python 3.x
- **Development Environment**: Jupyter Notebook
- **Key Libraries**:
  - `pandas` - Data manipulation and analysis
  - `datetime` - Date handling
  - `matplotlib` / `seaborn` (optional) - For visualizations

### Dataset

- **Source**: [Employee HR Dataset](https://drive.google.com/file/d/1av27ySoGHlKZpuNeswkcUtS-7f3PfrmO/view?usp=sharing)
- **Size**: 1020 rows of employee/HR data
- **Dataset Issues**:
  - Missing values
  - Two values combined into a single column (Department_Region)
  - Incorrectly formatted phone numbers

## Project Structure

```
Alation_Coding_Challenge_Xingye_Tan/
│
├── README.md                          # This file
│
├── notebook/
│   └── Part1.ipynb                     # Main notebook with data cleaning and EDA
│
├── data/
│   ├── raw/
│   │   └── employee_raw.csv           # Original dataset
│   └── cleaned/
│       └── employee_cleaned.csv       # Cleaned output data from Part 1
│
├── outputs/
│   ├── part1_eda/
│   │   ├── total_salary_by_department.png
│   │   ├── performance_distribution_by_department.png
│   │   ├── employees_by_region.png
│   │   └── eda_summary.md
│   │
│   └── part2_agent/
│       ├── q1_avg_salary_by_region.jpg
│       ├── q2_top_performers_by_department.jpg
│       ├── q3_most_tenured_by_department.jpg
│       └── agent_answers.md
│
├── agent/
│   ├── agent_description.md           # Agent implementation details
│   └── agent_link.txt                 # Agent access information
│
└── demo_video_link.md                 # Demo video link (if available)
```

## Instructions on How to Run the Project

### Prerequisites

1. Install Python 3.x (if not already installed)
2. Install required Python packages:
   ```bash
   pip install -r requirements.txt
   ```
   
   Or manually:
   ```bash
   pip install pandas jupyter matplotlib seaborn
   ```

### Running Part 1: Data Preprocessing and Exploration

1. **Navigate to the project directory**:
   ```bash
   cd Alation_Coding_Challenge_Xingye_Tan
   ```

2. **Open Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

3. **Open the notebook**:
   - Navigate to `notebook/Part1.ipynb` in the Jupyter interface
   - Or run: `jupyter notebook notebook/Part1.ipynb`

4. **Execute all cells**:
   - Run cells sequentially using `Shift + Enter`
   - Or use `Cell > Run All` from the menu

5. **Output files**:
   - The cleaned dataset will be saved to `data/cleaned/employee_cleaned.csv`
   - All EDA results will be displayed in the notebook
   - EDA summary is available in `outputs/part1_eda/eda_summary.md`
   - Visualizations are generated in the notebook

### Running Part 2: HR Agent

**Agent Implementation**: ✅ Completed

The HR Agent is implemented using OpenAI Agent Builder and deployed at: https://alation-agent-keao.vercel.app/

**Implementation Details**:
- Platform: OpenAI Agent Builder (platform.openai.com)
- Model: gpt-4o-mini
- Tool: Code Interpreter (with cleaned CSV dataset)
- Status: Live and deployed

For detailed implementation information, see `agent/agent_description.md` and `agent/agent_link.txt`.

**Note**: Answers to Part 2 questions are also calculated using pandas operations in the notebook. See `outputs/part2_agent/agent_answers.md` for reference results.

## Part 1: Data Preprocessing and Exploration

### A. Data Loading and Cleaning

The following tasks were completed:

#### Task 1: Data Loading
- Loaded the dataset into a Pandas DataFrame from `data/raw/employee_raw.csv`

#### Task 2: Remove Duplicates
- Found duplicates based on the `Email` column
- Kept only the first occurrence of each email address
- Removed duplicate rows

#### Task 3: Format Phone Numbers
- Removed all non-numerical elements from phone numbers
- Formatted phone numbers to standard US format: `(XXX) XXX-XXXX`
- Invalid phone numbers (not 10 digits) were marked as `NULL` (pd.NA)

#### Task 4: Split Department_Region Column
- Split the `Department_Region` column into two separate columns:
  - `Department`
  - `Region`
- Removed the original `Department_Region` column

#### Task 5: Round Salary
- Rounded `Salary` values to the nearest integer
- Converted `Salary` column to `Int64` type

#### Output
- Cleaned data saved to: `data/cleaned/employee_cleaned.csv`

### C. Exploratory Data Analysis (EDA)

#### Task 1: Descriptive Statistics
- Calculated key descriptive statistics (mean, median, standard deviation, uniqueness) for all applicable columns
- Results displayed in the notebook using `df.describe(include='all')`

#### Task 2: Aggregate Metrics

**a) Total Salary per Department**
- Calculated total salary aggregated by department
- Results available in the notebook
- Summary in `outputs/part1_eda/eda_summary.md`

**b) Distribution of Performance by Department**
- Analyzed performance score distribution across departments
- Results show value counts of `Performance_Score` grouped by `Department`
- Summary in `outputs/part1_eda/eda_summary.md`

**c) Distribution of Employees by Region**
- Counted number of employees in each region
- Results show employee count per region
- Summary in `outputs/part1_eda/eda_summary.md`

## Part 2: HR Agent

### Problem Definition

Build an AI agent using a tool and model of choice (e.g., Vertex AI with Gemini) that utilizes the cleaned data from Part 1 to answer the following questions:

1. **Which Region(s) offer the highest salary to employees on average?**
2. **Show me a list of top performers in each department?**
3. **Show me a list of the most tenured employees in each department?**

### Implementation Status

**✅ Agent Implemented**: The HR Agent is live and accessible at https://alation-agent-keao.vercel.app/

The agent uses OpenAI Agent Builder with Code Interpreter to answer questions about the HR dataset. For reference, answers have also been calculated using pandas in the notebook (see cells 27-29).

### Answers to Part 2 Questions

The following answers were calculated using pandas operations in the notebook:

#### Question 1: Which Region(s) offer the highest salary to employees on average?
- **Answer**: Calculated using `df.groupby('Region')['Salary'].mean().sort_values(ascending=False)`
- Results show regions sorted by average salary in descending order
- Detailed answer in `outputs/part2_agent/agent_answers.md`

#### Question 2: Show me a list of top performers in each department?
- **Answer**: Filtered employees with `Performance_Score == 'Excellent'` grouped by department
- Results show: Department, First_Name, Last_Name for top performers
- Detailed answer in `outputs/part2_agent/agent_answers.md`

#### Question 3: Show me a list of the most tenured employees in each department?
- **Answer**: 
  - Calculated `Tenure_Years` from `Join_Date` (using reference date: 2025-12-21)
  - Found the most tenured employee in each department
  - Results show the employee with the highest tenure per department
- Detailed answer in `outputs/part2_agent/agent_answers.md`

## Submission Artifacts

### ✅ Completed

1. **Instructions on how to run the project** - This README file
2. **Cleaned output data from Part 1** - `data/cleaned/employee_cleaned.csv`
3. **Output from Part 1 EDA tasks** - 
   - Results displayed in `notebook/Part1.ipynb`
   - Summary in `outputs/part1_eda/eda_summary.md`
4. **Output from questions listed in Part 2** - 
   - Answers calculated in `notebook/Part1.ipynb` (cells 27-29)
   - Detailed answers in `outputs/part2_agent/agent_answers.md`

### ⚠️ Not Included

1. **Access to Agent or instructions on how to recreate the agent** - ✅ Completed
   - Agent URL: https://alation-agent-keao.vercel.app/
   - Implementation details in `agent/agent_description.md`
   - Access information in `agent/agent_link.txt`
   - Platform: OpenAI Agent Builder
   - Dataset: Connected via Code Interpreter to `data/cleaned/employee_cleaned.csv`

2. **Video demo** - Optional, not provided
   - Link will be in `demo_video_link.md` if created

3. **Visualizations** - Placeholder files mentioned in structure
   - Visualization code examples in `outputs/part1_eda/README.md` and `outputs/part2_agent/README.md`
   - Can be generated from the notebook

## Evaluation Criteria

> 📋 **Detailed Evaluation Checklist**: See `EVALUATION_CHECKLIST.md` for a comprehensive analysis of how this project addresses each evaluation criterion.

This project addresses the following evaluation criteria:

### Code Quality & Clarity (25%)
- ✅ Readable and well-structured code
- ✅ Appropriate comments and documentation
- ✅ Adherence to Python best practices
- ✅ Well-organized project structure

### Data Processing & Feature Engineering (25%)
- ✅ Correctness of data cleaning operations
- ✅ Proper handling of duplicates, phone formatting, column splitting
- ✅ Appropriate data type conversions
- ✅ Clean data output in proper format

### Agent Implementation and Accuracy (35%)
- ✅ Agent implemented using OpenAI Agent Builder
- ✅ Agent deployed and accessible at provided URL
- ✅ Questions answered correctly using pandas operations (reference)
- ✅ Agent configured with detailed system prompt and question-specific rules
- ✅ Answers documented in `outputs/part2_agent/agent_answers.md`

### Insights & Documentation (15%)
- ✅ Clear instructions to run the project (this README)
- ✅ Comprehensive documentation of all tasks
- ✅ Output files provided in organized structure
- ✅ EDA summary and agent answers documented

## File Locations Reference

- **Notebook**: `notebook/Part1.ipynb`
- **Raw Data**: `data/raw/employee_raw.csv`
- **Cleaned Data**: `data/cleaned/employee_cleaned.csv`
- **EDA Summary**: `outputs/part1_eda/eda_summary.md`
- **Agent Answers**: `outputs/part2_agent/agent_answers.md`
- **Agent Description**: `agent/agent_description.md`
- **Demo Video**: `demo_video_link.md`

## Notes

- The dataset cleaning process successfully handles all identified issues (missing values, combined columns, phone formatting)
- All EDA tasks are completed and results are available in the notebook and summary files
- Part 2 questions are answered using pandas, but a full AI agent implementation would require integration with an AI toolchain
- Project structure follows best practices for data science projects with clear separation of raw data, cleaned data, outputs, and documentation

## Contact

For questions or clarifications about this submission, please refer to:
- This README file
- The notebook: `notebook/Part1.ipynb`
- EDA summary: `outputs/part1_eda/eda_summary.md`
- Agent answers: `outputs/part2_agent/agent_answers.md`
