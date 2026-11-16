# MyWhoosh Website

## Product Analysis

*The website is described as of October–November 2026. Changes noticed during the project are listed in the [Testing Strategy](QA-Portfolio-Testing-Strategy.md#scope-freeze).*

---

### Product Overview

MyWhoosh is a virtual sports platform for indoor training with connected fitness equipment. It supports cycling, running and rowing, with virtual routes, structured workouts, races and community events.

| Parameter | Details |
|:---|:---|
| **Website** | [mywhoosh.com](https://mywhoosh.com) |
| **Headquarters** | Abu Dhabi, United Arab Emirates |
| **Platforms (app)** | Windows, macOS, iOS, Android, Apple TV |
| **Business model** | Free-to-download app with progression mechanics (Levels, XP, Season Pass, unlockable items) |

**Target audience:** indoor and competitive cyclists, triathletes, rowers, beginners.

#### Product Context

Most product features live in the **application**, which is out of scope: Rowing and Triathlon modes, virtual gear shifting (MyShift), Speed Sensor mode, heads-up display, Link App, calendar and workout management, Day/Night mode, data migration, offline mode and ride data recovery.

The **website** supports the app. It helps users get started and download the app, browse routes and events, view results, build workouts, buy merchandise and manage their account. This portfolio tests the website only.

---

### Web Ecosystem

The website consists of the main site and several independent subdomains.

| Area | Domain | Login required |
|------|--------|----------------|
| Main website | `mywhoosh.com` | No |
| Authentication / user account | `event.mywhoosh.com` | — |
| Results | `results.mywhoosh.com` | No |
| Shop | `store.mywhoosh.com` | For the account page and checkout |
| Workout Builder | `workout.mywhoosh.com` | For all sections (the start page is public) |
| UCI CEWC | `uci.mywhoosh.com` | No |

#### QA Notes

This architecture creates risks that a single-domain site does not have:

- Navigation between subdomains and back
- Login state consistency (the user stays logged in on every subdomain after one login)
- Logout on one subdomain and its effect on the others
- Redirect to the login page and return to the requested page
- Link integrity and a consistent user experience across subdomains (headers and footers differ)

These risks are the main reason why **Subdomain Integration** is one of the executed focus areas (see the [Test Coverage Matrix](QA-Portfolio-Testing-Strategy.md#test-coverage-matrix)).

---

### Main Website Navigation

- Get Started
- Download
- Routes
- Events
- Results
- Shop
- Workout Builder
- UCI CEWC
- MyWhoosh Hub *(previously "Podcast", then "Blog"; see [Scope Freeze](QA-Portfolio-Testing-Strategy.md#scope-freeze))*
- About Us
- Login

---

### Primary User Flows

#### Get Started

***Homepage → Get Started → Learn how to start using MyWhoosh***

**Sections:** Get the App · The Essentials · Start Riding · What's New

**QA observation:** The page is an onboarding guide rather than standalone functionality. It explains the setup process, introduces the required equipment and leads users to download the app. Several "Download App" buttons appear on the page.

#### Download

***Homepage → Download → Select platform → Download application***

**Platforms:** iOS · Android · MyWhoosh (Windows) · MyWhoosh HD (Windows) · macOS · Apple TV · Link App iOS · Link App Android

**QA observation:** Desktop platforms start a file download. Mobile and Apple TV platforms open the app store. No login is required.

#### Routes

***Homepage → Routes → Select destination → View route information***

**QA observation:** The side menu lists all destinations. Each destination has a page with a description, route statistics (total routes, distance and elevation gain) and a table of routes with distance and elevation. No login is required.

#### Events

***Homepage → Events → Select event → Event details → Register Now → Sign In / Create New Account***

**QA observation:** Public event information is available without login. Registering for an event requires signing in or creating an account. Only the events listing page is in the checklist scope.

#### Results

***Homepage → Results → Select event → View Results***

**Sections:** Results list (gender, search, category and date filters) · Event results (days, checkpoints, categories, participant search)

**QA observation:** Public race results are available without login. Users can filter events, open the results of an event, switch between days, checkpoints and categories, and search for participants.

#### Shop

***Homepage → Shop → Product page → Cart***

**Sections:** Shop home · Product categories · Product page · Mini cart · Cart · Checkout · Order tracking · Search · Wishlist · Account · Contact

**QA observation:** The shop is a standalone e-commerce site on `store.mywhoosh.com`. Products can be browsed and added to the cart and wishlist without login. Checkout and the account page require a MyWhoosh account; for a guest, checkout shows "Login Required". No orders are placed in this project.

#### Workout Builder

***Homepage → Workout Builder → Select section → Sign In → Section***

**Sections:** Workouts · My Training Plans · MarketPlace · Subscriptions

**QA observation:** The Workout Builder start page opens without login and shows the four section cards. Opening any section requires login; a guest is sent to the MyWhoosh Sign In page.

#### UCI CEWC

***Homepage → UCI CEWC***

**Sections:** 2026 UCI CEWC · Event Details · Event Gallery · Results

**QA observation:** The section has its own header navigation, which differs from the main website. "Explore" opens the 2026 UCI CEWC page, and the highlighted button next to the menu opens the Event Gallery. The content changes with each championship.

#### MyWhoosh Hub and Podcast *(frozen baseline)*

***Homepage → MyWhoosh Hub***

**QA observation:** "Blog" and "MyWhoosh Hub" open the same page. The Podcast page still exists and is linked from the footer and from the headers of some subdomains. The Podcast checklist is kept as a frozen baseline and is not executed (see [Scope Freeze](QA-Portfolio-Testing-Strategy.md#scope-freeze)).

#### About Us

***Homepage → About Us → About MyWhoosh / Leadership***

**QA observation:** About Us is a dropdown in the main navigation. Each option opens its own information page.

#### Login

***Homepage → Login (`event.mywhoosh.com`)***

**Elements:** Email Address · Password · Forgot Password? · reCAPTCHA · Submit · Stay signed in · Create New Account?

**QA observation:** Existing users sign in with their MyWhoosh account. The "Submit" button is enabled by default. Users can recover a password or open the registration page.

#### Registration

***Homepage → Login → Create New Account? → Registration form → Verification email → Account verified***

**Fields:** First Name · Last Name · Email Address · Gender · Password · Confirm Password · Country · Date of birth · Weight (kg) · Height (cm) · consent to the Privacy Notice and Terms & Conditions · newsletter (optional) · reCAPTCHA

**QA observation:** The "Submit" button is enabled only after the consent checkbox is selected and the reCAPTCHA verification is completed. After registration, the account is verified through a link in the email. Registration is also reached from event registration ("Register Now") and from pages that require login.

---

### Known Requirements

No requirements specification is available. The following requirements are published in the MyWhoosh **Terms & Conditions** (checked on 12 November 2026) and are used as the basis for expected results in the [Test Cases](Test-Cases.md):

- Users must be at least **6 years** old.
- Users aged **6 to 18** may register only with **parental consent**, which is verified through the parent's email address. If consent is not given within one week, the child account data is deleted.
- Registration requires an email address, age, gender, country, height and weight.
- Login credentials must be kept confidential.

Where no requirement is published, expected results are based on user expectations, common user experience and consistency within the product (see the [Testing Strategy](QA-Portfolio-Testing-Strategy.md#test-approach)).

---

### Testing Priorities

| Priority | Areas |
|----------|-------|
| **High** | Login · Registration · Subdomain Integration (navigation and login state) · Shop cart (product page, mini cart, cart, guest checkout) · Main navigation · Download |
| **Medium** | Workout Builder access · Mobile web · Cross-browser smoke checks · Basic accessibility · Results |
| **Low** | Get Started · Routes · Events · UCI CEWC · About Us · Home page footer · Shop search, wishlist and account · MyWhoosh Hub / Podcast *(frozen)* |

All High and Medium areas are executed in this cycle, except Results. Low areas are documented in the checklists but not executed. The execution scope is defined in the [Test Coverage Matrix](QA-Portfolio-Testing-Strategy.md#test-coverage-matrix); the scope and out-of-scope areas are described in the [Testing Strategy](QA-Portfolio-Testing-Strategy.md#scope).

---

This analysis is the basis for the Checklists, Test Cases, Bug Reports, UI and UX Reviews, Accessibility Review and Final Test Report in this portfolio.
