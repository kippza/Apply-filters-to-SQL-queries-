# Apply Filters to SQL Queries

## Project Description

In this project, I used SQL to investigate a series of suspicious login attempts and identify specific employee machines that require security updates. By applying filters to data from the `log_in_attempts` and `employees` tables, I was able to isolate activity that could signal a security threat and help the IT team take targeted action. This approach supports efforts to maintain system security and data integrity across the organization.

---

## SQL Query Tasks

### ✅ Retrieve After Hours Failed Login Attempts

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00' AND success = 0;
This query filters the log_in_attempts table to show only failed login attempts (success = 0) that occurred after 6:00 PM. This is useful for identifying potentially unauthorized access attempts outside of normal business hours.

✅ Retrieve Login Attempts on Specific Dates
sql
Copy
Edit
SELECT *
FROM log_in_attempts
WHERE login_date IN ('2022-05-08', '2022-05-09');
This query pulls all login activity on May 8 and May 9, 2022. It helps focus the investigation around the time a known suspicious event occurred.

✅ Retrieve Login Attempts Outside of Mexico
sql
Copy
Edit
SELECT *
FROM log_in_attempts
WHERE country NOT LIKE '%MEX%';
This query excludes all login attempts from Mexico by filtering out values like MEX and MEXICO. This helps isolate potentially malicious access originating from other countries.

✅ Retrieve Employees in Marketing (East Building Only)
sql
Copy
Edit
SELECT *
FROM employees
WHERE department LIKE '%Marketing%' AND office LIKE 'East%';
This query returns all employees in the Marketing department whose office location starts with "East" (e.g., East-170). It's used to identify employee machines that need security updates in a specific building.

✅ Retrieve All Employees Not in IT
sql
Copy
Edit
SELECT *
FROM employees
WHERE department NOT LIKE '%Information Technology%';
This query returns employees from all departments except Information Technology, which already had their machines updated. It's used to focus on the remaining users who still need attention.

Summary
Using SQL queries with effective filtering techniques, I was able to assist in detecting suspicious login activity and support the IT team with security maintenance across departments. These queries provided targeted insights into login patterns, geographical anomalies, and department-specific needs—key components of an effective incident response and IT operations strategy.
