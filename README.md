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
## Screenshots
<img width="928" height="781" alt="Task 1  Retrieve after hours failed login attempts Pt 2" src="https://github.com/user-attachments/assets/7d1380f5-cd17-46b3-87a3-68e0c6053b01" />
<img width="920" height="524" alt="Task 1  Retrieve after hours failed login attempts Pt 1 " src="https://github.com/user-attachments/assets/2029d9fa-7fa1-46b0-b33f-fb750cbf85ea" />
<img width="933" height="793" alt="Task 1  Retrieve after hours failed login attempts Pt 3" src="https://github.com/user-attachments/assets/d8193aed-5d15-4be0-8b1f-9d9a54545645" />

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
## Screenshots
<img width="928" height="793" alt="Task 2  Retrieve login attempts on specific dates" src="https://github.com/user-attachments/assets/f5cbbf0d-92f7-4455-adff-4cc314aafaa4" />
<img width="928" height="749" alt="Task 2  Retrieve login attempts on specific dates Pt 2" src="https://github.com/user-attachments/assets/a9e6a69e-cb2c-4626-9d1c-c257c106c61d" />

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
## Screenshots
<img width="928" height="745" alt="Task 3  Retrieve login attempts outside of Mexico Pt 2" src="https://github.com/user-attachments/assets/a3a61f34-b718-4c83-b600-016a24801815" />
<img width="931" height="801" alt="Task 3  Retrieve login attempts outside of Mexico Pt 1" src="https://github.com/user-attachments/assets/160367ff-5875-46fd-b4b3-464127e87024" />

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
## Screenshot
<img width="926" height="491" alt="Task 4  Retrieve employees in Marketing East buidling specific" src="https://github.com/user-attachments/assets/5e1b4387-ee06-4eef-abfd-0298c21b0b38" />

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
## Screenshots
<img width="925" height="798" alt="Task 5  Retrieve employees in Finance or Sales Pt 1" src="https://github.com/user-attachments/assets/abb327f3-ba56-4d26-b26d-32b810a2d631" />
<img width="923" height="798" alt="Task 5  Retrieve employees in Finance or Sales Pt 2" src="https://github.com/user-attachments/assets/d4147f7e-2ffb-4320-ae2c-1c6724e0936b" />

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
## Screenshots
<img width="928" height="739" alt="Task 6  Retrieve all employees not in IT Pt 2" src="https://github.com/user-attachments/assets/f8dcab93-b876-41de-9997-6cf1310b19d0" />
<img width="925" height="798" alt="Task 6  Retrieve all employees not in IT Pt 1" src="https://github.com/user-attachments/assets/9ec2a782-f4f8-43d5-b1bd-da34ff012754" />

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
