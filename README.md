# RepairTrack - Repair Service Tracker Web Application
> **Web Programming College Project**

RepairTrack is a complete, modern, responsive web application for managing and tracking electronic device repair requests. Designed with a clean navy blue, white, and light-grey theme, it allows customers to submit repair bookings and track live technician progress via unique Repair IDs (e.g. `RT-1001`), while providing technicians with a comprehensive administrative management dashboard.

---

## 🌟 Key Features

### 1. Home Page (`#home`)
- **Hero Showcase**: Prominent headline *"Track Your Repair. Stay Updated."* with quick-action buttons and an integrated instant-tracking widget.
- **Service Benefits**: Highlights certified technicians, real-time 5-stage timeline updates, transparent upfront diagnostic pricing, and 90-day warranty.
- **4-Step Process Section**: Visual guide explaining *Book & Submit &rarr; Bench Diagnosis &rarr; Precision Repair &rarr; Pickup & Warranty*.
- **Metrics & Social Proof**: Live service counter statistics banner.

### 2. Book a Repair (`#book`)
- **Comprehensive Form**:
  - Customer Name & Phone Number (formatted validation)
  - Email Address (regex validation)
  - Device Type (*Mobile, Laptop, Tablet, Desktop, Other*)
  - Brand & Model input
  - Problem Category (*Screen Damage, Battery/Power, Liquid Damage, Port/Charging, Hardware, etc.*)
  - Problem Description (with live character counter and validation)
  - Preferred Drop-Off Date (automatically sets minimum to current date)
- **1-Click "Fill with Demo Data" Button**: Effortlessly populates realistic test data during college lab evaluations and presentations.
- **Auto-Generated Unique Repair ID**: Generates sequential IDs (e.g. `RT-1006`) and sets initial status to `"Request Received"`.
- **Booking Confirmation Modal**: Displays the assigned Repair ID with a 1-click clipboard copy button and a direct shortcut to track the device immediately.

### 3. Track Repair Status (`#track`)
- **Lookup by Repair ID**: Quick search with interactive demo chips (`RT-1001`, `RT-1002`, `RT-1003`, `RT-1005`).
- **5-Stage Visual Progress Timeline**:
  1. *Request Received*
  2. *Diagnosis*
  3. *In Repair*
  4. *Ready for Pickup*
  5. *Completed*
  - Active stage features animated pulse markers; completed stages display checkmarks; connector bar dynamically fills according to stage.
- **Diagnostic Cost & Dates**: Displays estimated repair cost (or `"Pending Diagnostic Quote"`) and expected target completion date.
- **Technician Workbench Notes**: Real-time diagnostic notes entered by the technician in the admin dashboard.
- **Overdue Alert Banner**: Automatically flags repairs that are past their expected completion date and not yet completed (try sample `RT-1005`).
- **Print Ticket / Receipt**: Dedicated `@media print` styling to print or save the repair ticket as a PDF.
- **Friendly Empty & Error States**: Graceful feedback if an invalid ID is entered.

### 4. Admin Management Dashboard (`#admin`)
- **College Prototype Authentication**:
  - Educational demo sign-in with pre-filled credentials:
    - **Username:** `admin`
    - **Password:** `admin123`
  - 1-click *"Fast Demo Login"* button for effortless grading demonstrations.
- **Real-Time Analytics Metrics Cards**:
  - Total Repair Requests
  - Pending Intake Requests (*Request Received + Diagnosis*)
  - In Progress Repairs (*In Repair*)
  - Completed / Ready (*Ready for Pickup + Completed*)
- **Searchable & Filterable Table**:
  - Live search across Repair IDs, customer names, phone numbers, and device brands.
  - Filter by repair status and device category.
  - Overdue warning tags on table rows.
- **Manage Repair Modal**:
  - Change repair status between all 5 stages.
  - Enter or adjust estimated repair cost ($).
  - Update expected completion date.
  - Log technician workbench notes (instantly reflected on customer tracking view).
- **Deletion with Confirmation Modal**: Safely delete records with confirmation safeguards.
- **Reset Demo Data**: Easily restore original sample records at any point.

### 5. Repair Request Catalog (`#history`)
- Searchable directory of all logged repair requests.
- Filter tabs for *All, Received, Diagnosis, In Repair, Ready for Pickup, and Completed*.
- Quick-track action buttons to jump directly to detailed tracking view.

---

## 🛠️ Technology Stack

- **Frontend Core:** Semantic HTML5, CSS3 (Modern Flexbox & CSS Grid, Custom CSS Variables), ES6+ Vanilla JavaScript.
- **Storage:** Browser `localStorage` for complete data persistence across page reloads without database setup.
- **Zero Heavy Dependencies:** No Node.js build step, no npm installs, and no external framework compilation required.
- **Styling Architecture:**
  - Modern Navy Blue (`#0F172A`), Slate Grey, and Accent Blue (`#2563EB`) design system.
  - Responsive breakpoints for Mobile (<768px), Tablet (<992px), and Desktop.
  - CSS animations (`fadeIn`, `pulseMarker`, `slideToast`).
  - Native SVG icons (crisp and scalable).

---

## 🚀 How to Run the Application

Because the project is built with standard Web technologies and client-side storage, you can run it using any of the following methods:

### Option A: Using Python Built-in Web Server (Recommended)
Open PowerShell or Command Prompt in the project folder:
```powershell
cd C:\Users\ANUSHEYA\.gemini\antigravity\scratch\repair-service-tracker
python -m http.server 8000
```
Then open your web browser and navigate to:
```
http://localhost:8000
```

### Option B: Direct Browser Launch (No Server Required)
Simply double-click `index.html` or open it directly in Google Chrome, Microsoft Edge, or Mozilla Firefox:
```
file:///C:/Users/ANUSHEYA/.gemini/antigravity/scratch/repair-service-tracker/index.html
```

---

## 🧪 Step-by-Step College Presentation & Testing Guide

| Step | Feature Tested | Action to Demonstrate | Expected Result |
| :--- | :--- | :--- | :--- |
| **1** | **Hero & Navigation** | Click on navigation bar links (*Home, Book, Track, History, Admin*). | Seamless instant view transitions without full page reloads. |
| **2** | **Quick Tracking** | On the Home page, click the sample chip `RT-1001` or enter `RT-1001` in the Quick Check box. | Directly opens Track page showing iPhone 14 Pro at the *In Repair* stage with timeline progress. |
| **3** | **Book a Repair** | Go to **Book a Repair** & click **"Fill with Demo Data"**, then click **"Submit Repair Request"**. | Realistic form fields auto-fill; form submits; confirmation modal appears displaying unique ID (e.g. `RT-1006`). |
| **4** | **Unique ID Tracking** | In the booking modal, click **"Track This Repair Now"**. | Directs to Track page showing the newly booked repair in stage `1. Request Received`. |
| **5** | **Overdue Alert Test** | On Track page, click sample chip `RT-1005 (Overdue Demo)`. | Displays red Overdue Alert Banner notifying that target completion date was in the past. |
| **6** | **Admin Sign-In** | Go to **Admin Portal**, click **"⚡ 1-Click Fast Demo Login"**. | Logs in immediately, displays 4 metric KPI cards and the data table. |
| **7** | **Admin Status Update** | On admin table, click **Edit** on `RT-1004` (Marcus Brody). Change status to `In Repair`, set cost to `$150.00`, add note: *"Replaced power supply and RAM"*, click **Save Changes**. | Table metrics update instantly. Jump to Track page for `RT-1004` to see stage advanced to *In Repair* and note visible! |
| **8** | **Data Persistence** | Refresh the browser (`F5` or `Ctrl+R`). | All modifications and newly created records persist intact in `localStorage`. |
| **9** | **Search & Filters** | In Admin or History, type `"MacBook"` in search or filter by `"Laptop"`. | Table immediately filters down to matching records in real-time. |
| **10**| **Reset Demo Records** | In Admin Dashboard, click **"Reset Demo Data"** and confirm. | Resets database back to default initial records for the next test. |

---

## 📁 Project File Structure

```
repair-service-tracker/
├── index.html          # Semantic HTML5 single-page application structure & modals
├── css/
│   └── style.css       # Complete design system, responsive grids, timeline, & print styles
├── js/
│   ├── storage.js      # LocalStorage manager, mock seeding, CRUD helpers, & ID generator
│   ├── app.js          # Client-side router, mobile navigation, & toast notification system
│   ├── book.js         # Booking form validation, demo data auto-fill, & intake handler
│   ├── track.js        # Timeline visualizer, overdue checks, search lookup, & ticket print
│   ├── admin.js        # Admin authentication, metrics calculation, edit modal, & record deletion
│   └── history.js      # Catalog listing, status filtering tabs, & search handler
└── README.md           # Project documentation, architecture overview, & presentation script
```

---

## 🎓 Academic Presentation Notes

- **Why LocalStorage?** Demonstrates persistent client-side state handling and JSON serialization in Web Programming without requiring complex backend servers or database configuration during evaluations.
- **Clean Architecture:** Code is modularized into distinct separation of concerns (`storage.js` for data layer, `app.js` for routing and UI, and individual feature controllers).
- **Responsive Layout:** Responsive down to 320px mobile screens with hamburger menu support.
