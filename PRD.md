# Product Requirements Document (PRD)


## 1. Executive Summary
**DormGuard** is a portable, plug-and-play hardware device designed to solve energy wastage in shared university dormitories. By monitoring occupancy, ambient light, and power usage, it provides real-time audio-visual feedback to remind students to save energy, reducing electricity bills and roommate conflicts.

---

## 2. Problem Statement
* **Context:** Undergraduate students in 4–6 person dorms frequently waste energy due to oversight (e.g., leaving lights on, chargers plugged in).
* **Current Workarounds:** Sticky notes and verbal reminders (inconsistent and lack data).
* **Consequences:** Inflated bills, roommate friction, and poor sustainability habits.

---

## 3. User Stories

| ID | As a... | I want to... | So that... |
| :--- | :--- | :--- | :--- |
| **US-01** | **Student** | Plug in the device and have it work immediately. | I don't have to read a manual or configure complex settings. |
| **US-02** | **Roommate** | See/Hear an alert when I leave a light on in an empty room. | I can correct my mistake immediately and save money. |
| **US-03** | **User** | See a daily summary of energy waste. | I can track my progress and feel motivated to improve. |
| **US-04** | **Resident** | Avoid arguments about the electricity bill. | We have objective data on who/what is wasting power. |
| **US-05** | **Student** | Have a gradual or gentle alert sound. | I can notice it without being startled while studying. |
| **US-06** | **Dorm Lead** | See a "Weekly Achievement Leaderboard" on screen. | I can recognize and praise the team's efforts. |

---

## 4. Functional Requirements & Feature List

### 4.1 Core Monitoring (The "Brain")
* **FR-01: Presence Detection** — PIR sensor to monitor human activity.
* **FR-02: Light Sensing** — Measure ambient light to detect if bulbs are active during daylight.
* **FR-03: Power Tracking** — Real-time current draw detection of the connected outlet.

### 4.2 Alert System (The "Feedback")
* **FR-04: Core Logic** — Trigger Alert `IF [No Motion] AND ([Light On] OR [Power Draw > Threshold])`.
* **FR-05: Audio-Visual Action** — LED indicator + Buzzer chime + Screen notification.
* **FR-06: Gentle Escalation** — Alerts must be distinct but non-intrusive (Gradual volume/brightness).

### 4.3 Data & Hardware
* **FR-07: Real-time Dashboard** — Display current saving status on an OLED screen.
* **FR-08: Historical Logs** — Daily count of "Wasted Energy Incidents" and weekly trends.
* **FR-09: Plug-and-Play** — Portable form factor; no complex software setup required.

---

## 5. Initial Architecture

###  Input Layer (Sensors)
* **PIR Motion Sensor** (Occupancy# DormGuard: Product Requirements Document (PRD)

> **Status:** Draft / Mission 2 Submission  
> **Core Concept:** A plug-and-play energy monitoring & alert system for shared dormitories.

---

## 1. Executive Summary
**DormGuard** is a portable, plug-and-play hardware device designed to solve energy wastage in shared university dormitories. By monitoring occupancy, ambient light, and power usage, it provides real-time audio-visual feedback to remind students to save energy, reducing electricity bills and roommate conflicts.

---

## 2. Problem Statement
* **Context:** Undergraduate students in 4–6 person dorms frequently waste energy due to oversight (e.g., leaving lights on, chargers plugged in).
* **Current Workarounds:** Sticky notes and verbal reminders (inconsistent and lack data).
* **Consequences:** Inflated bills, roommate friction, and poor sustainability habits.

---

## 3. User Stories

| ID | As a... | I want to... | So that... |
| :--- | :--- | :--- | :--- |
| **US-01** | **Student** | Plug in the device and have it work immediately. | I don't have to read a manual or configure complex settings. |
| **US-02** | **Roommate** | See/Hear an alert when I leave a light on in an empty room. | I can correct my mistake immediately and save money. |
| **US-03** | **User** | See a daily summary of energy waste. | I can track my progress and feel motivated to improve. |
| **US-04** | **Resident** | Avoid arguments about the electricity bill. | We have objective data on who/what is wasting power. |
| **US-05** | **Student** | Have a gradual or gentle alert sound. | I can notice it without being startled while studying. |
| **US-06** | **Dorm Lead** | See a "Weekly Achievement Leaderboard" on screen. | I can recognize and praise the team's efforts. |

---

## 4. Functional Requirements & Feature List

### 4.1 Core Monitoring (The "Brain")
* **FR-01: Presence Detection** — PIR sensor to monitor human activity.
* **FR-02: Light Sensing** — Measure ambient light to detect if bulbs are active during daylight.
* **FR-03: Power Tracking** — Real-time current draw detection of the connected outlet.

### 4.2 Alert System (The "Feedback")
* **FR-04: Core Logic** — Trigger Alert `IF [No Motion] AND ([Light On] OR [Power Draw > Threshold])`.
* **FR-05: Audio-Visual Action** — LED indicator + Buzzer chime + Screen notification.
* **FR-06: Gentle Escalation** — Alerts must be distinct but non-intrusive (Gradual volume/brightness).

### 4.3 Data & Hardware
* **FR-07: Real-time Dashboard** — Display current saving status on an OLED screen.
* **FR-08: Historical Logs** — Daily count of "Wasted Energy Incidents" and weekly trends.
* **FR-09: Plug-and-Play** — Portable form factor; no complex software setup required.

---

## 5. Initial Architecture

### 🔌 Input Layer (Sensors)
* **PIR Motion Sensor** (Occupancy
