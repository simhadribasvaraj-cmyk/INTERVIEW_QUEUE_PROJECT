# Walk-In Interview Queue Management System

## 📌 Project Overview

The **Walk-In Interview Queue Management System** is a MySQL database
project designed to organize and manage candidates attending walk-in
interviews.

In traditional walk-in interviews, candidates may spend hours waiting
without knowing their token status or estimated interview time. This
project uses a relational database to maintain candidate registrations,
interview tokens, queue positions, interviewer assignments, and
interview outcomes.

The goal is to make the recruitment process more organized and help HR
teams manage candidates efficiently.

## 🎯 Objectives

-   Store and manage candidate registration details.
-   Maintain unique interview token numbers.
-   Track candidate queue positions and interview status.
-   Assign candidates to interviewers.
-   Estimate waiting time based on queue position and average interview
    duration.
-   Generate recruitment and HR reports using SQL queries.

## 🛠️ Technologies Used

-   **Database:** MySQL
-   **Language:** SQL
-   **Concepts:** RDBMS, primary keys, foreign keys, JOINs, aggregate
    functions, filtering, sorting, and date-time functions.

## 🗂️ Database Structure

The project contains three main tables.

### 1. Candidates

Stores candidate registration information.

  Column                Description
  --------------------- ----------------------------------
  `candidate_id`        Primary key; unique candidate ID
  `candidate_name`      Candidate's name
  `phone`               Contact number
  `email`               Email address
  `job_role`            Role applied for
  `experience_years`    Years of experience
  `registration_time`   Registration date and time

### 2. Interviewers

Stores interviewer information.

  -----------------------------------------------------------------------
  Column                              Description
  ----------------------------------- -----------------------------------
  `interviewer_id`                    Primary key; unique interviewer ID

  `interviewer_name`                  Interviewer's name

  `department`                        Interviewer's department

  `average_interview_minutes`         Estimated interview duration in
                                      minutes
  -----------------------------------------------------------------------

### 3. Interview Queue

Tracks interview tokens, assignments, and candidate status.

  Column              Description
  ------------------- --------------------------------------
  `queue_id`          Primary key; unique queue record ID
  `candidate_id`      Foreign key referencing Candidates
  `interviewer_id`    Foreign key referencing Interviewers
  `token_number`      Unique interview token
  `queue_position`    Candidate's position in the queue
  `status`            Current interview status
  `interview_start`   Interview start time
  `interview_end`     Interview end time

### Relationships

-   One candidate can have multiple queue records.
-   One interviewer can be assigned multiple queue records.
-   Each queue record references one candidate and one interviewer.

## ⚙️ Key Features

1.  **Candidate Registration:** Store candidate details in the database.
2.  **Token Management:** Maintain unique tokens for interview tracking.
3.  **Queue Management:** Display waiting candidates in queue order.
4.  **Interview Status Tracking:** Track statuses such as Waiting, In
    Interview, Selected, Rejected, Absent, and Completed.
5.  **Waiting-Time Estimation:** Calculate estimated waiting time using
    queue position and average interview duration.
6.  **HR Reporting:** Summarize candidates by status and analyze
    interviewer workloads.

## 💻 SQL Concepts Demonstrated

-   `CREATE DATABASE` and `CREATE TABLE`
-   `INSERT`, `SELECT`, and `UPDATE`
-   `WHERE`, `ORDER BY`, and `LIMIT`
-   `INNER JOIN` and `LEFT JOIN`
-   `GROUP BY`, `COUNT()`, `SUM()`, and `CASE`
-   Primary key and foreign key constraints
-   Date-time functions and calculated columns

## 🚀 How to Run the Project

### Prerequisites

-   MySQL Server installed on your computer.
-   MySQL Workbench or MySQL Command Line Client.

### Steps

1.  Clone or download this repository:

    ``` bash
    git clone https://github.com/YOUR-USERNAME/walk-in-interview-queue-management.git
    ```

2.  Open MySQL Workbench or the MySQL command line.

3.  Create the database:

    ``` sql
    CREATE DATABASE interview_queue;
    USE interview_queue;
    ```

4.  Run the SQL scripts in this repository to create the three tables.

5.  Insert the sample candidate and interviewer records.

6.  Execute the queries to test queue tracking, status updates, and HR
    reports.

## ⏱️ Waiting-Time Calculation

A basic estimated waiting-time formula is:

`Estimated Wait = (Queue Position - 1) × Average Interview Duration`

**Example:** If a candidate is in position 4 and each interview takes an
average of 20 minutes:

`Estimated Wait = (4 - 1) × 20 = 60 minutes`

This is a simplified estimate. Actual waiting times may vary depending
on interview duration, delays, and interviewer availability.

## 📊 Sample Use Cases

-   Finding all candidates currently waiting.
-   Identifying the next candidate to be interviewed.
-   Counting candidates by interview status.
-   Checking interviewer workload.
-   Estimating candidate waiting times.
-   Reviewing interview outcomes.

## 🔮 Future Enhancements

-   Develop an HR dashboard for queue monitoring.
-   Build a web interface using Python or Java.
-   Allow candidates to check their token status online.
-   Add automated SMS or email notifications.
-   Generate daily recruitment reports.
-   Improve waiting-time estimates using actual interview durations.

## 📚 Learning Outcomes

This project demonstrates practical use of relational database design,
SQL query writing, data relationships, queue management logic, and
business reporting.

## 👨‍💻 Author

**Your Name**

-   GitHub: `https://github.com/YOUR-USERNAME`

## 📄 License

This project is intended for educational and portfolio purposes. Add a
license if you plan to distribute it publicly.
