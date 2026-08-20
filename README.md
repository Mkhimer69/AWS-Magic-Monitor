# 🚀 AWS Magic Monitor

A real-time workforce monitoring dashboard for Amazon Connect built as a Tampermonkey userscript.

AWS Magic Monitor intercepts live Amazon Connect Analytics API calls and converts raw operational data into a lightweight command center for Real-Time Analysts (RTAs), Workforce Management (WFM), Operations Managers, and Team Leads.

---

## 📸 Overview

AWS Magic Monitor transforms native AWS Connect analytics data into an interactive dashboard that provides:

- Queue Occupancy
- Available Agents
- Agents On Contact
- Routing Profile Distribution
- Compliance Flags
- Longest Active Contacts
- Real-Time Refresh Monitoring
- CSV Export

All data is collected directly from the Amazon Connect Analytics Dashboard without requiring external APIs, databases, or backend services.

---

## ✨ Features

### Real-Time Monitoring

- Live AWS Connect API interception
- Automatic refresh when dashboard data updates
- Real-time queue occupancy calculations
- Queue-based workforce visibility

### Agent Visibility

- Available Agents
- On Contact Agents
- Duration Tracking
- Longest Active Contacts
- Missed Contact Detection

### Compliance Monitoring

Custom operational flags:

- Break > 16 minutes
- Lunch > 31 minutes
- Coaching > 31 minutes
- Meeting > 31 minutes
- Missed Contacts
- After Contact Work > 6 minutes

### Queue Analytics

- Occupancy %
- Available Count
- Contact Count
- Routing Profile Distribution
- Queue-Level Agent Visibility

### Productivity Features

- CSV Export
- Resizable Dashboard
- Draggable Dashboard
- Expandable Sections
- Auto Sorted Lists

---

## 🛠️ Technical Highlights

### AWS Analytics Interception

The tool listens for AWS Analytics API calls:

```javascript
window.fetch = async (...args) => {
    ...
}
```

and extracts:

- AGENT_VIEW_NAME
- AGENT_VIEW_STATE
- AGENT_VIEW_STATE_DURATION
- AGENT_VIEW_PROFILE
- ACTIVE_SLOTS
- MAX_SLOTS

---

### Queue Aggregation

Agents are automatically grouped by routing profile:

```javascript
Driver
Safety
Rider
Support
```

Queue occupancy is then calculated using:

```text
Occupancy % = Active Slots / Capacity
```

---

### Live Dashboard Rendering

Data is rendered dynamically into:

- Queue Cards
- Agent Tables
- Compliance Sections
- Routing Profile Summaries

without requiring page refreshes.

---

## 🖥️ User Interface

### Dashboard Header

- Refresh Timestamp
- Export Button
- Collapse Button

### Queue Cards

Each queue contains:

- Occupancy %
- Available Agents
- On Contact Agents
- Flagged Agents
- Routing Profiles

### Expandable Sections

```text
Available
On Contact
Flags
Routing Profiles
```

---

## 📂 Exporting Data

Export all captured AWS analytics data into CSV:

```text
Agent_RealTime_Status.csv
```

Useful for:

- Staffing Analysis
- Historical Reviews
- Workforce Planning
- Operational Audits

---

## 🚦 Current Version

```text
v3.0.0
```

### Included

✅ AWS API Interception  
✅ Queue Occupancy  
✅ Agent Monitoring  
✅ Longest Contact Tracking  
✅ Compliance Flags  
✅ Routing Profile Distribution  
✅ CSV Export  
✅ Draggable UI  
✅ Resizable UI  
✅ Real-Time Refresh Tracking  

---

## 🔮 Roadmap

### v3.1

- Queue Filters
- Longest Available Tracking
- Queue Search

### v3.2

- Queue Health Indicators
- Staffing Risk Detection
- Occupancy Threshold Alerts

### v4.0

- Screenshot Mode
- Alert Center
- Historical Snapshots
- Trend Analysis

---

## 📊 Business Use Cases

### Real-Time Analysts

Monitor staffing and occupancy across queues.

### Workforce Management

Identify staffing imbalances and routing profile trends.

### Operations Managers

Track queue health and operational risk in real time.

### Team Leads

Review individual agent status and compliance concerns.

---

## ⚙️ Technology Stack

- JavaScript
- Tampermonkey
- Amazon Connect
- Browser Fetch Interception
- HTML
- CSS
