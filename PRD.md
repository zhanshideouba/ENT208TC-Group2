# Product Requirements Document

## 1. Executive Summary
DormGuard is a portable, plug-and-play hardware device designed to solve energy wastage in shared university dormitories. By monitoring occupancy, ambient light, and power usage, it provides real-time audio-visual feedback to remind students to save energy, thereby reducing electricity bills and roommate conflicts.

## 2. Problem Statement
**Context:** Undergraduate students in 4–6 person dorms frequently waste energy due to busy schedules and oversight (e.g., leaving lights on, chargers plugged in).

**Current Workarounds:** Sticky notes and verbal reminders.

**Pain Points:** These methods lack consistency, real-time feedback, and visual data.

**Consequences:** Inflated electricity bills, roommate conflicts over cost-sharing, and a failure to cultivate low-carbon habits.

## 3. Target Users
**Primary Persona:** Sophomore and Junior undergraduates living in 4–6 person dorms.

**Characteristics:**
**Share monthly electricity costs:** High sensitivity to utility expenses.
**Busy academic/club schedules:** Leads to frequent forgetfulness and oversight.
**Value sustainability:** They care about the environment but lack the tools to practice it easily in a shared space.

**Why existing solutions fail:** Industrial energy monitors are too complex and not designed for small-scale, rented dorm environments.

## 4. User Stories

| ID | As a... | I want to... | So that... |
| :--- | :--- | :--- | :--- |
| US-01 | Student | Plug in the device and have it work immediately | I don't want to read a manual or configure complex settings. |
| US-02 | Roommate | Hear/See an alert when I leave a light on in an empty room | I can correct my mistake immediately and save money. |
| US-03 | User | See a daily summary of energy waste | I can track my progress and feel motivated to improve. |
| US-04 | Resident | Avoid arguments about the electricity bill | We have objective data on who/what is wasting power. |
| US-05 | Student | Have a gradual or gentle alert sound | I can notice it without being startled or interrupted while studying. |
| US-06 | Dorm Lead | See a "Weekly Achievement Leaderboard" on screen | I can recognize and praise the team's efforts during dorm meetings. |

## 5. Functional Requirements & Features

### 5.1 Core Monitoring (The "Brain")
**FR-01:** The device must automatically monitor human presence (PIR sensor) within the dorm.
**FR-02:** The device must measure ambient light levels to detect daylight or active bulbs.
**FR-03:** The device must detect real-time power status (current draw) of the connected outlet.

### 5.2 Alert System
**FR-04: Logic:** If [No Motion] AND [Light On] OR [High Ambient Light] AND [Power Draw > Threshold] → Trigger Alert.
**FR-05: Action:** Trigger immediate audio-visual alert (LED indicator + Buzzer/Chime) and screen notification.
**FR-06:** Alerts must be distinct enough to be noticed but not intrusive enough to disrupt study.

### 5.3 Data & Display
**FR-07:** Display real-time energy-saving status on the onboard screen.
**FR-08:** Show a daily count of "Wasted Energy Incidents."
**FR-09:** Maintain a "Dormitory Energy-Saving Check-in Log" (historical data).

### 5.4 Hardware Constraints
**FR-10: Form Factor:** Portable, compact, suitable for a desk or bedside table.
**FR-11: Setup:** "Plug-and-play" architecture. No complex installation or app configuration.

## 6. Initial Architecture (High-Level)
Note: This is a
