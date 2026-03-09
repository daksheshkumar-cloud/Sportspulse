# ⚡ SportsPulse — Athlete Intelligence Platform

> A single-file, zero-dependency sports performance dashboard built with vanilla HTML, CSS, and JavaScript.

---

## 📖 Overview

**SportsPulse** is a dark-themed, data-rich web application for tracking and managing athlete performance. It simulates a real sports analytics platform complete with role-based login, live KPI updates, injury monitoring, training plans, and detailed per-athlete breakdowns — all running entirely in the browser with no backend required.

---

## ✨ Features

### 🔐 Authentication
- Role-based login system supporting three user types: **Coach**, **Analyst**, and **Athlete**
- Animated login page with branded left panel and credential form
- Demo credentials are displayed on the login screen for easy access
- Role-specific navigation and dashboard views post-login

### 🏠 Overview Dashboard (Coach & Analyst)
- Live KPI cards: Average Heart Rate, Peak Speed, Active Athletes, Session Score
- Animated 7-session **Performance Intensity** bar chart
- Radial SVG gauges for team Endurance, Strength, and Recovery scores
- **Top Performers** table with risk bars, speed stats, and score pills
- Live Activity Feed with real-time event simulation

### 🏃 Athletes Page
- Responsive card grid for all 8 athletes
- Per-card stats: performance score, speed, heart rate, calories
- Position-based filter buttons (Forward, Midfielder, Defender, Goalkeeper)
- Risk tags (Low / Medium / High) and animated score bars

### 📊 Analytics Page
- KPI tiles: Tracking Accuracy, Data Points, Average Latency
- Speed Distribution bar chart and Training Load Heatmap (7×5 grid)
- Big-number metrics: Shoot Accuracy (87%), Defensive Coverage (74%), Fatigue Index (38%)

### ⚡ Training Page
- Weekly training plan with day, session type, duration, and intensity
- Colour-coded session completion tracker (done / pending)

### ❤️ Injury Monitor
- Summary KPIs: Low Risk (9), Medium Risk (3), High Risk (2), On Rest (2)
- Full athlete injury risk table with animated load bars and risk indicators

### ⚙️ Settings Page
- **Profile Settings** — editable name and email with save confirmation
- **Notification Settings** — toggleable alerts for Live Alerts, Session Reports, Email Digest, Push Notifications
- **Sensor Configuration** — GPS, Heart Rate Monitor, Accelerometer, Computer Vision toggles
- **System Settings** — Dark Mode, Auto-Export, Data Sharing, ML Predictions toggles

### 🏃 Athlete Role (Personal Dashboard)
When logged in as an Athlete, the sidebar switches to a personal view:
- **My Performance** — radar chart across 6 attributes (Speed, Offense, Defense, Shoot, Dribble, Pass), live stats, recent match ratings
- **Training** — personal weekly schedule with session detail and today's drill breakdown
- **Progress** — monthly performance trend chart, personal bests, skill progression bars
- **Profile** — editable contact/physical info, contract details, and benchmark metrics (Sprint, VO₂ Max, Peak Speed, Jump Height)

---

## 🗂️ Project Structure

```
Index1.html          ← Entire application (HTML + CSS + JS in one file)
```

This is a **single-file application**. All styles, markup, and JavaScript are contained within `Index1.html`.

---

## 🚀 Getting Started

No installation, build step, or server is needed.

1. Download or clone the repository
2. Open `Index1.html` in any modern web browser
3. Use the demo credentials below to log in

### Demo Credentials

| Role    | Username  | Password   |
|---------|-----------|------------|
| Coach   | `coach`   | `pulse123` |
| Analyst | `analyst` | `pulse123` |
| Athlete | `athlete` | `pulse123` |

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| HTML5 | Semantic structure and page layout |
| CSS3 | Custom properties, Flexbox, Grid, animations, clip-paths |
| Vanilla JavaScript | DOM manipulation, routing, data rendering, live updates |
| Google Fonts | Bebas Neue, Rajdhani, JetBrains Mono |
| SVG | Inline radial gauges, radar chart, line charts |

No frameworks. No libraries. No build tools.

---

## 🎨 Design System

The UI uses a dark cyberpunk aesthetic with a consistent set of CSS custom properties:

| Variable | Color | Usage |
|---|---|---|
| `--neon` | `#00f5ff` | Primary accent, active states |
| `--fire` | `#ff4d00` | Warnings, high-risk indicators |
| `--gold` | `#ffd700` | Medium risk, secondary highlights |
| `--green` | `#00ff88` | Success, low-risk, positive trends |
| `--purple` | `#a855f7` | Analyst role accent |
| `--dark` | `#060b14` | Main background |
| `--card` | `#0b1628` | Card/panel backgrounds |

Typography is handled via three Google Fonts:
- **Bebas Neue** — display headings and large numbers
- **Rajdhani** — body text and UI labels
- **JetBrains Mono** — monospace data labels and code-style text

---

## 📱 Responsive Behaviour

| Breakpoint | Behaviour |
|---|---|
| `> 900px` | Full sidebar + multi-column grid layouts |
| `≤ 900px` | Sidebar hidden (off-canvas), single-column grids, login hides left panel |
| `≤ 560px` | Athletes grid collapses to a single column |

---

## ⚙️ Key JavaScript Functions

| Function | Description |
|---|---|
| `doLogin()` | Validates credentials and renders the role-specific app shell |
| `doLogout()` | Tears down the app and returns to the login screen |
| `switchPage(name, el)` | SPA-style page router that shows/hides page sections and re-renders charts |
| `buildDashboard()` | Orchestrates rendering of all dashboard data panels on login |
| `buildChart(id, heights, labels)` | Renders animated bar charts using divs and CSS transitions |
| `buildAthletesGrid()` | Dynamically generates all athlete cards from the `PLAYERS` data array |
| `buildInjuryTable()` | Renders the injury risk monitor with animated progress bars |
| `buildTrainingPlan()` | Generates the weekly plan and session completion tracker |
| `startLiveUpdates()` | Simulates real-time data by randomly fluctuating KPI values every 2 seconds |
| `startClock()` | Displays and updates a live clock in the topbar |
| `drawRadar(stats)` | Draws a hexagonal radar chart on a `<canvas>` element for athlete performance |
| `buildAthleteProgress()` | Renders the athlete's monthly trend chart and personal bests |
| `saveProfile()` | Handles the settings profile save action with a confirmation message |

---

## 📦 Data

All application data is defined as JavaScript constants at the top of the `<script>` block:

- `USERS` — credentials and display metadata for the three roles
- `PLAYERS` — array of 8 athletes with stats (score, speed, HR, calories, injury risk)
- `ACTIVITIES` — live activity feed messages
- `TRAINING_PLAN` — weekly training schedule with day, type, duration, intensity, and completion status

---

## 🔮 Potential Enhancements

- Connect to a real backend (Node.js / Express) for live sensor data
- Persist user settings and profile changes with `localStorage` or a database
- Add a mobile sidebar toggle button for small screens
- Implement actual CSV/PDF export for session reports
- Integrate a real charting library (Chart.js, D3.js) for richer visualisations
- Add player comparison views and drill-down modals from the Athletes grid

---

## 👤 Author

Built as part of the **SportEval** project.  
Designed for the Full-Stack Web Development (FWD) module at **KL University, Bachupally**.

---

## 📄 Licence

This project is for educational purposes. Feel free to fork and extend it.
