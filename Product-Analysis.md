# MyWhoosh Website

## Product Analysis

### Product Overview

MyWhoosh is a virtual sports platform that allows users to train indoors using connected fitness equipment.

The platform supports cycling, running, and rowing, providing virtual routes, structured workouts, races, and community events.

**Website**

https://mywhoosh.com

**Company**

MyWhoosh

**Headquarters**

Abu Dhabi, United Arab Emirates

**Supported Platforms**

- Windows
- macOS
- iOS
- Android

**Business Model**

Free-to-download application with progression mechanics such as Levels, XP, Season Pass, and unlockable items.

---

## Target Audience

- Indoor cyclists
- Competitive cyclists
- Triathletes
- Rowers
- Beginners

---

## Core Features

### Rowing Mode

Indoor rowing with performance tracking. Supports Concept2 and FTMS-compatible rowing machines.

### Triathlon Mode

Dual-login bike/run transitions designed for triathlon events.

### Workout Builder

Create, import, and manage custom workouts through the website with synchronization to the application.

### Virtual Gear Shifting (MyShift)

Thirty virtual gears controlled via the MyWhoosh Link App or directly in the game.

### Speed Sensor Mode

Allows users to ride without a smart trainer using speed-to-power algorithms.

### Heads-Up Display (HUD)

Displays real-time ride information during Free Ride, Workouts, and Events.

### Link App Integration

Allows users to start and manage workouts remotely.

### Calendar & Workout Management

Supports scheduling, rescheduling, and restoring missed workouts.

### Day / Night Mode

Automatic or manual environment lighting based on the user's local time.

### Data Migration

Allows riders to transfer their profile level and rating from supported platforms.

### Offline Mode

Continues recording rides locally during temporary connection loss.

### Data Recovery

Temporarily stores ride data server-side after crashes or unexpected disconnections.

---

## Website Structure

### Main Website

- Get Started
- Download
- Routes
- Events
- Results
- Podcast
- About MyWhoosh
- Leadership

### Separate Services

- Shop (store.mywhoosh.com)
- Workout Builder (workout.mywhoosh.com)
- UCI CEWC (uci.mywhoosh.com)
- Account & Login (event.mywhoosh.com)

---

## QA Notes

The MyWhoosh ecosystem consists of the main website and multiple independent subdomains.

This architecture introduces additional testing scenarios, including:

- Cross-subdomain navigation
- Session persistence
- Login state consistency
- Link integrity
- User experience consistency across services

---

## Key User Flows

### Onboarding

Homepage → Get Started → Download → Device compatibility

### Account

Registration → Login → Profile → Logout

### Workout Builder

Create workout → Save → Export → Synchronization information

### Events

Browse events → Open event details → Registration flow

### Shop

Navigate to Shop → Browse products → Cart (navigation only)

### Newsletter

Subscribe → Form validation → Confirmation

### Cross-Subdomain Navigation

Verify navigation between:

- mywhoosh.com
- event.mywhoosh.com
- workout.mywhoosh.com
- store.mywhoosh.com

---

## Out of Scope

The following areas are not included in this portfolio:

- Native desktop application functionality
- Native mobile application functionality
- Smart trainer and hardware integration
- Payment processing
- Backend and API testing

---

## Testing Priorities

### High Priority

- Navigation
- Registration
- Login
- Download flow
- Newsletter validation

### Medium Priority

- Events
- Routes
- Cross-subdomain navigation

### Low Priority

- About pages
- Leadership
- Podcast

---

This analysis serves as the foundation for the Checklists, Test Cases, Bug Reports, UI/UX Reviews, Accessibility Review, and Final Test Report included in this portfolio.
