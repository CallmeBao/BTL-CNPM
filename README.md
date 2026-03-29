# Tutor Support System (TSS) - Frontend Application

**Course:** Software Engineering - CO3001
<img width="2537" height="1234" alt="image" src="https://github.com/user-attachments/assets/29326fc6-4ef3-45f4-b6e5-454cd568c070" />

## Project Overview

This repository contains the frontend application for the **Tutor Support System**, a comprehensive educational platform designed to connect students and tutors. Engineered using **Next.js (App Router)**, the application digitizes and streamlines the tutoring lifecycle, from discovery and matching to schedule management and real-time communication.

The system implements role-based access control with distinct, optimized portals for both Students and Tutors. By leveraging Next.js Route Groups and Dynamic Routing, the architecture maintains a strict separation of concerns while maximizing UI component reusability across different user flows.

## Features & Scope

### 1. Student Portal (`app/Sinhvien`)
A dedicated workspace enabling students to find academic support and manage their learning journey.

* **Student Dashboard:** Provides a high-level summary of daily schedules and key academic metrics.
* **Tutor Discovery (`/tim-tutor`):** A robust two-column search interface featuring dynamic filters to help students find suitable tutors based on specific criteria.
* **Class & Schedule Management:**
  * **My Classes (`/my-classes`):** Displays enrolled classes utilizing a responsive grid layout.
  * **Class Details (`[classId]`):** A dynamic, tab-based interface that allows seamless navigation between Lectures, Quizzes, and Appointments without triggering page reloads.
  * **Interactive Calendar (`/schedule`):** Integrates FullCalendar to visualize personal learning schedules across Month, Week, and Day views.
* **Program Registration (`/dang-ky`):** A streamlined application form with built-in validation and a success confirmation flow.

### 2. Tutor Portal (`app/Tutor`)
A comprehensive management interface empowering tutors to organize classes, track student progress, and control their availability.

* **Tutor Dashboard:** Monitors critical metrics such as total enrolled students, accumulated teaching hours, and pending registration approvals.
* **Class Administration (`/register-class` & `/my-classes`):**
  * **Creation Modals:** Intuitive interfaces to establish new tutoring classes and configure initial settings.
  * **Session Management (`[classId]`):** Deep-dive management tools for specific classes. Tutors can add lectures, schedule appointments, and manage student rosters via categorized tabs.
  * **Action Hub:** Quick-access tools (`AddLectureModal`, `AddScheduleModal`, `ManageMaterialsModal`) designed to expedite administrative tasks.
* **Teaching Schedule (`/schedule`):** A centralized FullCalendar interface dedicated exclusively to managing teaching commitments and availability.

### 3. Shared Communication Core (`/tin-nhan`)
A unified, real-time messaging system utilized by both Students and Tutors.

* **Interface Architecture:** Features a flexible two-column layout consisting of a conversation list sidebar and a dynamic chat window (`[peopleId]`).
* **Optimized Reusability (DRY):** The messaging logic and UI components (including `UserProfileModal`) are highly modularized. They are shared across both the Student and Tutor route groups, demonstrating efficient code reuse and maintainability.

## Technical Stack

| Category | Technology |
| :--- | :--- |
| **Core Framework** | Next.js (App Router) |
| **UI Library** | React |
| **Styling** | Tailwind CSS |
| **Advanced Components** | `@fullcalendar/react` (Schedule & Time Management) |
| **Architecture** | Component-driven, Role-based Route Groups, Dynamic Routing |

## Installation & Setup Guide

### Prerequisites
Before running the project, ensure you have the following installed:
* **Node.js**: Version 18.17.0 or higher.
* **Package Manager**: `npm`, `yarn`, or `pnpm`.
* **Backend API**: Ensure the accompanying Spring Boot backend service for the Tutor Support System is running and accessible.

### Local Development Setup

## Installation & Setup Guide

### Prerequisites
Before running the project, ensure you have the following installed:

- **Node.js**: Version 18.17.0 or higher  
- **Package Manager**: `npm`, `yarn`, or `pnpm`  
- **Backend API**: Ensure the accompanying Spring Boot backend service is running  

---

### Local Development Setup

#### 1. Clone the repository:
```bash
git clone https://github.com/CallmeBao/BTL-CNPM.git
cd BTL-CNPM
```
#### 2. Install dependencies: ####
```bash
npm install
```
#### 3. Run the development server ####
```bash
npm run dev
```
