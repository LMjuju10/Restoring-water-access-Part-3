# Restoring-water-access-Part-3
# Weaving the Data Threads of Maji Ndogo’s Narrative
---

## Project Overview: Results of Audit on Maji Ndogo Water Project

This project documents the findings of an independent audit on the **Maji Ndogo water project**. Our primary focus was on the database recording water sources across the country, an audit initiated due to inconsistencies identified by Chidi Kunto and his team.

The audit's objective was to assess the **integrity** and **accuracy** of the data within the database. This involved verifying that the data was accurate and had not been tampered with, ensuring its reliability for decision-making and governance.

After a rigorous examination of the database records and data entry/modification procedures, we confirmed that most of the data aligns with good governance and data-driven decision-making principles.

However, we did identify instances of **tampered data** requiring immediate attention. Re-examined records are attached for your review.

---

## Data Sources

* `md_water_services`

---

## Data Analysis

### 1. ERD (Entity-Relationship Diagram)

To effectively integrate the auditor's report, understanding the database structure is crucial, as it dictates how we access multiple tables. First, we need to grasp the relationships between tables, which will guide our data retrieval. Please refer to the ERD for the `md_water_services` database.  

![Md Water Services ERD](https://www.example.com/)

#### Observations:

The **`visits` table serves as the central table**. While `location_id`, `source_id`, and `assigned_employee_id` are **primary keys** in their respective tables, they act as **foreign keys** within the `visits` table. These relationships are predominantly **one-to-many**.

For example, for each unique `location` in the `location` table, there can be multiple corresponding records in the `visits` table, detailing various visit times. This clearly illustrates a **one-to-many relationship**.

### 2. Integrating Auditor’s Report

The additional auditor's report table, containing the audit findings, was successfully loaded into our SQL environment.

### 3. Linking Records to Employees

Upon investigating the potential origins of these errors, we discovered that employees at certain locations had incorrectly assigned scores, leading to these flawed records in our results.

We believe there are two main reasons for these discrepancies:

* **Human error:** It's expected that employees, being human, will occasionally make mistakes.
* **Intentional misconduct:** Unfortunately, the alternative is that someone deliberately assigned incorrect scores.

In either scenario, employees are the source of these errors. We utilized **JOINs** and **CTEs** (Common Table Expressions) to conduct further investigations and retrieve the necessary information.

### 4. Gathering Evidence

While all employees make mistakes, a corrupt individual would likely exhibit a significantly higher number of "mistakes" than the average. We identified employees who made more than the average number of mistakes and compiled a "Suspect List." This list, combined with information recorded in the `statements` column of the Auditor's report, helped us gather concrete evidence.

Considering both the frequency of mistakes and these incriminating statements provided a reliable basis for our conclusions.

---

## Insights

Our investigation identified four key suspects who were found to be the most corrupt: **Zuriel Matembo, Malachi Mavuso, Bello Azibo, and Lalitha Kaburi**.

The evidence supporting this conclusion is twofold:

1.  They all consistently made **more mistakes than their peers on average**.
2.  They are the **only individuals against whom incriminating statements were made** in the auditor's report.
