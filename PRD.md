# Product Requirements Document

## 1. Executive Summary
DormGuard is a portable, plug-and-play hardware device designed to solve energy wastage in shared university dormitories. By monitoring occupancy, ambient light, and power usage, it provides real-time audio-visual feedback to remind students to save energy, thereby reducing electricity bills and roommate conflicts.

## 2. Problem Statement
**Context:**  
Undergraduate students in 4–6 person dorms frequently waste energy due to busy schedules and oversight (e.g., leaving lights on, chargers plugged in).

**Current Workarounds:**  
Sticky notes and verbal reminders.

**Pain Points:**  
These methods lack consistency, real-time feedback, and visual data.

**Consequences:**  
Inflated electricity bills, roommate conflicts over cost-sharing, and a failure to cultivate low-carbon habits.

## 3. Target Users
**Primary Persona:**  
Sophomore and Junior undergraduates living in 4–6 person dorms.

**Characteristics:**  
Share monthly electricity costs: High sensitivity to utility expenses  
Busy academic/club schedules: Leads to frequent forgetfulness and oversight  
Value sustainability: They care about the environment but lack the tools to practice it easily in a shared space

**Why existing solutions fail:**  
Industrial energy monitors are too complex and not designed for small-scale, rented dorm environments

## 4. User Stories

### Role 1: Dorm Resident Student
**User Story:**  
As a dorm resident student, I want the system to automatically cut power to non-essential devices when the room is unoccupied, so that I can save energy without changing my daily habits.

**Acceptance Criteria:**  
When both the infrared (PIR) sensor and ambient light sensor confirm the room has been unoccupied for ≥15 minutes and ambient light is ≥300 lux, the system must automatically disable designated outlets (e.g., desk lamp, phone charger) within 30 seconds  
Immediately after power cutoff, a push notification must appear in the student’s mobile app within 2 seconds: “Power off: Desk lamp & USB outlet (saved 0.18 kWh)”  
If the student re-enters the room within 5 minutes of cutoff, the system should automatically restore power to previously active devices (with an option for manual override)  
In a 3-day pilot, ≥80% of students report noticing the auto-shutoff feature and agree with the statement: “It helped me save energy without requiring extra effort”

**UI Description (for designers):**  
Home screen → [Energy-Saving Status] card (e.g., “Idle mode active — Saved 0.2 kWh today”)  
Tap to view “Last 3 Auto-Saving Actions” (device name, time, energy saved)  
Settings page → Toggle “Smart Power Zones” on/off (e.g., Desk Zone, Bedside Zone, AC-dedicated outlet)

### Role 2: Dormitory Building Manager
**User Story:**  
As a dormitory building manager, I want the system to provide real-time alerts for abnormal electricity usage patterns, so I can proactively intervene before issues escalate—reducing both energy waste and safety hazards.

**Acceptance Criteria:**  
The system must identify and flag either of the following as “High Risk” within 1 minute:  
   A room consuming >5 W in standby mode while unoccupied (i.e., >1.5× the floor average)  
   Continuous high-power consumption (>200 W) between midnight and 6:00 AM  
Each alert must include room number, current power draw, duration, and inferred device type (e.g., “Likely electric heater”)  
The manager dashboard must generate a daily “Top 5 High-Consumption Rooms” leaderboard, ranked by energy intensity  
In a 1-week pilot, ≥90% of “High Risk” alerts are verified by staff as true positives (not false alarms)

**UI Description (for designers):**  
Admin Dashboard → Floor plan view (color-coded by consumption level: green ≤ average, yellow 1–1.5×, red >1.5×)  
Click any room → Pop-up detail panel showing real-time power curve, last occupancy timestamp, and alert history  
Action Log tab → Allows recording interventions (e.g., “Room 302 inspected — removed unauthorized heating pad”)

### Role 3: Property Manager
**User Story:**  
As a property manager, I want to receive actionable daily energy-saving reports for each dorm unit so I can assess performance, identify improvement opportunities, and use data to motivate all residents to participate in energy conservation.

**Acceptance Criteria:**  
A summary report must be automatically generated and delivered via email/SMS every day at 8:00 AM, including:  
   Total building-wide energy saved that day vs. target achievement rate  
   Top 3 best-performing dorm rooms in energy saving  
   One personalized recommendation (e.g., “B4 Building reduced standby power by 40%—consider promoting their ‘power-off-when-leaving’ habit!”)  
The report must clearly flag “Waste Hotspots”: rooms where electricity consumption during unoccupied periods exceeds 30% of their total usage  
A weekly “Energy-Saving Leaderboard” must be displayed in public areas (e.g., bulletin boards or lobby digital screens), ranked by percentage reduction in standby power consumption (not total energy use) to ensure fair and comparable evaluation  
In the first month of pilot deployment, ≥70% of surveyed residents report having seen the leaderboard and state they adjusted their behavior as a result (e.g., “I now unplug chargers more proactively”)

**UI Description (for designers):**  
Property Management Dashboard → “Energy Insights” Module:  
   Daily Summary Card (date, total building energy saved, “Room of the Week”)  
   Drill-down analytics: Building → Floor → Room → Hourly energy heatmap (overlaid with occupancy status)  
   One-click export button → Generate a PDF report with charts and actionable recommendations  
Public Display Mode → Rotating showcase of “This Week’s Energy Saver” and “Eco Tips” (e.g., “Unplug idle chargers—save 0.05 kWh per day!”)

## 5. Functional Requirements & Features

### 5.1 Core Monitoring (The "Brain")
**FR-01:** The device must automatically monitor human presence (PIR sensor) within the dorm  
**FR-02:** The device must measure ambient light levels to detect daylight or active bulbs  
**FR-03:** The device must detect real-time power status (current draw) of the connected outlet

### 5.2 Alert System
**FR-04: Logic:** If [No Motion] AND [Light On] OR [High Ambient Light] AND [Power Draw > Threshold] → Trigger Alert  
**FR-05: Action:** Trigger immediate audio-visual alert (LED indicator + Buzzer/Chime) and screen notification  
**FR-06:** Alerts must be distinct enough to be noticed but not intrusive enough to disrupt study

### 5.3 Data & Display
**FR-07:** Display real-time energy-saving status on the onboard screen  
**FR-08:** Show a daily count of "Wasted Energy Incidents"  
**FR-09:** Maintain a "Dormitory Energy-Saving Check-in Log" (historical data)

### 5.4 Hardware Constraints
**FR-10: Form Factor:** Portable, compact, suitable for a desk or bedside table  
**FR-11: Setup:** "Plug-and-play" architecture. No complex installation or app configuration

## 6. Initial Architecture (High-Level)
**Input Layer (Sensors):**  
PIR Motion Sensor (Occupancy)  
Photoresistor/Light Sensor (Ambient Light)  
Current Sensor (e.g., CT Clamp or Relay feedback for Power Status)  

**Processing Layer (MCU):**  
Microcontroller (e.g., ESP32 or similar) to process logic: IF (Room Empty && Power On) THEN Alert  

**Output Layer (Feedback):**  
OLED/LCD Screen (Data visualization)  
RGB LED Ring (Visual Status: Green=Good, Red=Waste)  
Piezo Buzzer (Audio Alert)  

**Power:**  
Mains powered (pass-through) or Rechargeable Battery (Portable)  

## 7. Success Metrics (KPIs)
**Onboarding Speed:** Users can set up the device in < 1 minute without reading instructions  
**Usability:** 90% of test users can correctly identify alert signals and perform corrective actions  
**Behavior Change:** Frequency of daily wasted-energy alerts shows a downward trend over time  
**Reliability:** Device operates continuously for 7 days without failure in a live dorm setting  
**User Satisfaction:** 80% of users report that the data display enhances their awareness of energy conservation
