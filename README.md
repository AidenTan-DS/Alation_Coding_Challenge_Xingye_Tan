# Alation Coding Challenge: AI and Data Engineering

## Overview

This project implements data preprocessing, exploratory data analysis, and an AI agent for HR data analysis.

## Project Structure

```
Alation_Coding_Challenge_Xingye_Tan/
│
├── README.md
├── requirements.txt
│
├── notebook/
│   └── Part1.ipynb                     # Data cleaning, EDA, and analysis
│
├── data/
│   ├── raw/
│   │   └── employee_raw.csv
│   └── cleaned/
│       └── employee_cleaned.csv
│
├── outputs/
│   ├── part1_eda/                      # EDA visualizations
│   │   ├── total_salary_by_department.png
│   │   ├── performance_distribution_by_department.png
│   │   └── employees_by_region.png
│   │
│   └── part2_agent/                    # Agent question answers
│       ├── q1_avg_salary_by_region.jpg
│       ├── q2_top_performers_by_department.jpg
│       └── q3_most_tenured_by_department.jpg
│
└── agent/
    └── agent_description.md
```

## Part 1: Data Preprocessing and EDA

### Data Cleaning Tasks
- Removed duplicates based on Email column
- Formatted phone numbers to standard US format: (XXX) XXX-XXXX
- Split Department_Region into Department and Region columns
- Rounded Salary to integers

### EDA Results
- Descriptive statistics for all columns
- Total salary by department
- Performance distribution by department
- Employee distribution by region

All results and visualizations are in `notebook/Part1.ipynb` and `outputs/part1_eda/`.

## Part 2: HR AI Agent

### Agent Access
**URL**: https://alation-agent-keao.vercel.app/

### Implementation
- **Platform**: OpenAI Agent Builder
- **Model**: gpt-4o-mini
- **Tool**: Code Interpreter (with cleaned CSV dataset)
- **Status**: Live and deployed

### Questions Answered
1. Which Region(s) offer the highest salary to employees on average?
2. Show me a list of top performers in each department?
3. Show me a list of the most tenured employees in each department?

Answers are available in the agent interface and visualized in `outputs/part2_agent/`.

For detailed agent implementation, see `agent/agent_description.md`.

## How to Run

### Getting Started

1. **Clone or download the project**:
   ```bash
   # Option 1: Clone from GitHub (if available)
   git clone <repository-url>
   cd Alation_Coding_Challenge_Xingye_Tan
   
   # Option 2: Download as ZIP and extract
   # Then navigate to the project directory
   cd Alation_Coding_Challenge_Xingye_Tan
   ```

2. **Verify data files**:
   - The raw data file should be located at: `data/raw/employee_raw.csv`
   - If the file is missing, ensure you have downloaded/cloned the complete project
   - The cleaned data will be generated when you run the notebook

### Prerequisites

1. **Install Python 3.x** (if not already installed)

2. **Install required packages**:
   ```bash
   pip install -r requirements.txt
   ```
   
   This will install: pandas, jupyter, matplotlib, seaborn

### Part 1: Data Preprocessing and EDA

1. **Start Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

2. **Open the notebook**:
   - Navigate to `notebook/Part1.ipynb`
   - Or run directly: `jupyter notebook notebook/Part1.ipynb`

3. **Run all cells**:
   - Execute cells sequentially (Shift + Enter)
   - Or use menu: Cell → Run All

4. **Check outputs**:
   - Cleaned data saved to: `data/cleaned/employee_cleaned.csv`
   - EDA visualizations displayed in notebook
   - Visualizations also saved in: `outputs/part1_eda/`

### Part 2: HR AI Agent

**Access the deployed agent**:
- **URL**: https://alation-agent-keao.vercel.app/
- Simply open the URL in your browser and start asking questions

**To recreate the agent**:
- See detailed instructions in `agent/agent_description.md`

## Submission Artifacts

- ✅ Instructions on how to run the project
- ✅ Cleaned output data: `data/cleaned/employee_cleaned.csv`
- ✅ EDA outputs: `outputs/part1_eda/` (visualizations)
- ✅ Agent access: https://alation-agent-keao.vercel.app/
- ✅ Agent recreation instructions: `agent/agent_description.md`
- ✅ Part 2 answers: `outputs/part2_agent/` (visualizations)
