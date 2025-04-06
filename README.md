# Exploratory-Data-Analysis-on-Titanic-Dataset-using-SQL
# 🚢 Titanic Dataset EDA using SQL

Welcome to my SQL-based Exploratory Data Analysis (EDA) project on the iconic **Titanic dataset**. In this project, I used SQL to uncover patterns and insights related to passenger survival, demographics, class, and more.

---

## 📌 Table of Contents

- [Overview](#-project-overview)
- [Technologies Used](#-technologies-used)
- [Dataset Info](#-dataset-info)
- [Objectives](#-project-objectives)
- [Sample Queries](#-sample-sql-queries)
- [Insights](#-key-insights)
- [Learnings](#-what-i-learned)
- [Future Scope](#-future-improvements)

---

## 📖 Project Overview

This project focuses on analyzing the Titanic dataset using **Structured Query Language (SQL)**. The goal is to extract meaningful patterns and gain insights into survival rates based on various features such as gender, class, and embarkation port.

---

## 🛠 Technologies Used

- **SQL** (MySQL / PostgreSQL / SQLite)
- **Titanic Dataset** – [Kaggle Source](https://www.kaggle.com/c/titanic/data)
- **SQL Editor** – DB Browser / MySQL Workbench / pgAdmin

---

## 📁 Dataset Info

Key columns used from the dataset:
- `PassengerId`
- `Survived` (0 = No, 1 = Yes)
- `Pclass` (1st, 2nd, 3rd class)
- `Name`, `Sex`, `Age`
- `SibSp`, `Parch` (family aboard)
- `Ticket`, `Fare`
- `Cabin`, `Embarked` (C, Q, S)

---

## 🎯 Project Objectives

- Clean and explore Titanic data using SQL queries
- Analyze survival rates based on:
  - Gender
  - Age
  - Passenger Class
  - Embarkation Port
  - Family Size
- Derive useful patterns using SQL clauses like `GROUP BY`, `ORDER BY`, `CASE`, and `JOIN`

---

## 💻 Sample SQL Queries

```sql
-- Survival Rate by Gender
SELECT Sex, 
       COUNT(*) AS Total, 
       SUM(Survived) AS Survived, 
       ROUND(SUM(Survived)*100.0/COUNT(*), 2) AS SurvivalRate
FROM Titanic
GROUP BY Sex;

-- Average Age of Survivors and Non-Survivors
SELECT Survived, 
       ROUND(AVG(Age), 2) AS AverageAge
FROM Titanic
GROUP BY Survived;

-- Survival Rate by Passenger Class
SELECT Pclass, 
       COUNT(*) AS Total, 
       SUM(Survived) AS Survived, 
       ROUND(SUM(Survived)*100.0/COUNT(*), 2) AS SurvivalRate
FROM Titanic
GROUP BY Pclass;
