# 🅿️ University of Iowa Parking Analysis Dashboard

A powerful Power BI dashboard designed to help the **University of Iowa's Parking and Transportation Department** monitor, analyze, and optimize parking lot usage across campus. This project empowers data-driven decisions through rich visuals, interactive filters, and advanced forecasting techniques.

---

## 📊 Overview

### 🎯 Purpose

This dashboard provides critical insights into:

- 🚗 Parking usage trends (entries, exits, durations)
- 👥 User behavior (access groups, usage patterns)
- ⏰ Peak usage forecasting (monthly and yearly)
- 🎓 Impact of academic events on parking demand

It supports strategic decisions for:
- Issuing new parking access cards
- Managing access groups
- Optimizing parking policies

---

## 📐 Data Model & Relationships

### 🔗 Core Tables

| Table | Purpose | Key Fields |
|-------|---------|------------|
| `CardTransaction` | Log of parking card usage | CardNumber, EntranceDate, ExitDate, LotNumber |
| `CardAccessGroupAssignment` | Maps cards to access groups | CardNumber, GroupNumber, Priority |
| `Calendar` | Time intelligence support | Date, Month, Year, DayOfWeek, IsWeekend |
| `AcademicCalendar` | Academic events metadata | Date, EventType, Description |
| `DailyPeakUsage` | Pre-calculated peak parking usage | Date, LotNumber, DailyPeak |
| `CardBridge` | Bridge for many-to-many relationships | CardNumber |

### 🔗 Relationships

- `Calendar[Date]` → `CardTransaction[EntranceDate]` (Active)
- `Calendar[Date]` → `CardTransaction[ExitDate]` (Inactive)
- `CardTransaction[CardNumber]` → `CardBridge[CardNumber]`
- `CardAccessGroupAssignment[CardNumber]` → `CardBridge[CardNumber]`
- `Calendar[Date]` → `AcademicCalendar[Date]`
- `Calendar[Date]` → `DailyPeakUsage[Date]`

---

## 📈 Key Dashboards & Insights

| Page | Description |
|------|-------------|
| **Dashboard Overview** | Entry point with purpose, KPIs, and academic calendar |
| **Parking Access Insights** | Active cards, access groups, lot summaries, top/least used groups |
| **Usage by Lots** | Heatmaps showing occupancy and transactions by time |
| **Peak Entry/Exit Days** | Trends and anomalies like overnight or long stays |
| **Parking During Events** | Event vs. non-event comparisons |
| **Forecasted Peak Usage (2025)** | Prophet-based time series predictions |

---

## 📉 Forecasting (2025 Peak Usage)

### 📦 Technology Used
- **Facebook Prophet (via Python Visual in Power BI)**
- **Power BI**
- **Python**
- **Python**

### 🧠
