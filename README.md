# Local Storage Task Tracker — Modern React & Tailwind CSS Application

A complete, responsive, and professional **Task Tracker** web application built with **React**, **Tailwind CSS**, and the browser's native **LocalStorage API**. Zero backend or database required — all tasks persist automatically in the user's browser.

![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38B2AC?logo=tailwind-css&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-6-646CFF?logo=vite&logoColor=white)
![Storage](https://img.shields.io/badge/Storage-Browser%20LocalStorage-10B981)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success)

---

## 🌟 Features Overview

### 1. Full CRUD Operations & Status Management
- **Create (Add Task):**
  - Add tasks with **Title** (required, with validation to prevent empty submissions).
  - Add **Description** for additional task details and notes.
  - Choose **Priority**: `Low 🟢`, `Medium 🟡`, or `High 🔴`.
  - Pick a **Due Date** with interactive calendar input or quick chips (`Today`, `Tomorrow`, `+1 Week`).
  - Automatic generation of unique IDs using `crypto.randomUUID()` with fallback.
- **Read (View Tasks):**
  - View all tasks in clean, interactive card layouts.
  - Automatically loads previously saved tasks from browser `LocalStorage` upon opening or refreshing.
  - Pre-seeded with helpful starter tasks on first launch.
- **Update (Edit & Status Toggle):**
  - **Status Toggle:** Click the checkbox or task title to mark between `Pending` and `Completed` status with smooth transitions and strikethrough styling.
  - **Inline Editing:** Edit Title, Description, Priority, and Due Date directly with Save / Cancel actions and keyboard shortcuts.
- **Delete (Safe Removal):**
  - **Confirmation Dialog:** Accessible confirmation modal before deleting any individual task to prevent accidental data loss.
  - **Bulk Clear Completed:** One-click clear option to delete all completed tasks at once after confirmation.

### 2. Live Search & Multi-criteria Filtering
- **Search Bar (`SearchBar`):**
  - Instant real-time search across both **Task Title** and **Task Description**.
  - Includes a clear button (`X`) and live matching item counter.
- **Filter Bar (`FilterBar`):**
  - **Status Tabs:** Filter between **All**, **Pending**, and **Completed** tasks with dynamic badge counts.
  - **Priority Filter:** Filter by specific priority (`All Priorities`, `High`, `Medium`, `Low`).
  - **Sorting Options:**
    - 🕒 **Newest first** (default)
    - ⏳ **Oldest first**
    - 🔥 **Priority: High to Low**
    - 🌱 **Priority: Low to High**
    - 📅 **Due date: Soonest first**
    - 📆 **Due date: Latest first**
  - **Reset Filters:** One-click reset to restore default view when filters or search are active.

### 3. Task Statistics & Insights (`Statistics`)
- **Metric Cards:**
  - 📋 **Total Tasks**
  - ⏳ **Pending Tasks** (with overdue counter warnings)
  - ✅ **Completed Tasks**
- **Completion Progress Bar:**
  - Real-time animated progress bar showing completion rate percentage and task fractions.
  - High-priority pending alerts and overdue warnings.

### 4. Browser LocalStorage API Integration
- **Zero Backend Required:** Directly leverages browser `localStorage`.
- **Permanent Availability:** Data survives page reloads, tab closures, and browser restarts.
- **Defensive Error Handling:** Uses safe `try...catch` blocks to protect against disabled storage, quota limits, or corrupted data.
- **Versioned Schema Migration:** Seamlessly normalizes tasks and migrates legacy formats.

### 5. Responsive Design & UI Polish
- **Mobile-First Responsive Layout:** Flawless experience across phones, tablets, laptops, and wide screens.
- **Tailwind CSS Styling:** Modern typography (`Plus Jakarta Sans`), glassmorphism accents, soft gradients, clean borders, and accessible color contrasts.
- **Micro-Interactions & Animations:** Smooth hover lift, fade-in transitions, slide-up modal dialogs, and non-intrusive toast notifications.

---

## 📂 Project Structure

```text
Task5/
├── dist/                          # Production build output
├── public/                        # Static public assets
├── src/
│   ├── assets/                    # Static image/media assets
│   ├── components/                # Reusable modular React components
│   │   ├── ConfirmModal.jsx       # Accessible delete confirmation dialog modal
│   │   ├── FilterBar.jsx          # Status tabs, priority filter & sorting selector
│   │   ├── SearchBar.jsx          # Real-time search bar (searches title & description)
│   │   ├── Statistics.jsx         # Summary cards, overdue alerts & progress bar
│   │   ├── TaskCard.jsx           # Individual task card with status, badges & editing
│   │   ├── TaskFilter.jsx         # Backward-compatible wrapper for FilterBar
│   │   ├── TaskForm.jsx           # Create/Edit form with validation, priority & due date
│   │   ├── TaskItem.jsx           # Backward-compatible wrapper for TaskCard
│   │   ├── TaskList.jsx           # Container with contextual empty states
│   │   ├── TaskStats.jsx          # Backward-compatible wrapper for Statistics
│   │   └── Toast.jsx              # Action feedback toast notifications
│   ├── utils/
│   │   └── storage.js             # LocalStorage safe read/write/sample loader
│   ├── App.jsx                    # Root component & central state orchestrator
│   ├── index.css                  # Tailwind CSS configuration & custom animations
│   └── main.jsx                   # React root mount point
├── index.html                     # HTML5 template with viewport & typography
├── package.json                   # Project metadata and dependencies
├── vite.config.js                 # Vite build tool configuration
└── README.md                      # Comprehensive project documentation
```

---

## 🛠️ Data Model / Task Schema

Each task stored in LocalStorage contains:

```json
{
  "id": "task-1727971200000-abc1234",
  "title": "Prepare quarterly project review",
  "description": "Outline key deliverables, slide deck, and performance metrics.",
  "priority": "high",
  "dueDate": "2026-10-05",
  "status": "pending",
  "completed": false,
  "createdAt": "2026-10-03T17:00:00.000Z",
  "completedAt": null
}
```

---

## 🚀 Installation & Running the Project Locally

### Prerequisites
- [Node.js](https://nodejs.org/) (version 18 or newer recommended)
- `npm` (bundled with Node.js)

### Step 1: Clone or Navigate to the Project Directory
```bash
cd Task5
```

### Step 2: Install Dependencies
```bash
npm install
```

### Step 3: Start the Development Server
```bash
npm run dev
```
Open your browser and navigate to:
```text
http://localhost:5173
```

### Step 4: Build for Production
To generate the optimized production bundle:
```bash
npm run build
```

### Step 5: Preview Production Build
To preview the generated production build locally:
```bash
npm run preview
```

### Step 6: Code Quality & Linting
Run the fast linter to verify zero linting errors:
```bash
npm run lint
```

---

## 💡 Tech Stack & Libraries

- **React.js 19:** Functional components, hooks (`useState`, `useEffect`, `useMemo`, `useRef`).
- **Tailwind CSS v4:** Modern utility-first styling with responsive modifiers and animations.
- **Lucide React:** Lightweight, clean vector icons for high visual clarity.
- **Vite 6:** Ultra-fast development server and optimized rollup bundler.
- **Browser LocalStorage API:** Client-side persistent JSON key-value storage.

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
