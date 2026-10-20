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

### Scope

This project focuses on testing the public **MyWhoosh website**.

The current scope includes:

- Website navigation (menus, links, breadcrumbs)
- Registration and authentication flows
- Navigation and login state across subdomains (`event.`, `workout.`, `store.`, `results.`, `uci.`), including access to Workout Builder
- Core form functionality and validation
- Shop: product options, cart and wishlist (no orders are placed)
- Results: search, filters and results data
- Download page
- User interface (UI) consistency, including a visual UI review in Figma (annotated screenshots with the expected result described for each issue)
- User experience (UX) review
- Cross-browser compatibility (Chrome, Safari and Firefox on macOS)
- Mobile web (Safari on iPhone)
- Basic accessibility checks

**Out of scope:**

- MyWhoosh desktop and mobile applications (may be added in a future portfolio update)
- Smart trainer and hardware integration
- Payment/subscription flows (no access to a test environment with real transactions)
- Backend/API-level testing

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

#### Scope Freeze

Note: The main menu item in this position changed several times after the initial checklist scope had been defined (226 checklist items): **"Podcast" → "Blog" → "MyWhoosh Hub"**. The latest change to **"MyWhoosh Hub"** was observed during Firefox cross-browser testing within the same session. "Blog" and "MyWhoosh Hub" open the same page; the Podcast page itself still exists and is linked from the footer and from the headers of some subdomains.

As this is a learning and portfolio project with a fixed test scope rather than an ongoing production QA effort, the original Podcast checklist is kept as a frozen baseline but is not executed.

Testing of newly introduced or actively changing functionality falls outside the defined scope of this project. Therefore, MyWhoosh Hub was not added to the test suite, and Podcast checks are marked as Skipped in test runs.

Other sections that changed during the project (e.g. UCI CEWC, Workout Builder, Results, the footer) were updated in the checklists to match the site as of October 2026.

---

### Testing Objectives

The objectives of this project are to:

- Verify that core user flows (registration, login, navigation, shopping cart) work as expected
- Verify that login state and navigation work consistently across MyWhoosh subdomains
- Identify functional defects, broken links, validation issues in forms, and incorrect data or calculations
- Evaluate UI consistency across pages (layout, typography, responsiveness)
- Assess UX quality from a new user's perspective (clarity, ease of navigation)
- Confirm consistent behaviour across major browsers and on mobile (iPhone)
- Check for basic accessibility issues (contrast, alt text, keyboard navigation)
- Document findings using industry-standard formats (checklists, test cases, exploratory session notes, bug reports) to demonstrate professional QA practice

---

### Test Approach

Testing is performed manually, combining three complementary methods:

- **Checklist-based testing** — checklists covering the website pages and features
- **Test-case-based testing** — predefined test cases covering critical user flows with validation rules or multiple steps (login, registration, shopping cart, contact form), designed before execution
- **Exploratory testing** — time-boxed sessions used to identify usability issues, unexpected behaviour, UI inconsistencies, and edge cases that may not be covered by scripted test cases

As no requirements specification is available, expected results are based on user expectations, common user experience and consistency within the product.

Testing is performed from the perspective of an end user interacting with the publicly available website.

Both **positive** (valid input) and **negative** (invalid input, edge cases, and boundary values) scenarios are covered where applicable.

---
### Test Coverage Matrix

| Feature | Test Artifact | Execution |
|---------|---------------|-----------|
| **Main Website** | | |
| Navigation | Checklist | Executed |
| Get Started (How It Works) | Checklist | Not executed |
| Download | Checklist | Executed |
| Routes | Checklist | Not executed |
| Events | Checklist | Not executed |
| Results | Checklist | Executed |
| Shop | Checklist, Test Cases (TC-SHOP), Exploratory (ES-01 – ES-04) | Partially executed |
| Contact Form | Checklist, Test Cases (TC-CONTACT) | Executed |
| Workout Builder | Checklist | Executed |
| UCI CEWC | Checklist | Not executed |
| Podcast | Checklist | Frozen baseline |
| About Us | Checklist | Not executed |
| Home Page Footer | Checklist | Not executed |
| Login | Test Cases | Executed |
| Registration | Test Cases, Exploratory (ES-05, ES-07) | In progress |
| **Cross-Website** | | |
| Subdomain Integration | Checklist, Exploratory (ES-05, ES-06, ES-08) | Executed |
| Cross-Browser Compatibility | Checklist | Executed |
| Mobile Web | Checklist | Executed |
| Accessibility | Checklist | Executed |
| **Design Review** | | |
| UI Consistency | UI Review | Planned |
| UX Evaluation | UX Review | Planned |

**Executed** — all checks of the section are run in this cycle. 

**Partially executed** — only the subsections marked as included in the checklist are run. 

**Not executed** — the checklist documents the area but is not run in this cycle. 

**Frozen baseline** — see Scope Freeze.

---

### Tools

| Purpose | Tool |
|----------|------|
| Checklists and test cases | Qase |
| Test runs | Qase (results are exported after each run and stored in the repository) |
| Bug tracking | Jira |
| Repository hosting | GitHub |
| Browser inspection & debugging | Chrome DevTools, Safari Web Inspector, Firefox DevTools |
| Accessibility checks | axe DevTools, Lighthouse, macOS VoiceOver |
| UI review (annotated screenshots) | Figma |

All project documents and their status are listed in the [README](README.md).

---

### Test Environment

#### Hardware

- MacBook Air M3
- iPhone 12 Pro

#### Operating System

- macOS Tahoe 26.6.2
- iOS 26.6.2

#### Browsers

- Google Chrome 155.0.8059.41
- Safari 26.6.2
- Mozilla Firefox 158.0
- Safari on iOS 26.6.2

#### Browser Matrix

| Browser | Device | What is executed |
|---------|--------|------------------|
| Chrome | MacBook | Full execution scope |
| Safari | MacBook | Areas that depend on cookies and session (Login test cases, Subdomain Integration, Shop cart and Wishlist, Workout Builder), the Cross-Browser smoke set, and a re-check of every bug found in Chrome |
| Firefox | MacBook | Cross-Browser smoke set and a re-check of every bug found in Chrome |
| Safari | iPhone 12 Pro | Mobile Web |

The depth of testing is chosen by risk. Website logic (filters, calculations, links) works the same in every browser, so it is fully tested in Chrome only. Safari handles cookies more strictly, so it covers the areas that rely on cookies and session. Firefox gets a short smoke set. Browsers update automatically; the exact versions are recorded with each test run.

---

### Assumptions & Limitations

- Testing is limited to the publicly accessible MyWhoosh website; no access to staging/test environments or backend systems
- Real payments and account-sensitive actions (e.g. subscription purchase) are not executed; no orders are placed, and the Checkout page for logged-in users is not tested
- Valid messages are not submitted through the Contact form, as they would reach the real MyWhoosh support team; only form validation is checked
- Only one personal test account is available; test cases that need other account types (e.g. an inactive or disabled account) are marked as Blocked
- Findings reflect the site's behaviour at the time of testing and may not remain accurate if the site is updated afterward. The site changed several times during the project (main menu, footer, UCI CEWC, Workout Builder); these changes are documented with the date they were noticed, and findings from the test runs are recorded with the date and a screenshot
- Test run results are not stored permanently on the Qase free plan, so they are exported after each run and kept in the repository
- This is an independent learning project, not affiliated with or commissioned by MyWhoosh
