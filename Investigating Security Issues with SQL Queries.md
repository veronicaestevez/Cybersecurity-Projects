# 🔍 Investigating Security Issues with SQL Queries 🛡️

## Project Overview: 

Welcome to this project where I step into the shoes of a security professional working for a large organization! 🏢 
My goal? To dive deep into the world of data analysis and cybersecurity 🖥️, uncovering potential threats to the company’s system. 
Let's take a closer look at how I used SQL to solve real-world security problems. 🚨

## 🚨 The Scenario
As a security expert, I was tasked with investigating unusual login activity within the organization. 🔐 
Recent reports flagged suspicious login attempts, raising concerns about unauthorized access. 
To tackle this issue, I used SQL to analyze data from the `employees` and `log_in_attempts` tables. 
By applying precise filters, I could pinpoint patterns that indicated potential security threats. ⚠️

## 💡 What I Did:

**SQL Data Retrieval 🗄️:** Wrote SQL queries to extract records of interest, filtering data from two key tables: `employees` and 
`log_in_attempts`. This allowed me to focus on suspicious behavior.

**Security Investigation 🔍:** Used data analysis to identify unusual patterns in login activity and detect any unauthorized access.

**Protecting Data 🛡️:** By isolating key security risks, I was able to help secure the organization’s systems and prevent future breaches.

## ✨ Key Skills Demonstrated:
**🖥️ SQL Mastery:** Used advanced queries to filter and retrieve critical data efficiently.

**🔍 Data Analysis:** Investigated login trends to identify possible security threats.

**🛡️ Security Best Practices:** Demonstrated the importance of proactive threat detection in protecting sensitive information.

💼 This project showcases the intersection of data analysis and cybersecurity, leveraging SQL as a powerful tool for keeping 
systems secure. By diving into the data, I was able to uncover insights and protect the organization from potential threats. 🎯
The following steps provide examples of how I used SQL with filters to perform security-related tasks:

### Task 1. Retrieve after hours failed login attempts

A possible security issue took place after business hours (past 18:00). 🚨 To investigate, I needed to focus on all failed login attempts during this timeframe. The SQL query below shows how I filtered for these after-hours failures. 👇

![image](https://github.com/user-attachments/assets/5e34add0-c646-4471-8e4f-e70d1876bc45)

In the screenshot above, you’ll see two parts: my SQL query and a snippet of the output. 📊 This query focuses on failed login attempts made after 18:00. I started by selecting all records from the `log_in_attempts` table. From there, I added a `WHERE` clause, combined with an `AND` operator, to narrow down the results to unsuccessful login attempts after business hours. The first condition, `login_time > '18:00'`, filters out attempts made after 18:00, and the second condition, `success = 0`, ensures only failed attempts are included. ✅

**NOTE:** For the second condition I could also input `success = FALSE`, hence **TRUE** is represented as `1`, and **FALSE** represented as `0` in the success column.

### Task 2. Retrieve login attempts on specific dates

On 2022-05-09, a suspicious event was detected. 🚨 I needed to investigate any login activity that occurred on that date or the day prior. The SQL query below shows how I filtered for login attempts on these specific dates. 👇

![image](https://github.com/user-attachments/assets/1dc09109-84a0-407e-948c-c72737ff27a5)

The first part of the screenshot is my query, and the second part is a portion of the output. This query retrieves all login attempts from either **2022-05-09** or the previous day, **2022-05-08**. I began by selecting all records from the `log_in_attempts table`. Then, I applied a `WHERE` clause with an `OR` operator to filter the results to include only those attempts from the specified dates. The first condition, `login_date = '2022-05-09'`, targets logins on **2022-05-09**, while the second condition, `login_date = '2022-05-08'`, focuses on logins from **2022-05-08**. 

### Task 3. Retrieve login attempts outside of Mexico

While diving into the login attempt data for the organization, I noticed some unusual activity from locations outside of Mexico. 🌍 These attempts might indicate potential security concerns and warrant further investigation.

Check out the SQL query below that I used to isolate these international login attempts. 👇

![image](https://github.com/user-attachments/assets/5a236dfb-a606-48a5-ad93-42d47c9c1265)

In the screenshot, you’ll find my SQL query at the top and a preview of the results below. This query is set up to pull login attempts from anywhere except Mexico. 🌍 I started by pulling all the data from the `log_in_attempts table`. Then, I filtered out entries for Mexico using `NOT` and `LIKE` with `MEX%` to catch both **"MEX"** and **"MEXICO"** entries. The `%` symbol in `LIKE` works like a wildcard, letting me match any additional characters.

### Task 4. Retrieve employees in Marketing

My team needs to upgrade computers for certain employees in the Marketing department. 💻 To determine which machines require updating, I ran a SQL query to find the right information.

Check out the code below, which shows how I filtered for employee computers in the Marketing department located in the East building. 🏢🔍

![image](https://github.com/user-attachments/assets/e4424d9f-3a40-4b15-9dea-947e7f0df57f)

In the screenshot, you'll see my SQL query at the top and a glimpse of the results below. 📊 This query retrieves all employees working in the Marketing department who are based in the East building. 🏢 I began by selecting all data from the `employees` table. Then, I applied a `WHERE` clause with `AND` to filter out employees who are in Marketing and located in the East building. I used `LIKE 'East%'` to capture all office numbers in the East building, as the office column includes both the building name and specific office numbers. The first condition `department = 'Marketing'` targets those in Marketing, while the second condition office `LIKE 'East%'` pinpoints those in the East building.

### Task 5. Retrieve employees in Finance or Sales

We also need to update the machines for employees in the Finance and Sales departments. 💼🔧 Since these updates require different security patches, I needed to focus on employees from just these two departments.

Below is the SQL query I used to filter for employee machines specifically from the Finance and Sales departments. 📈💻

![image](https://github.com/user-attachments/assets/40b7a6ac-afcc-450e-9391-33965a0c66d3)

In the screenshot, you'll find my SQL query at the top and a snippet of the results below. 📊 This query pulls up all employees working in either the **Finance** or **Sales** departments. 💼 I started by selecting all records from the `employees` table. Then, I used a `WHERE` clause with `OR` to capture employees from both departments. The OR operator ensures that the query includes employees from either department, not just one. The first condition, `department = 'Finance'`, filters for those in **Finance**, while the second condition, `department = 'Sales'`, targets those in **Sales**.

### Task 6. Retrieve all employees not in IT

My team needs to carry out one final security update for employees outside the Information Technology department. 🛡️🔧 To proceed, I needed to gather details on these employees first.

The following shows how I crafted a SQL query to filter for employee machines from everyone who isn’t in the IT department. 💻

![image](https://github.com/user-attachments/assets/067aedc1-5272-4498-b223-729d210f10e1)

In the screenshot, you’ll see my SQL query at the top and a snippet of the results below. 📊 This query retrieves all employees who are not in the Information Technology department. 🚫 I began by pulling all records from the `employees` table, then applied a `WHERE` clause with `NOT` to exclude those in the **IT** department.

## Summary

I utilized SQL filters to extract detailed information about login attempts and employee machines. 🖥️🔍 Working with two tables, `log_in_attempts` and `employees`, I applied various operators — `AND`, `OR`, and `NOT` — to pinpoint exactly what was needed for each task. Additionally, I used the `LIKE` operator and the `%` wildcard to match specific patterns in the data.



















