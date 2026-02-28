# 🧪 QA Tracker Pro

A powerful cloud-enabled QA task management dashboard built with pure HTML, CSS and JavaScript.

Live Cloud Sync powered by Cloudflare Workers.

---

## 🚀 Features

### 📋 Task Management
- Create / Edit / Delete Tasks
- Status Tracking:
  - TODO
  - IN PROGRESS
  - TESTING
  - BLOCKED
  - DONE
- Priority Levels:
  - HIGH
  - MEDIUM
  - LOW
- Environment tagging (QA / Staging / Prod)
- Estimate hours tracking
- Blocker tracking
- Notes support

---

### 🐛 Bug Tracker
- Log bugs with severity:
  - CRITICAL
  - HIGH
  - MEDIUM
  - LOW
- Bug status management:
  - OPEN
  - IN FIX
  - FIXED
  - CLOSED
- Steps to reproduce

---

### 📊 Analytics & Reporting
- Status distribution charts (Chart.js)
- Priority distribution charts
- Daily summary reports
- EOD (End of Day) auto-generated report
- Download / Copy report options
- Leaderboard
- Activity log
- Sprint-style board view
- List view
- Analytics view (multi-day aggregation)

---

### ⏱ Time Tracking
- Estimated vs Actual hours
- Accuracy tracking
- Per-task time management

---

### 📋 Templates
- Save reusable task templates
- Quick add tasks from templates

---

### 📝 Scrum Notes
- Yesterday updates
- Today plan
- Priorities
- Blockers

---

### 🧠 Scratchpad
- Quick notes
- Auto-saved to cloud

---

### ☁️ Cloud Sync
- Real-time sync to Cloudflare Worker backend
- Cloud status indicator:
  - Green → Synced
  - Orange → Syncing
  - Red → Failed

---

## 🏗 Architecture

Frontend:
- Pure HTML
- CSS
- Vanilla JavaScript
- Chart.js CDN

Backend:
- Cloudflare Worker
- Stores JSON data
- Acts as simple REST API

```
Browser (QA Tracker Pro)
        ↓
Cloudflare Pages (Hosting)
        ↓
Cloudflare Worker (API Endpoint)
        ↓
JSON Data Store
```

---

## 🌐 Deployment

### Option 1: Cloudflare Pages (Recommended)

1. Push this project to GitHub.
2. Go to Cloudflare Dashboard.
3. Pages → Create Project.
4. Connect Git repository.
5. Framework preset: None
6. Build command: Leave empty
7. Output directory: `/`
8. Deploy.

---

## 🔌 Worker Backend Setup

Your frontend uses:

```js
const SHEET_URL = "https://qatracker.kunal-249.workers.dev";
```

To set up backend:

1. Create Cloudflare Worker.
2. Add POST handler to store data.
3. Add GET handler with `?action=getAll`.
4. Deploy worker.
5. Replace `SHEET_URL` if needed.

---

## 📦 Data Structure

```js
allData = {
  "YYYY-MM-DD": {
    tasks: [],
    bugs: [],
    userData: {},
    scrum: {},
    scratch: "",
    timeTracks: [],
    templates: []
  }
}
```

---

## 📊 Key Concepts

- Data stored per date
- Activity log keeps last 50 actions
- Tasks auto-categorized by status
- Analytics aggregates across all dates
- EOD report auto-builds from current date data

---

## 🛡 Advantages

- No framework dependency
- No build step required
- Fully serverless
- Free hosting
- Fast global CDN
- Mobile responsive
- Offline-friendly UI

---

## 📈 Future Improvements

- Multi-user login
- Role-based access
- Export to Google Sheets
- Dark/Light theme persistence
- CSV export
- Drag & Drop board

---

## 👨‍💻 Author

Kunal

---

## 📄 License

Internal QA Tool – Not for commercial redistribution.
