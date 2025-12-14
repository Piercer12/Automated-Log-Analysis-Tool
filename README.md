# Automated-Log-Analysis-Tool
A Python automation script that parses system logs, tracks user activity, and generates CSV reports using Regex.

# 📊 Automated System Log Analysis & Reporting Tool

## 🚀 Project Overview
This Python-based automation tool is designed to parse complex system log files (`syslog`), extract critical operational data, and generate structured reports. It was built to solve the common IT support challenge of manually auditing massive log files to identify frequent error patterns and user activity.

## 🎯 Key Features
* **Regex Pattern Matching:** Utilizes advanced Regular Expressions (`re` module) to parse unstructured log lines and extract components (Error Messages, Usernames, Log Types).
* **Data Aggregation:** Dynamically counts error frequencies and tracks user actions (INFO vs. ERROR) using Python dictionaries.
* **Intelligent Sorting:** Automatically ranks errors from most frequent to least frequent for easy prioritization.
* **Automated Reporting:** Exports processed data into two clean CSV files (`error_message.csv` and `user_statistics.csv`) ready for stakeholder reporting.

## 🛠️ Technologies Used
* **Language:** Python 3
* **Modules:** `re` (Regex), `csv`, `operator`, `sys`
* **Skills Applied:** String manipulation, File I/O, Data Sorting, Dictionary manipulation.

## 📂 File Structure
* `log_analysis.py`: The main script containing the logic.
* `syslog.log`: A sample log file used for testing and demonstration.
* `user_statistics.csv`: Output report showing usage data per user.
* `error_message.csv`: Output report showing the hierarchy of system errors.

## ⚙️ How It Works
The script iterates through the log file and applies the following logic:
1.  **Ingest:** Reads the raw log file line-by-line.
2.  **Parse:** Applies the regex pattern `r"ticky: ([\w+]*):? ([\w' ]*)[\[[#0-9]*\]?]? ?\((.*)\)$"` to separate data.
3.  **Process:**
    * If the log entry is an **ERROR**, it updates the global error count.
    * It simultaneously updates the specific user's activity log.
4.  **Export:** Writes the organized data to CSV format.

## 📈 Sample Output
**error_message.csv**
```csv
Error, Count
Timeout while retrieving information, 15
The ticket was modified while updating, 9
Connection to DB failed, 4
