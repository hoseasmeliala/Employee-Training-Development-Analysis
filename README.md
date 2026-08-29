# 📊 Employee Training & Development Analytics

### PT PLN Unit Induk Wilayah Nusa Tenggara Timur (UIW NTT)

**HR Analytics | Microsoft Power BI | Power Query | Star Schema | DAX | Data Visualization | Business Intelligence**

> **From Training Data to Decision Support**

---

# 📑 Table of Contents

* [📌 Project Overview](#-project-overview)
* [🏢 Project Context](#-project-context)
* [🎯 Business Problem](#-business-problem)
* [❓ Key Business Questions](#-key-business-questions)
* [🎯 Business Objectives](#-business-objectives)
* [📂 Dataset Information](#-dataset-information)
* [🔍 Scope of Analysis](#-scope-of-analysis)
* [🛠 Tools & Techniques](#-tools--techniques)
* [🔄 Project Workflow](#-project-workflow)
* [🧹 Data Preparation](#-data-preparation)
* [🏗 Data Modeling](#-data-modeling)
* [🧮 KPI & DAX Development](#-kpi--dax-development)
* [📊 Power BI Dashboards](#-power-bi-dashboards)
* [📌 Key Findings](#-key-findings)
* [📈 Business Insights](#-business-insights)
* [🔎 Diagnostic Analysis](#-diagnostic-analysis)
* [💡 Business Recommendations](#-business-recommendations)
* [🎯 Management Action Priority](#-management-action-priority)
* [🎯 Project Outcomes](#-project-outcomes)
* [⚠️ Analytical Limitations](#-analytical-limitations)
* [🚀 Future Improvements](#-future-improvements)
* [📁 Repository Structure](#-repository-structure)
* [📚 Documentation](#-documentation)
* [🛠 Technology Stack](#-technology-stack)
* [👤 About the Author](#-about-the-author)
* [⭐ Project Summary](#-project-summary)

---

# 📌 Project Overview

Employee Training & Development Analytics is an end-to-end HR Analytics project developed to transform employee training records into a structured analytical and decision-support solution.

The project evaluates training performance from multiple dimensions:

* Training Participation
* Learning Effectiveness
* Employee Development
* Training Completion
* Training Investment
* Diagnostic Analysis

Using Microsoft Power BI, Power Query, Star Schema modeling, and DAX measures, this project converts raw training data into management-ready insights that support evidence-based decision making.

---

# 🏢 Project Context

Training and development require organizational resources, employee participation, and financial investment.

Reporting only the number of employees trained does not provide a complete picture of training performance. Therefore, this project evaluates training through multiple analytical perspectives:

Participation → Exposure → Completion → Learning → Investment → Diagnostic Analysis

The project was inspired by experience gained during an HR internship at PT PLN UIW NTT and uses a synthetic dataset created for portfolio purposes.

---

# 🎯 Business Problem

Organizations often track training participation but lack visibility into:

* Training coverage across employees
* Learning improvement after training
* Differences in employee development exposure
* Completion performance
* Training investment distribution
* Areas requiring further investigation

Without an integrated analytical solution, management may struggle to evaluate the effectiveness of training programs.

---

# ❓ Key Business Questions

1. How broadly do training programs reach employees?
2. Do assessment scores improve after training?
3. Which employee groups receive lower training exposure?
4. Which departments show lower completion rates?
5. Where is training investment concentrated?
6. Which areas deserve further investigation?

---

# 🎯 Business Objectives

| Objective        | Description                         |
| ---------------- | ----------------------------------- |
| Participation    | Measure employee training coverage  |
| Effectiveness    | Evaluate learning improvement       |
| Development      | Analyze training exposure           |
| Completion       | Identify completion gaps            |
| Investment       | Analyze training spending           |
| Decision Support | Generate actionable recommendations |

---

# 📂 Dataset Information

### Dataset Components

| Dataset              | Description                    |
| -------------------- | ------------------------------ |
| Employee             | Employee master data           |
| Training Transaction | Training participation records |
| Training Master      | Training program information   |
| Date Dimension       | Time intelligence table        |

### Dataset Scale

* 959 Employees
* ~4,000 Training Records
* 25 Training Programs

---

# 🔍 Scope of Analysis

The project focuses on:

* Participation Analytics
* Learning Analytics
* Development Analytics
* Completion Analytics
* Investment Analytics
* Diagnostic Analytics

---

# 🛠 Tools & Techniques

### Business Intelligence

* Microsoft Power BI

### Data Transformation

* Power Query

### Data Modeling

* Star Schema
* Fact & Dimension Tables

### Data Analysis

* DAX Measures
* KPI Framework

### Visualization

* Interactive Dashboards
* Executive Reporting

---

# 🔄 Project Workflow

```text
Business Understanding
        ↓
Data Preparation
        ↓
Data Modeling
        ↓
KPI & DAX Development
        ↓
Visual Analytics
        ↓
Business Interpretation
        ↓
Diagnostic Analysis
        ↓
Recommendations
```

---

# 🧹 Data Preparation

Data cleaning and transformation were performed using Power Query.

Key activities:

* Data type standardization
* Missing value review
* Category consistency checks
* Identifier validation
* Relationship preparation
* Date dimension creation

📷 Insert Power Query Screenshot Here

---

# 🏗 Data Modeling

The analytical model follows a Star Schema design.

### Fact Table

* FactTraining

### Dimension Tables

* DimEmployee
* DimTraining
* DimDate

Benefits:

* Faster reporting
* Cleaner relationships
* Reusable DAX calculations
* Scalable model design

📷 Insert Data Model Screenshot Here

---

# 🧮 KPI & DAX Development

### Workforce KPIs

* Total Employees
* Training Participants
* Participant Rate

### Development KPIs

* Total Training Hours
* Average Training Hours
* Employees Below 30 Hours

### Effectiveness KPIs

* Average Pre-Training Score
* Average Post-Training Score
* Learning Improvement

### Completion KPIs

* Training Completion Rate

### Investment KPIs

* Total Training Cost
* Cost per Participant

📷 Insert DAX Measures Screenshot Here

---

# 📊 Power BI Dashboards

## 1. Training Overview

Focus:

* Participation
* Coverage
* Workforce Reach
* 
![Training Overview](dashboard/01_training_overview.png)

---

## 2. Training Effectiveness

Focus:

* Pre vs Post Assessment
* Learning Improvement
* Completion Rate

📷 Dashboard Screenshot

---

## 3. Employee Development

Focus:

* Training Exposure
* Development Distribution
* Low Exposure Identification

📷 Dashboard Screenshot

---

## 4. Training Investment

Focus:

* Training Cost
* Cost Distribution
* Spending Trends

📷 Dashboard Screenshot

---

## 5. Executive Summary

Focus:

* High-Level KPIs
* Strategic Insights

📷 Dashboard Screenshot

---

## 6. Training Insights

Focus:

* Diagnostic Analysis
* Drill-Down Investigation

📷 Dashboard Screenshot

---

# 📌 Key Findings

### Training Participation

* 934 employees participated in training
* Participation Rate ≈ 97.4%

### Learning Improvement

* Average Learning Improvement ≈ +7.99 points

### Development Exposure

* 162 employees accumulated less than 30 training hours

### Investment

* K3 / OHS accounts for approximately 52.3% of total training investment

### Completion

* TJSL completion rate ≈ 81.6%

---

# 📈 Business Insights

The analysis indicates that:

* Training coverage is high across the workforce.
* Participation does not automatically mean balanced development.
* Certain employee groups receive lower cumulative training exposure.
* Learning outcomes generally improve after training.
* Training spending is concentrated in specific categories.

---

# 🔎 Diagnostic Analysis

The project extends beyond descriptive reporting.

Diagnostic views include:

* Employees Below 30 Hours by Department
* Employees Below 30 Hours by Job Level
* Completion Rate by Department
* Training Cost vs Learning Improvement

The purpose is to identify areas that require deeper management review.

---

# 💡 Business Recommendations

### 1. Close Training Exposure Gaps

Monitor employees with low cumulative training hours.

### 2. Improve Completion Performance

Review categories and departments with lower completion rates.

### 3. Monitor High-Investment Programs

Evaluate spending alongside learning outcomes.

### 4. Replicate Strong Learning Practices

Analyze characteristics of high-performing programs.

### 5. Establish a Comprehensive Training KPI Framework

Monitor Participation + Exposure + Completion + Learning + Investment simultaneously.

---

# 🎯 Management Action Priority

| Priority | Focus Area        |
| -------- | ----------------- |
| 1        | Training Exposure |
| 2        | Completion        |
| 3        | Investment        |
| 4        | Learning Outcomes |

---

# 🎯 Project Outcomes

This project successfully delivers:

* End-to-End HR Analytics Solution
* Power Query Transformation Workflow
* Star Schema Data Model
* Reusable DAX KPI Layer
* Interactive Power BI Dashboard Suite
* Diagnostic Analysis Framework
* Management-Oriented Recommendations

---

# ⚠️ Analytical Limitations

* Synthetic dataset
* No causal inference
* No financial ROI calculation
* Learning improvement ≠ business impact
* 30-hour threshold is analytical only

---

# 🚀 Future Improvements

Future versions may incorporate:

* Employee Performance Ratings
* Promotion History
* Productivity Metrics
* Training Feedback Data
* Operational KPIs
* Training ROI Analysis

---

# 📁 Repository Structure

```text
Employee-Training-Development-Analytics/
│
├── README.md
│
├── datasets/
│   ├── Employee_Training_Analytics_Dataset.xlsx
│
├── powerbi/
│   ├── Employee_Training_Development_Analytics.pbix
│
├── dashboard_screenshots/
│   ├── 01_training_overview.png
│   ├── 02_training_effectiveness.png
│   ├── 03_employee_development.png
│   ├── 04_training_investment.png
│   ├── 05_executive_summary.png
│   └── 06_training_insights.png
│
├── data_model/
│   └── star_schema_model.png
│
├── power_query/
│   └── power_query_steps.png
│
├── dax/
│   └── dax_measures_examples.png
│
└── documentation/
    └── HR_Analytics_Case_Study.pdf
```

---

# 📚 Documentation

Additional project documentation:

* HR Analytics Case Study
* Data Dictionary
* KPI Definition Guide
* Dashboard Documentation

---

# 🛠 Technology Stack

* Microsoft Power BI
* Power Query
* DAX
* Excel
* Data Modeling
* Business Intelligence

---

# 👤 About the Author

**Hosea Yurie Haganta S Meliala**

Data Analyst Portfolio Project

Former HR Intern — PT PLN UIW NTT

Skills demonstrated:

* Data Cleaning
* Data Transformation
* Data Modeling
* DAX Development
* Dashboard Design
* HR Analytics
* Business Intelligence
* Data Storytelling

---

# ⭐ Project Summary

This project demonstrates how employee training records can be transformed into a comprehensive HR Analytics solution using Microsoft Power BI.

Rather than focusing solely on participation metrics, the analysis evaluates training through multiple dimensions:

Participation → Exposure → Completion → Learning → Investment → Diagnostic Analysis

The result is a management-ready analytical framework that supports data-driven decision making and continuous workforce development.
