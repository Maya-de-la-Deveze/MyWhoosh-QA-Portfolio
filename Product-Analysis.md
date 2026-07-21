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

### Main Website

- Get Started
- Download
- Routes
- Events
- Results
- Shop
- Workout Builder
- UCI CEWC
- Podcast
- About Us
- Login

### MyWhoosh Web Ecosystem

**Main Website**
mywhoosh.com


**Results**
├── results.mywhoosh.com
   

**Shop**
├── store.mywhoosh.com
   

**Workout Builder**
├── workout.mywhoosh.com
   

**UCI CEWC**
├── uci.mywhoosh.com
   

**Authentication / User Account**
└── event.mywhoosh.com
   

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

## Primary User Flows

### Get Started

***Homepage → Get Started → Learn how to start using MyWhoosh***

**Available sections**

- Get the App
- The Essentials
- Start Riding
- What's New

**QA Observation**

The Get Started page serves as an onboarding guide for new users rather than providing standalone functionality.

It explains the setup process, introduces the required equipment, and guides users toward downloading the application. Multiple "Download App" call-to-action buttons are available throughout the page.

### Download

***Homepage → Download → Select platform → Download application***

**Available platforms**

- iOS
- Android
- Windows (MyWhoosh)
- Windows (MyWhoosh HD)
- macOS
- Apple TV
- Link App iOS
- Link App Android

**QA Observation**

The Download page provides installation packages for all supported platforms.

Users select the required platform and download the appropriate application. No authentication is required.

### Routes

***Homepage → Routes → Select destination → View route information***

**Available sections**

- France
- Bhutan
- Japan
- UCI
- MyWhoosh World
- Switzerland
- California
- Hudayriyat
- Arabia
- Colombia

**QA Observation**

The Routes page presents all available virtual riding destinations.

Each destination has a dedicated page containing a general description, route statistics, and a table listing the available routes with distance and elevation information.

No authentication is required to browse the available routes.

### Events

***Homepage → Events → Select event → Event Details → Register Now → Sign In / Create New Account***

**Available sections**

- Upcoming Events
- Event Details
- Event Information
- Registration

**QA Observation**

The Events page displays a list of upcoming events available on the MyWhoosh platform.

Selecting an event opens a dedicated event page containing the event information and a registration option.

Users can browse all public event information without authentication. However, registering for an event requires signing in to an existing account or creating a new account.

### Results

***Homepage → Results → Select event → View Results***

**Available sections**

- Event Results
- Search
- Filters
- Categories
- Stage Results
- Individual Rankings

**QA Observation**

The Results page provides access to public race results without requiring authentication.

Users can browse completed events, open detailed results for a selected event, search for participants, filter results, switch between categories, and view stage-specific rankings.

### Shop

***Homepage → Shop → Browse products***

**Available sections**

- Product Categories
- Product Details
- Search
- Wishlist
- Shopping Cart
- Contact Us

**QA Observation**

The Shop is hosted on a dedicated subdomain (`store.mywhoosh.com`) and functions as a standalone e-commerce website within the MyWhoosh ecosystem.

Users can browse products without authentication. Shopping features such as the wishlist, account management, and checkout require user authentication.

### Workout Builder

***Homepage → Workout Builder → Login page***

**Available sections**

- Workouts
- My Training Plans
- Marketplace
- Subscriptions

**QA Observation**

The Workout Builder is hosted on a dedicated subdomain. Selecting any available section opens the Workout Builder website, where unauthenticated users are redirected to the login page before they can access the available features.

### UCI CEWC

***Homepage → 2025 UCI CEWC***

**Available sections**

- 2025 UCI CEWC
- Explore Abu Dhabi
- Event Details
- Event Gallery
- Results
- Watch Replay

**QA Observation**

The UCI CEWC section combines content hosted within the MyWhoosh website and external resources.

- **Explore** redirects users to the dedicated UCI CEWC website.
- **Watch Replay** opens the official UCI event page.
- **View Full Results** opens the official UCI results page in a new browser tab.
- The section uses a dedicated secondary navigation menu that differs from the main website navigation.

### Podcast

***Homepage → Podcast***

**Available sections**

- Featured podcast
- Podcast episodes
- Apple Podcasts
- Spotify
- YouTube

**QA Observation**

The page displays the latest podcast followed by a list of episodes. Each episode has its own page with an embedded player and links to Apple Podcasts, Spotify, and YouTube.

### About Us

***Homepage → About Us***

**Available sections**

- About MyWhoosh
- Leadership

**QA Observation**

The **About Us** menu is implemented as a dropdown in the main navigation. Selecting either option opens its corresponding information page.

### Login

***Homepage → Login***

**Available sections**

- Email address
- Password
- Forgot Password
- Stay signed in
- reCAPTCHA verification
- Submit
- Create New Account

**QA Observation**

The Login page allows existing users to sign in using their MyWhoosh account. Users can recover a forgotten password or navigate to the account registration page if they do not already have an account.









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
