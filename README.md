# 📘 README: Understanding Second Normal Form (2NF) in SQL
## 🧠 Project Title
Database Normalization: Achieving Second Normal Form (2NF) Using a Company Employees Table

## 📝 Description
This notebook is part of a database normalization learning series, focusing on the **Second Normal Form (2NF)**. Building on 1NF, it explores how to **eliminate partial dependencies** by organizing non-key attributes into separate, related tables. We use a `Company_employees` table from a restaurant management database as our case study.

| ⚠️ This notebook must be run on a **local machine** with a **MySQL database**. It will **not run on Google Colab** as it connects to the `company_data` database hosted in MySQL Workbench.

## 🎯 Learning Objectives
By the end of this lesson, you will be able to:

- ✅ Understand what qualifies a table to be in **Second Normal Form (2NF)**

- ✅ Identify **partial dependencies** (i.e., non-key attributes that depend on part of a composite key)

- ✅ Normalize data by **splitting tables** to remove partial dependencies

- ✅ Create and populate new relational tables using **SQL DDL** and **DML**

## 📦 Requirements
### 💻 Environment
- **MySQL Workbench**

- **Jupyter Notebook**, **VS Code**, or **any SQL-compatible IDE**

- Python Libraries (for MySQL access in Jupyter):
```
pip install sqlalchemy pymysql pandas
```
### 📁 Database
- Database name: `company_data`

- Main table used: `Company_employees`

## 🧱 Project Structure
```
.
├── 2nf_normalization_notebook.ipynb   # Main instructional notebook
├── README.md                          # Documentation and project guide
├── sql/                               # Optional: SQL scripts for schema and inserts
└── company_data_schema.sql            # Optional: SQL schema file
```
## 🔧 How to Use
1. Open MySQL Workbench and ensure the `company_data` database is active.

2. Launch the notebook in Jupyter or VS Code.

3. Connect to your MySQL server using the following format:
```
   mysql+pymysql://root:<your_password>@localhost:3306/company_data
```
4. Run through the notebook step-by-step to:

    - Inspect the unnormalized structure
    
    - Identify partial dependencies
    
    - Split attributes into new tables
    
    - Query normalized tables

## 🧪 Example of 2NF Transformation
**❌ Not in 2NF (violates due to partial dependency):**
```
| EmployeeID | JobCode | JobTitle  | Salary |
| ---------- | ------- | --------- | ------ |
| 1          | J001    | Manager   | 1000   |
| 2          | J002    | Developer | 900    |
```

`JobTitle` and `Salary` depend only on `JobCode`, not the full composite key.

**✅ Normalized to 2NF:**
**Table 1: Employee_roles**
```
| EmployeeID | JobCode |
| ---------- | ------- |
| 1          | J001    |
| 2          | J002    |
```
**Table 2: Jobs**
```
| EmployeeID | JobCode |
| ---------- | ------- |
| 1          | J001    |
| 2          | J002    |
```

## 📚 Key Concepts in 2NF
- **1NF compliance is a prerequisite**

- **No partial dependency** of non-prime attributes on part of the composite primary key

- Promotes **modularity** and **reusability** of data structures

## 📧 Contact
**Author**: Ibrahim Ambale
📍 Nairobi, Kenya
🔗 LinkedIn: [Ibrahim Ambale](https://linkedin.com/in/ibrahim-ambale/)


