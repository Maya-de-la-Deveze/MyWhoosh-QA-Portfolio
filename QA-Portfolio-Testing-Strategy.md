# MyWhoosh Website

## QA Portfolio Testing Strategy

### Project Type

**Independent QA Portfolio Project**

---

### Purpose

This document describes the testing strategy for my personal QA portfolio.

The goal of this project is not to reproduce MyWhoosh's internal QA process, but to demonstrate a structured and professional approach to software testing by evaluating a real-world product.

All testing activities, documentation, and findings presented in this repository were created independently for educational purposes and to showcase my QA skills.

---

## Scope

This project focuses on testing the public **MyWhoosh website**.

The current scope includes:

- Website navigation (menus, links, breadcrumbs)
- Registration and authentication flows
- Core form functionality and validation
- User interface (UI) consistency, including a visual UI review in Figma (annotated screenshots and "as-is vs. should-be" comparisons)
- User experience (UX) review
- Cross-browser compatibility
- Basic accessibility checks

**Out of scope:**

- MyWhoosh desktop and mobile applications (may be added in a future portfolio update)
- Payment/subscription flows (no access to a test environment with real transactions)
- Backend/API-level testing
- Performance and load testing
- Security penetration testing

**Scope Freeze:**

Note: The menu item in this position was renamed multiple times after the initial test scope had been defined (226 test cases): **"Podcast" → "Blog" → "MyWhoosh Hub"**. The latest rename to **"MyWhoosh Hub"** was observed during Firefox cross-browser testing within the same session.

As this is a learning and portfolio project with a fixed test scope rather than an ongoing production QA effort, this item was intentionally excluded from the test suite and is not covered by testing.

Testing of newly introduced or actively changing functionality falls outside the defined scope of this project. Therefore, the item was not added to the existing test suite. Podcast-related test steps are skipped in subsequent test runs because the original Podcast item is no longer available on the site in its original form.

---

## Testing Objectives

The objectives of this project are to:

- Verify that core user flows (registration, login, navigation) work as expected
- Identify functional defects, broken links, and validation issues in forms
- Evaluate UI consistency across pages (layout, typography, responsiveness)
- Assess UX quality from a new user's perspective (clarity, ease of navigation)
- Confirm consistent behaviour across major browsers
- Check for basic accessibility issues (contrast, alt text, keyboard navigation)
- Document findings using industry-standard formats (test cases, bug reports) to demonstrate professional QA practice

---

## Test Approach

Testing is performed manually, combining two methods:

- **Test-case-based testing** — predefined test cases covering critical user flows (registration, login, navigation, core forms), designed before execution
- **Exploratory testing** — unscripted, time-boxed sessions to uncover UI/UX issues and edge cases not covered by scripted test cases

Both **positive** (expected/valid input) and **negative** (invalid input, edge cases, boundary values) scenarios are covered where applicable.

---
## Test Coverage Matrix

| Feature | Test Artifact |
|---------|---------------|
| **Main Website** | |
| Navigation | Checklist |
| Get Started (How It Works) | Checklist |
| Download | Checklist |
| Routes | Checklist |
| Events | Checklist |
| Results | Checklist |
| Shop | Checklist |
| Workout Builder | Checklist |
| UCI CEWC | Checklist |
| Podcast | Checklist |
| About Us | Checklist |
| Login | Test Cases |
| Registration | Test Cases |
| **Cross-Website** | |
| Cross-Subdomain Navigation | Checklist |
| Cross-Browser Compatibility | Checklist |
| Accessibility | Checklist |
| **Design Review** | |
| UI Consistency | UI Review (Checklist + Figma) |
| UX Evaluation | UX Review (Figma) |

---

## Testing Objectives

The objectives of this project are to:

- Verify that core user flows (registration, login, navigation) work as expected
- Identify functional defects, broken links, and validation issues
- Evaluate UI consistency across pages
- Assess user experience from a new user's perspective
- Confirm consistent behaviour across major browsers
- Identify basic accessibility issues
- Document findings using professional QA documentation

---

## Test Approach

Testing is performed manually using a combination of two complementary methods.

### Test Case-Based Testing

Predefined test cases covering critical user flows such as registration, login, navigation, and form validation.

### Exploratory Testing

Time-boxed exploratory sessions used to identify usability issues, unexpected behaviour, UI inconsistencies, and edge cases that may not be covered by scripted test cases.

Testing was performed from the perspective of an end user interacting with the publicly available website.

Both **positive** (valid input) and **negative** (invalid input, edge cases, and boundary values) scenarios are covered where applicable.

---

## Tools & Deliverables

| Purpose | Tool |
|----------|------|
| Test case management | Qase |
| Bug tracking | Jira |
| Task management | Trello |
| Repository hosting | GitHub |
| Browser inspection & debugging | Chrome DevTools |

### Deliverables

This project currently includes:

- Website structure documentation
- QA Portfolio Testing Strategy
- Product Analysis
- Test cases
- Bug reports
- Test summary report

---

## Test Environment

### Hardware

- MacBook Air M3

### Operating System

- macOS Tahoe 26.5.2

### Browsers

- Google Chrome 150.0.7871.115
- Safari 26.5.2
- Mozilla Firefox 152.0.5

### Devices

- Desktop

---

## Assumptions & Limitations

- Testing is limited to the publicly accessible MyWhoosh website; no access to staging/test environments or backend systems
- Real payments and account-sensitive actions (e.g. subscription purchase) are not executed
- Findings reflect the site's behaviour at the time of testing and may not remain accurate if the site is updated afterward
- This is an independent learning project, not affiliated with or commissioned by MyWhoosh

## Out of Scope

The following testing types are explicitly excluded from this project on ethical and 
legal grounds, as this testing is conducted against a live production site without 
authorization from MyWhoosh:

- **Security testing** (e.g. SQL injection, XSS, penetration testing) — not performed, 
  as exploiting vulnerabilities on an unauthorized third-party system is illegal 
  regardless of intent.
- **Load/performance testing** (e.g. stress testing, spike testing) — not performed, 
  as generating artificial load against production infrastructure without authorization 
  could disrupt service for real users and carries similar legal risk.

This project focuses on functional, UI/UX, and accessibility testing only, which does 
not interfere with or compromise the platform's normal operation.
