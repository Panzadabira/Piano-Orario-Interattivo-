<p align="left">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS">
  <img src="https://img.shields.io/badge/Firebase_Firestore-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase">
  <img src="https://img.shields.io/badge/Architecture-Single_Page_App-8A2BE2?style=for-the-badge" alt="SPA">
</p>

# Universal Interactive Timeline & Workflow Planner
> *A flexible, drag-and-drop workflow and scheduling engine featuring hybrid cloud synchronization (Firebase Firestore + Local JSON Fallback).*

---

## Project Overview

The **Universal Timeline & Workflow Planner** is a standalone Single-Page Application (SPA) engineered for visualizing complex workflows, schedules, and multi-team operations.

Moving beyond static spreadsheets, this tool merges the instant ergonomics of an **interactive Kanban board** with the structure of a **multi-dimensional time grid**. It is built for absolute operational continuity: utilizing intelligent live cloud sync for collaborative environments, while maintaining full offline capability and resilience through native JSON state import and export.

---

## Core Features

*  **Fluid Drag-and-Drop Ergonomics:** Effortlessly move tasks across time slots, operational columns, and categories, or temporarily park them in the dedicated backlog area.
*  **Real-Time Cloud Synchronization:** Natively connected to **Firebase Firestore**. Every grid modification, task re-ordering, or structural change is saved instantly to the cloud, complete with a real-time connection status telemetry ping.
*  **Resilient Fallback Architecture:** If cloud connectivity is unavailable or disabled, the system automatically falls back to loading local state via a JSON schema, guaranteeing zero operational downtime.
*  **Highly Dynamic Grid Matrix:**
  * **Custom Time Slots / Columns:** Dynamically add, edit, or reorder temporal columns (e.g., *Phase 1*, *Q2*, *Morning Shift*) directly from the UI.
  * **Categorized Operational Rows:** Segment your schedule by color-coded themes and departments (e.g., *Operations*, *Logistics*, *Training*, *Urgent*, *Management*).
*  **Total Portability (JSON Export / Import):** Export your entire grid architecture—including tasks, coordinates, rows, and columns—into a clean, portable `.json` file with a single click, or restore previous states instantly.
*  **Modern UI / UX:** Built with **Tailwind CSS**, featuring sticky headers and columns for seamless horizontal scrolling across large datasets, and intuitive semantic color-coding.

---

## Tech Stack & Architecture

The entire engine is streamlined into a highly optimized, dependency-light architecture that requires no complex build pipelines or local backend servers:

| Component | Technology / Method |
| :--- | :--- |
| **Core Logic & Structure** | HTML5 / Vanilla JavaScript (ES6+ Modules) |
| **Styling & Design System** | Tailwind CSS (via high-performance CDN) & Inter Font |
| **Database & Auth** | Google Firebase (Firestore Database + Anonymous Authentication) |
| **Interactivity** | Native HTML5 Drag and Drop API |

---


##  User Guide
1. Task Management
Creation: Click the blue + New Task button. Assign a title, an optional subtitle (e.g., specific tags, dates, or assignees), and select a color category.

Editing & Deletion: Hover over any task on the grid or in the backlog; click the pencil icon in the top-right corner to modify its properties or remove it from the board.

2. Grid Customization
Use the + Column and + Row controls to expand your matrix. You can insert new elements precisely where needed (e.g., "Before: Phase 2" or "At the end").

3. The Backlog Board
The bottom grey area (Unassigned Tasks) serves as an operational holding zone. Drop tasks here when they are postponed, paused, or awaiting scheduling into a definitive time slot.

---

##  Data Security & Persistence

The planner employs a multi-tiered persistence strategy:

Live Cloud State: Data is continuously synced to a secure, isolated Firestore document path: artifacts/{appId}/public/data/planner_state/main.

Offline Data Portability: Download a complete snapshot of your database at any time by clicking Export. The generated JSON payload maps exact spatial grid coordinates (rowIndex, colIndex) for every task, ensuring seamless data restoration across different machines.

---
