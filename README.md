# Physical Activity & BMI Trends in Norway (1998-2025)

## Project Overview

This project was created to improve my skills in data cleaning and data visualization, and to get more experience with real-world data.

The objective was to explore long-term trends in physical activity and Body Mass Index (BMI) in Norway using publicly available data from Statistisk sentralbyrå (SSB).

The project focused on transforming a complex public dataset into an interactive Power BI dashboard through data cleaning, feature engineering, and data visualization.

---

# Project Objectives

The objectives of this project were to:

- Investigate how physical activity levels have changed in Norway between 1998 and 2025.
- Explore trends in BMI categories across different age groups.
- Compare lifestyle indicators between age groups.
- Practice data cleaning and transformation using Power Query.
- Build interactive Power BI dashboards to support exploratory analysis.

---

# Dataset

- **Source:** Statistisk sentralbyrå (SSB) https://www.ssb.no/en/statbank/table/06181
- **Dataset:** Table 06181 – Lifestyle habits (percent), by living habit, year and age
- **Format:** Excel (.xlsx)
- **Data Type:** Public survey data

The dataset contains annual survey data covering physical activity, BMI categories, sedentary behaviour and other lifestyle indicators across multiple age groups.

---

# Data Cleaning

The original dataset required a lot preprocessing before analysis.

The data preparation process included:

- Removing metadata and unnecessary rows
- Unpivoting the dataset into a normalized table
- Renaming and cleaning columns
- Correcting data types
- Removing invalid records
- Creating category fields
- Creating a custom Age Order column for proper visualization sorting

  ![Data Cleaning](Images/datacleaning_process.png)


---

# Dashboards

## 1. Physical Activity Trends

An interactive dashboard was created to explore how different exercise habits have changed over time.

Users can:

- Select exercise indicators
- Compare age groups
- Explore long-term trends
- View dynamic summary statistics

![Physical Activity](Images/exercise_dashboard.png)

---

## 2. BMI Trends

A second dashboard was created using the same layout to investigate BMI categories across different age groups.

Users can compare:

- Underweight
- Overweight
- Obesity
- Age-specific trends
- Changes over time

![BMI Dashboard](Images/bmi_dashboard.png)

---

# Feature Engineering

Several additional fields were created to improve the dashboards.

Power Query:

- Lifestyle Category
- Age Order
- Cleaned dimensions

DAX:

- Selected Indicator
- Highest Percentage
- Lowest Percentage
- Overall Change Since 1998

These measures update dynamically based on the selected lifestyle indicator.

---

# Tools Used

- Power BI Desktop
- Power Query
- DAX
- Microsoft Excel
- Data Cleaning
- Data Visualization

---

# Key Findings

- Weekly exercise generally increased across most age groups.
- The proportion of people reporting that they never exercise has declined over time.
- Younger age groups consistently reported higher levels of physical activity.
- BMI indicators varied considerably across age groups.

---

# Learning Outcomes

Through this project I improved my experience with:

- Power Query
- Data Cleaning
- Data Transformation
- Feature Engineering
- DAX
- Dashboard Design
- Interactive Data Visualization
- Working with real-world public datasets
  
---

# Disclaimer

This project was created as part of my learning journey in Data Analytics.

The primary objective was to practice data cleaning, data transformation, DAX, and interactive dashboard development using a real-world public dataset from Statistisk sentralbyrå (SSB).

The dashboards were developed for educational and portfolio purposes and should not be interpreted as an official statistical analysis.
