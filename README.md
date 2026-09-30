# CivicFix – Citizen Issue Tracker
### Smart City & Civic Life Vertical • Innovation Forge 2026

**CivicFix** is a complete, modern civic-tech web application engineered to bridge the gap between citizens and municipal authorities for reporting, routing, tracking, and resolving road and public-space issues.

---

## 🏛️ Problem & Solution Overview

### Problem Statement
Citizens frequently encounter dangerous potholes, road cave-ins, water stagnation, and blocked pedestrian sidewalks with no transparent or accountable mechanism to track complaints until physical resolution.

### CivicFix Solution Journey
$$\text{Report} \longrightarrow \text{Route} \longrightarrow \text{Track} \longrightarrow \text{Resolve}$$

1. **Report**: Citizen snaps or uploads a photo, picks an issue category, pins the location on an interactive city map, and submits in under 60 seconds.
2. **Route**: Municipal operations center receives the report, reviews urgency/priority, and dispatches the work order to the responsible department (Road Maintenance, Public Works, Water Department, Sanitation).
3. **Track**: Citizen gets an instant unique tracking ID (e.g. `CFX-2026-00124`) to monitor live field progress through a 4-stage visual timeline.
4. **Resolve**: Field crews execute repairs on site, municipal supervisors verify remediation, and the issue is officially marked resolved with timestamps and notes.

---

## 🚀 Key Features

- **Civic Tech Design System**: Sleek modern dark UI with glassmorphism, glowing status badges, vibrant civic accents, responsive layouts, and accessible typography (`Plus Jakarta Sans` & `Inter`).
- **5-Step Citizen Reporting Wizard**:
  - **Step 1: Category Selection**: Pothole, Damaged Road, Water Stagnation, Blocked Footpath, Street Maintenance, Other Civic.
  - **Step 2: Issue Details**: Title, detailed description with pre-filled suggestion chips for rapid testing.
  - **Step 3: Location Pinpoint**: Interactive Mock City Grid map with radar pin placement, coordinates calculation, and 6 preset municipal sectors.
  - **Step 4: Photo Evidence**: Drag & drop file upload with live FileReader preview + 4 pre-loaded real photos generated for this MVP.
  - **Step 5: Review & Submit**: Comprehensive pre-submission review card.
- **Unique Complaint ID Generation**: Instant generation of tracking codes (`CFX-2026-00124`, `CFX-2026-00128`).
- **Visual 4-Stage Lifecycle Timeline**:
  - `Reported` ✓ $\rightarrow$ `Assigned` ✓ $\rightarrow$ `In Progress` ● $\rightarrow$ `Resolved` ○
  - Dynamic pulse on active stage, green checkmarks on completed milestones, timestamps, and departmental field notes.
- **Citizen Dashboard ("My Complaints")**:
  - Live metric counters (Total, Active, Resolved).
  - Filter tabs (All, Active, Resolved).
  - Cards with mini progress bars and quick tracking links.
- **Authority / Admin Dashboard**:
  - Live municipal operational KPIs (Total, New Reports, Assigned, In Progress, Resolved).
  - Multi-filtering by Status, Category, and Priority.
  - Real-time search across ID, Title, and Location.
  - Interactive **Admin Management Modal**:
    - Change Status (`Reported`, `Assigned`, `In Progress`, `Resolved`)
    - Assign Department (`Road Maintenance`, `Public Works`, `Water Department`, `Sanitation`, `Local Maintenance Team`)
    - Set Priority (`Low`, `Medium`, `High`, `Critical`)
    - Add Official Department Notes & Resolution Remarks
- **Real-Time Data Synchronization**:
  - Single central reactive store backed by `localStorage` (with automatic in-memory fallback).
  - Updates in Admin immediately sync to the Citizen Tracking page and Dashboard without page reload!
- **Civic Copilot – AI Civic Assistant**:
  - Floating launcher at bottom-right with animated pulse, status indicator, and teaser pill.
  - Dedicated municipal AI assistant window titled "Civic Copilot" with clear Demo Mode indicators.
  - Intelligent guidance on reporting potholes, damaged roads, garbage/waste, and streetlights.
  - Step-by-step reporting walkthrough with direct action triggers into the report wizard.
  - Live complaint tracking verifying actual statuses, departments, and timelines directly from `CivicStore` (no fake data).
  - Quick-reply inquiry buttons: *"How to report an issue?"*, *"How to track my complaint?"*, *"What services are available?"*, *"How does CivicFix work?"*, plus contextual issue chips.
  - Seamless navigation hooks to Citizen views and Authority Portal.

---

## 📁 Project Structure

```
civicfix/
├── index.html                   # Complete semantic HTML5 single-page application
├── css/
│   ├── styles.css               # Modern CivicTech design system & responsive styling
│   └── chatbot.css              # Civic Copilot AI widget styles & responsive layout
├── js/
│   ├── data.js                  # Data store, sample complaints, categories, reactive store
│   ├── app.js                   # Application controller, wizard logic, admin actions
│   └── chatbot.js               # Civic Copilot AI assistant, intent engine & live lookup
├── assets/
│   └── images/                  # Real civic issue imagery
│       ├── pothole.jpg          # Generated realistic asphalt pothole photo
│       ├── water_stagnation.jpg # Generated realistic water logging photo
│       ├── damaged_road.jpg     # Generated realistic cracked road photo
│       └── blocked_footpath.jpg # Generated realistic blocked sidewalk photo
├── server.ps1                   # Zero-dependency PowerShell static HTTP server
└── README.md                    # Project documentation
```

---

## 🏃 How to Run the Application

### Option A: Local HTTP Server (Recommended)
1. Open PowerShell and navigate to the project directory:
   ```powershell
   cd C:\Users\jayas\.gemini\antigravity-ide\scratch\civicfix
   ```
2. Start the local server:
   ```powershell
   powershell -ExecutionPolicy Bypass -File server.ps1
   ```
3. Open your browser and go to:
   ```
   http://localhost:3000
   ```

### Option B: Direct Browser Open
Because CivicFix is built with vanilla web technologies, you can also double-click:
```
C:\Users\jayas\.gemini\antigravity-ide\scratch\civicfix\index.html
```
to open it directly in Google Chrome, Microsoft Edge, Firefox, or Safari.

---

## 🎯 Innovation Forge 2026 Presentation Flow

Follow this exact sequence to demonstrate the platform to evaluators:

1. **Home**: Open `http://localhost:3000`. Show the landing page, live pulse counters, and the 4-step process.
2. **Report Issue**: Click **Report an Issue**. Select **Pothole** $\rightarrow$ Click Next $\rightarrow$ Click pre-fill chip *"Large pothole near main road"* $\rightarrow$ Click Next $\rightarrow$ Select *"Main Road"* location $\rightarrow$ Click Next $\rightarrow$ Select photo $\rightarrow$ Review $\rightarrow$ Click **Submit Complaint**.
3. **Receive ID**: See success screen with generated ID (e.g. `CFX-2026-00128`).
4. **Track Complaint**: Click **Track This Complaint**. Show the visual timeline in `Reported` state.
5. **Open Authority Portal**: Click **Authority Portal** or **Admin Mode** in the header. See the complaint in the queue.
6. **Assign & Advance**: Click **Manage** on the complaint. Change status to `In Progress`, assign to **Road Maintenance**, add field notes, and click **Save & Sync Updates**.
7. **Mark Resolved**: Open **Manage** again, change status to `Resolved`, and save.
8. **Verify Citizen View**: Switch back to **Track Complaint** or click **My Complaints**. Notice that the status is now officially `Resolved` with full completion checkmarks and official sign-off!
