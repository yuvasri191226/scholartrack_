# 🎓 ScholarTrack: Scholarship & Fellowship Deadline Tracker

**ScholarTrack** collects scholarship and fellowship announcements from approved public websites and displays them in one searchable dashboard. Every notice links back to the original official announcement, and the app never guesses missing information. 🔗✅

Built as a mini project for the **Cybernaut Edtech** internship (*WEB-02, Web Scraping*).

## 🎯 The Problem
Scholarship information is scattered across university and official funding websites. Students waste time searching and can end up trusting stale or inaccurate deadlines.

## ✨ Features
- 🕸️ **Collector Adapters:** Supports 2 approved notice layouts with request timeout, retry, and exponential backoff.
- 📋 **Normalized Data:** Standardizes title, provider, education level, discipline, region, benefit, eligibility excerpt, deadline, and source URL.
- ⏳ **Honest Deadlines:** Unknown deadlines are explicitly shown as `"unknown"`—never converted into made-up dates.
- 🌍 **Timezone-Aware Deadlines:** Includes a timezone selector; raw UTC is never displayed as the source's local time.
- 🔄 **Revision Tracking:** Source corrections are saved as updates with full change history (previous vs. updated deadline) rather than duplicate notices.
- 🚫 **Withdrawn Notice Tracking:** Flags and tracks notices that have been officially withdrawn.
- 🔍 **Search & Filters:** Filter notices by study level, discipline, notice type, status, and deadline window.
- 📌 **Source Citations:** Displays direct source links alongside last-checked / freshness status on every notice.
- 🛠️ **Operator Dashboard:** Flags failed or blocked sources (never silently skipped), tracks run logs, provides a manual review queue (approve/flag), and supports CSV export.
- 🔔 **Alerts:** Triggers one alert per meaningful deadline revision with a delivery log *(safe demo mode, no real emails sent)*.

## 🛠️ Tech Stack
- 🐍 **Language:** Python
- ⚡ **Backend:** FastAPI, SQLAlchemy, Alembic
- 💾 **Database:** SQLite / PostgreSQL
- 🎨 **Frontend:** Jinja2 Templates
- 🧪 **Testing:** `pytest`

## 📂 Project Structure
```text
app/
├── collectors/   # Source adapters + HTTP fetching (timeout, retry, backoff)
├── services/     # Normalization, date handling, change detection, queries
└── routes/       # Public dashboard and operator pages
tests/            # Automated test suite
