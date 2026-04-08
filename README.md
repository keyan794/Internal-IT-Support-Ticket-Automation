# 🧠 AI-Powered IT Support Ticket Automation (n8n)

## 📌 Overview

This project is an **end-to-end automated IT support ticket processing system** built using **n8n**.
It reads raw ticket data from a CSV file, validates, cleans, deduplicates, enriches, and generates structured outputs along with analytics.

The workflow simulates a **real-world IT helpdesk automation pipeline**.

---

## 🚀 Features

* 📂 **CSV Ingestion**

  * Reads raw ticket data from local storage

* 🧹 **Data Normalization**

  * Cleans and standardizes:

    * Issue Type
    * Priority
    * Email

* ✅ **Validation**

  * Email format validation (Regex)
  * Priority validation (High / Medium / Low)

* 🔁 **Deduplication Logic**

  * Removes duplicate tickets within **24-hour window**
  * Based on:

    * Email + Issue Type + Timestamp

* 🆔 **Ticket ID Generation**

  * Unique ID for every valid ticket

* 🧑‍💻 **Team Routing**

  * Automatically assigns tickets:

    * Network (WiFi)
    * IT Support (Login)
    * Applications (Software)
    * Infrastructure (Hardware)
    * General (Other)

* ⏱ **SLA Calculation**

  * High → 4 hours
  * Medium → 24 hours
  * Low → 72 hours

* 📊 **Summary Reporting**

  * Total tickets received
  * Processed tickets
  * Rejected tickets
  * Team-wise distribution

* ⚠️ **Error Handling**

  * Captures file storage failures

---

## 🏗 Workflow Architecture

```
Read CSV
   ↓
Capture Total Count
   ↓
Normalize Data
   ↓
Validation (Email & Priority)
   ↓
Generate Ticket ID
   ↓
Deduplication
   ↓
Team Assignment
   ↓
SLA Calculation
   ↓
├── Processed Tickets → CSV
├── Rejected Tickets → CSV
└── Summary Report → CSV
```

---

## 📁 Output Files

| File                    | Description                            |
| ----------------------- | -------------------------------------- |
| `processed_tickets.csv` | Cleaned and enriched valid tickets     |
| `rejected_tickets.csv`  | Invalid tickets with rejection reasons |
| `summary_report.csv`    | Aggregated metrics                     |
| `storage_errors.csv`    | File write errors (if any)             |

---

## 📊 Example Output

### Processed Tickets

```
ticket_id,issueType,priority,team,sla_deadline
TICK-...,wifi,high,Network,...
TICK-...,login,medium,IT Support,...
```

### Summary Report

```
metric,value
total_received,6
processed,4
rejected,1
Network,1
IT Support,1
Applications,1
Infrastructure,0
General,1
```

---

## 🛠 Tech Stack

* **n8n** (Workflow Automation)
* **JavaScript (Code Nodes)** for logic
* **Regex** for validation
* **CSV Processing**

---

## 🧠 Key Concepts Demonstrated

* Data Pipeline Design
* ETL (Extract, Transform, Load)
* Data Cleaning & Validation
* Deduplication Strategy
* SLA Management Logic
* Workflow Automation
* Error Handling & Logging

---

## 📈 Real-World Use Cases

* IT Helpdesk Automation
* Customer Support Ticketing Systems
* Internal Ops Automation
* Workflow Orchestration Systems

---

## ⚙️ How to Run

1. Install n8n
2. Import the workflow JSON
3. Place your CSV file at:

   ```
   C:/Users/Karthikeyan/.n8n-files/tickets.csv
   ```
4. Click **Execute Workflow**

---

## 🔮 Future Improvements

* 🔗 Integrate with ticketing tools (Jira / ServiceNow)
* 🤖 Add ML-based classification
* 📩 Email/Slack notifications
* 🌐 API trigger instead of manual trigger
* 📊 Dashboard (Power BI / Streamlit)

---

## 👨‍💻 Author

**Karthikeyan**
Aspiring Data Scientist | AI & Automation Enthusiast

---

## ⭐ If you like this project

Give it a ⭐ on GitHub!
