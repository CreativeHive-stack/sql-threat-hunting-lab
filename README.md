# SQL Threat Hunting & Security Log Analysis Lab

## Overview

This project demonstrates SQL-based threat hunting and security log analysis using MariaDB.

The lab focused on querying authentication logs, employee records, and login attempt data to identify suspicious activity, analyze failed login attempts, and filter organizational security events using SQL queries commonly used in SOC and blue team environments.

---

## Objectives

- Analyze failed login attempts
- Investigate after-hours authentication activity
- Filter login events by country
- Query employee department records
- Practice SQL threat hunting techniques
- Improve database investigation skills

---

## Environment

- Database: MariaDB
- Query Language: SQL
- Lab Type: Security Investigation Lab
- Methodology: Defensive Security / Threat Hunting

---

## Tools Used

- MariaDB
- SQL
- SELECT statements
- WHERE filtering
- Logical operators (AND / OR / NOT)

---

# Task 1 — Retrieve After-Hours Failed Login Attempts

## Purpose

This query was used to identify failed login attempts occurring after business hours.

## SQL Concepts Used

- SELECT
- WHERE
- AND
- Boolean filtering

## Query Logic

The query filtered:
- Login times after 18:00
- Failed login attempts only

### Query Used

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
AND success = FALSE;
```

### Skills Demonstrated

- Authentication log analysis
- SQL filtering
- Threat hunting
- Security event review

---

# Task 2 — Retrieve Login Attempts on Specific Dates

## Purpose

This query investigated login activity on targeted dates for event correlation and authentication review.

## SQL Concepts Used

- SELECT
- WHERE
- OR operator
- Date filtering

## Query Logic

The query filtered login activity occurring on:
- 2022-05-08
- 2022-05-09

### Query Used

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09'
OR login_date = '2022-05-08';
```

### Skills Demonstrated

- Date-based event filtering
- Authentication monitoring
- SQL analysis
- Security investigations

---

# Task 3 — Retrieve Login Attempts Outside of Mexico

## Purpose

This query filtered authentication attempts originating outside a specified geographic region to identify unusual login behavior.

## SQL Concepts Used

- SELECT
- WHERE
- NOT operator
- LIKE operator

## Query Logic

The query filtered all login attempts where the country was not Mexico.

### Query Used

```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

### Skills Demonstrated

- Geographic filtering
- Threat hunting methodology
- SQL logic operations
- Authentication analysis

---

# Task 4 — Retrieve Marketing Employees in East Buildings

## Purpose

This query filtered employee records based on department and office location for administrative investigation purposes.

## SQL Concepts Used

- SELECT
- WHERE
- AND operator
- LIKE operator

## Query Logic

The query filtered:
- Employees in the Marketing department
- Employees located in East offices

### Query Used

```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

### Skills Demonstrated

- Organizational data analysis
- SQL filtering
- Administrative record investigation
- Database analysis

---

# Task 5 — Retrieve Employees in Finance or Sales

## Purpose

This query demonstrated the use of OR conditions to filter multiple departments during organizational data analysis.

## SQL Concepts Used

- SELECT
- WHERE
- OR operator

## Query Logic

The query filtered employees from:
- Finance department
- Sales department

### Query Used

```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

### Skills Demonstrated

- Multi-condition filtering
- SQL query construction
- Employee database analysis
- Security data investigation

---

# Task 6 — Retrieve All Employees Not in IT

## Skills Demonstrated

- SQL querying
- Database investigation
- Security log analysis
- Authentication monitoring
- Threat hunting methodology
- Data filtering
- Boolean logic analysis
- SQL conditional operators
- Organizational data analysis


## Skills Demonstrated

- SQL querying
- Database investigation
- Security log analysis
- Authentication monitoring
- Threat hunting methodology
- Data filtering
- Security event analysis
- MariaDB usage
- Defensive security techniques

---

## Key Takeaways

This lab strengthened foundational SQL investigation and threat hunting skills through hands-on analysis of authentication and employee data commonly encountered in SOC and security analyst environments.

The exercises improved understanding of:
- Authentication event analysis
- Database filtering logic
- Threat hunting methodologies
- Security-focused SQL querying
- Defensive investigation workflows

---

## Disclaimer

This project was conducted in a controlled lab environment for educational and professional portfolio purposes only.

---

## Author

Brandon H. Steeno  
Aspiring Cybersecurity Analyst & SOC Professional
