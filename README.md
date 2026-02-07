# 🏥 Hospital Management Dashboard (Power BI)

A comprehensive **Hospital Management Dashboard** built using **Power BI** to monitor appointments, patients, doctors and billing performance.
This project provides hospital management with actionable insights through interactive visuals and well-structured DAX measures.

---

## 📊 Project Overview

This dashboard helps hospitals:

* Track **patient flow**
* Monitor **appointment statuses**
* Analyze **doctor performance**
* Gain insights into **revenue and billing**
* Improve **operational efficiency**

The report is divided into **four analytical pages**, each focusing on a core hospital function.

---

## 🧮 Core DAX Measures

### Appointment Metrics

```DAX
Total Appointments = COUNT(appointments[appointment_id])

Completed Appointments =
CALCULATE(
    COUNT(appointments[appointment_id]),
    appointments[status] = "Completed"
)

Cancelled Appointments =
CALCULATE(
    COUNT(appointments[appointment_id]),
    appointments[status] = "Cancelled"
)

No Show Appointments =
CALCULATE(
    COUNT(appointments[appointment_id]),
    appointments[status] = "No-show"
)
```

### Revenue Metrics

```DAX
Total Revenue = SUM(billing[amount])

Paid Revenue =
CALCULATE(
    SUM(billing[amount]),
    billing[payment_status] = "Paid"
)

Pending Revenue =
CALCULATE(
    SUM(billing[amount]),
    billing[payment_status] = "Pending"
)
```

### Patient Metrics

```DAX
Total Patients = DISTINCTCOUNT(patients[patient_id])

New Patients =
CALCULATE(
    DISTINCTCOUNT(patients[patient_id]),
    YEAR(patients[registration_date]) = YEAR(TODAY())
)
```

---

## 📄 Dashboard Pages & Features

### 📌 Page 1: Hospital Overview Dashboard

**Goal:** High-level KPIs for management

**Visuals:**

* KPI Cards: Total Patients, Total Appointments, Total Revenue, Completed Appointments
* Donut Chart: Appointment Status Distribution
* Line Chart: Appointments Over Time
* Bar Chart: Revenue by Payment Status

**Slicers:**

* Appointment Date
* Hospital Branch

---

### 📌 Page 2: Patient & Appointment Analysis

**Goal:** Understand patient behavior and appointment patterns

**Visuals:**

* Patient Details Table
* Bar Chart: Appointments by Gender
* Column Chart: Appointments by Status
* Heat Map / Matrix: Appointment Time vs Date

**Slicers:**

* Status
* Gender
* Insurance Provider

---

### 📌 Page 3: Doctor Performance Dashboard

**Goal:** Track doctor workload and efficiency

**DAX Measure**

```DAX
Appointments per Doctor = COUNT(appointments[appointment_id])
```

**Visuals:**

* Bar Chart: Appointments per Doctor
* Stacked Bar: Doctor vs Appointment Status
* Doctor Information Table

**Slicers:**

* Specialization
* Hospital Branch

---

### 📌 Page 4: Billing & Treatment Insights

**Goal:** Revenue and treatment analysis

**Visuals:**

* KPI Cards: Paid Revenue, Pending Revenue
* Bar Chart: Revenue by Treatment Type
* Line Chart: Revenue Trend
* Billing & Treatment Table

**Slicers:**

* Payment Status
* Treatment Type

---

## 🛠 Tools & Technologies

* **Power BI**
* **DAX**
* **Data Modeling**
* **Interactive Visualizations**

---

## 🎯 Key Insights Enabled

* Appointment completion vs no-show tracking
* Revenue leakage through pending payments
* Doctor workload distribution
* Patient demographics and insurance trends
* Treatment-wise revenue contribution

---

## 👩‍💻 Author

**Ismat Khan**

📧 Email: [ismatafrozkhan121@gmail.com](mailto:ismatafrozkhan121@gmail.com)

🔗 GitHub: [https://github.com/ismat-data](https://github.com/ismat-data)

---

## ⭐ If You Like This Project

Give it a ⭐ on GitHub and feel free to fork or suggest improvements!

---
