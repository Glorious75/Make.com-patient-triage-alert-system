# 🚨 Patient Triage Alert System

**Make.com automation · Built by Gloria Njorteah · April 2026**

A 3-scenario automation that cuts clinical triage response time from **90 minutes to under 2 minutes**. Patient intake forms are automatically captured in Airtable, triaged by urgency level, and escalated via Slack — with zero manual intervention.

---

## 📌 Project Overview

| Field | Detail |
|---|---|
| **Platform** | Make.com |
| **Scenarios** | 3 — Intake Capture · Urgency Triage · 24hr Escalation |
| **Trigger** | Google Form submission · Airtable record watch · Daily 8AM schedule |
| **Actions** | Airtable record creation · Slack urgency alerts · 24hr escalation |
| **Channels** | #urgent-triage · #medium-triage · #triage-escalations |
| **Result** | Response time reduced from 90 mins → under 2 mins |
| **Status** | ✅ Live — all 3 scenarios active and passing |

---

## 🗂️ Table of Contents

- [The Problem](#the-problem)
- [All 3 Scenarios — Overview](#all-3-scenarios--overview)
- [Scenario Breakdown](#scenario-breakdown)
- [Airtable Database](#airtable-database)
- [Live Slack Alert](#live-slack-alert)
- [Impact & Results](#impact--results)
- [Tools Used](#tools-used)
- [Author](#author)

---

## ❌ The Problem

Clinics lose critical time when patient intake forms are processed manually. Reception staff must read forms, assess urgency, and manually alert doctors — a process taking **30 to 90 minutes**.

| Before | After Automation |
|---|---|
| Manual form reading: 30–90 mins | Auto-captured in Airtable: < 30 secs |
| Doctor notified by phone or walk-in | Instant Slack alert with full patient details |
| No follow-up on open cases | Automated 24-hour escalation system |
| Risk of missed urgent patients | Zero missed high-priority alerts |

---

## 🔁 All 3 Scenarios — Overview

![Patient Triage — All 3 Scenarios](patient_triage_workflow_v2.jpg)

---

## 🧩 Scenario Breakdown

### S1 · Patient Intake Capture

![S1 — Patient Intake Capture](S1-Patient%20form%20intake.jpg)

Every new Google Form submission is automatically captured and stored in Airtable with `Status = Open`. No manual data entry. No delay.

- **Trigger:** Google Form submitted → Google Sheets new row detected
- **Action:** Record auto-created in Airtable with all 11 patient fields populated

---

### S2 · Urgency Triage Alert

![S2 — Urgency Triage Alert](S2-Urgency%20Traige%20Alert.jpg)

New Airtable records are watched in real time. A Router reads the `Urgency Level` field and routes the alert to the correct Slack channel instantly.

- **Trigger:** New Airtable record detected
- **Action:** Router sends alert to:
  - 🔴 `#urgent-triage` — High urgency patients
  - 🟡 `#medium-triage` — Medium urgency patients
  - 🟢 Low urgency — Record logged, no alert fired

---

### S3 · 24hr Escalation Alert

![S3 — 24hr Escalation Alert](24-hours%20Escalation%20Alert.jpg)

Runs automatically every day at **8:00 AM**. Searches Airtable for any High urgency cases that have been open for more than 24 hours and fires an escalation alert to `#triage-escalations`.

- **Trigger:** Daily schedule at 8:00 AM
- **Action:** Loop through unresolved patients → Send escalation to #triage-escalations

---

## 🗄️ Airtable Database

![Airtable Patient Triage Database](Airtable%20_Database%20CRM.jpg)

The `Intake Records` table in Airtable serves as the central CRM — storing all patient records with real-time Status tracking across 11 structured fields: Name, Date of Birth, Contact Number, Primary Symptoms, Urgency Level, Duration, Preferred Doctor, Status, and Submission Timestamp.

---

## 💬 Live Slack Alert — #urgent-triage

![High Urgency Slack Notification](High%20Ugency%20slack%20notificatio%20.jpg)

Real-time HIGH URGENCY alert fired to `#urgent-triage` for patient **Fabian Greatness** — Tiredness & Dizziness, 5 days — instantly notifying the clinical team with full patient details including contact number, symptoms, duration, preferred doctor, and submission timestamp.

---

## 📊 Impact & Results

| Metric | Result |
|---|---|
| Triage response time | **< 2 minutes** (was 30–90 mins) |
| Scenarios built | **3** — fully automated clinical intake pipeline |
| High urgency alerts missed | **0** |
| Slack channels automated | **3** — #urgent-triage · #medium-triage · #triage-escalations |
| Airtable fields tracked | **11** structured patient fields |

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| ![Make.com](https://img.shields.io/badge/Make.com-6D00CC?style=flat&logo=make&logoColor=white) | Automation platform — all 3 scenarios |
| ![Google Forms](https://img.shields.io/badge/Google_Forms-7248B9?style=flat&logo=googleforms&logoColor=white) | Patient intake form — triggers S1 |
| ![Airtable](https://img.shields.io/badge/Airtable-18BFFF?style=flat&logo=airtable&logoColor=white) | Central CRM — stores all patient records |
| ![Slack](https://img.shields.io/badge/Slack-4A154B?style=flat&logo=slack&logoColor=white) | Real-time alerts — 3 dedicated channels |

---

## 📁 Repository Structure

```
Make.com-patient-triage-alert-system/
│
├── README.md
├── patient_triage_workflow_v2.jpg      ← All 3 scenarios overview
├── S1-Patient form intake.jpg          ← S1 — Intake capture
├── S2-Urgency Traige Alert.jpg         ← S2 — Urgency triage
├── 24-hours Escalation Alert.jpg       ← S3 — 24hr escalation
├── Airtable _Database CRM.jpg          ← Airtable patient records
└── High Ugency slack notificatio .jpg  ← Live Slack alert
```

---

## 👩🏾‍💻 Author

**Gloria Njorteah** · Make.com Automation · April 2026

*Built with Make.com — automating clinical triage so no urgent patient is ever missed.*
