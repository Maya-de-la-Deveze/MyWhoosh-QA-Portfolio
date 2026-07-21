# MyWhoosh Website

## QA Checklist

*Based on the testing scope and priorities defined in the [Product Analysis](Product-Analysis.md) and [QA Portfolio Testing Strategy](QA-Portfolio-Testing-Strategy.md).*

### Table of Contents

- [Navigation](#navigation)
- [Get Started (How It Works)](#get-started-how-it-works)
- [Download](#download)
- [Subdomain Integration](#subdomain-integration)
- [Routes](#routes)
- [Results](#results-resultsmywhooshcom)
- [Shop](#shop-storemywhooshcom)
- [Workout Builder](#workout-builder-workoutmywhooshcom)
- [UCI Cycling Esports World Championships](#uci-cycling-esports-world-championships)
- [Podcast](#podcast)
- [Home Page Footer](#home-page-footer)
- [Cross-Browser Compatibility](#cross-browser-compatibility)
- [Accessibility](#accessibility)

---

## **Navigation**

- [ ] All main menu items are clickable and lead to the correct page
- [ ] Logo redirects to the homepage from any page
- [ ] No broken links (404) are found in the main navigation
- [ ] Navigation remains consistent across the main website

> **Note:** Footer link verification is covered separately in the [Home Page Footer](#home-page-footer) section.

---

> **Note:** Authentication flows (Login and Registration) and Event registration are covered by dedicated [Test Cases](Test-Cases.md) due to their validation rules and multi-step workflows.

---
## **Get Started (How It Works)**

- [ ] Get Started page loads successfully
- [ ] Platform download buttons navigate to the correct destination
- [ ] Bike / Devices / Smart Trainer / Dictionary tabs switch content correctly
- [ ] Content updates correctly when switching between tabs
- [ ] Carousel navigation works correctly
- [ ] Carousel displays all available slides
- [ ] Partner logos are displayed
- [ ] Partner logo links navigate to the correct external websites
- [ ] External links open correctly
- [ ] Page is accessible without authentication

---

## **Download**

- [ ] All supported platforms are listed (iOS, Android, Windows, Windows HD, macOS, Apple TV, Link App iOS, Link App Android)
- [ ] Desktop download buttons start downloading the correct installer
- [ ] Mobile platform buttons redirect to the correct App Store or Google Play page
- [ ] Download page is accessible without authentication
- [ ] Download page displays correctly in tested desktop browsers


---

## **Subdomain Integration**

MyWhoosh Web Ecosystem:

- Main Website — `mywhoosh.com`
- Results — `results.mywhoosh.com`
- Shop — `store.mywhoosh.com`
- Workout Builder — `workout.mywhoosh.com`
- UCI CEWC — `uci.mywhoosh.com`
- Authentication / User Account — `event.mywhoosh.com`

Checks:

- [ ] Navigation from `mywhoosh.com` to `store.mywhoosh.com` works correctly
- [ ] Navigation from `mywhoosh.com` to `workout.mywhoosh.com` works correctly
- [ ] Navigation from `mywhoosh.com` to `results.mywhoosh.com` works correctly
- [ ] Navigation from `mywhoosh.com` to `uci.mywhoosh.com` works correctly
- [ ] Login redirects users to the `event.mywhoosh.com` authentication page when required
- [ ] User session is handled correctly when navigating between subdomains
- [ ] Browser Back button behaves correctly after switching between subdomains
- [ ] Cross-subdomain links are functional

---

## **Routes**

- [ ] Routes page loads successfully
- [ ] Each listed route opens its corresponding route page
- [ ] Route title is displayed
- [ ] Route description is displayed
- [ ] Route distance is displayed
- [ ] Route elevation is displayed
- [ ] Route image is displayed
- [ ] Partner logos are displayed on route pages
- [ ] Partner logo links open the correct external websites
- [ ] Routes can be viewed without authentication

---

## **Results** (results.mywhoosh.com)

### Results List

- [ ] Results page loads without authentication
- [ ] Gender switch (Men/Women) updates the displayed results
- [ ] Event search returns relevant results
- [ ] Empty search displays an appropriate message
- [ ] Category filter updates the displayed events
- [ ] Date filter updates the displayed events
- [ ] Event cards display required information
- [ ] "View Results" opens the corresponding event results page
- [ ] Pagination navigation works correctly

### Event Results

> **Note:** Due to the educational scope of this portfolio project, detailed functional verification was performed on one representative event results page.

- [ ] Event results page loads successfully
- [ ] Event title is displayed
- [ ] Ranking tabs (Individual, Master, Youth, GCC, Teams, Sprint Winner, King of the Mountain) switch correctly
- [ ] Player search returns relevant results
- [ ] Empty player search displays an appropriate message
- [ ] Category filter updates the displayed results
- [ ] Day selector updates the displayed results
- [ ] Reset button clears all applied filters
- [ ] Ranking table displays participant information correctly
- [ ] Pagination navigation works correctly
- [ ] Filters work correctly when used in combination

---

> **Note:** UI consistency and UX evaluation are documented separately in the Figma-based [UI Review](UI-Review.md) and [UX Review](UX-Review.md).

---

## **Shop** (store.mywhoosh.com)

### *Landing Page*

#### Header

- [ ] Home link opens the Home page
- [ ] Shop link opens the Shop page
- [ ] Contact link opens the Contact page
- [ ] Logo redirects to the Home page
- [ ] Search opens the search function
- [ ] Wishlist opens the Wishlist page
- [ ] Account opens the login/account page


#### Hero Section

- [ ] Shop Collection button opens the Shop page


#### Products Carousel

- [ ] Product cards open the corresponding product pages


#### Collections

- [ ] Men Collection card opens the Men's collection page
- [ ] Women Collection card opens the Women's collection page


#### Featured Products

- [ ] Featured Product cards open the corresponding product pages


#### Jerseys

- [ ] Men's Jersey card opens the corresponding product page
- [ ] Women's Jersey card opens the corresponding product page


#### Top Rating

- [ ] Top Rating product cards open the corresponding product pages


#### Footer

- [ ] Footer links navigate to the correct pages


### *Categories*

- [ ] Product categories can be opened
- [ ] Activewear category opens correctly
- [ ] Clothing category opens correctly
- [ ] Women category opens correctly
- [ ] Men category opens correctly
- [ ] Switching between categories updates the product list

### *Product Page*

- [ ] Product page opens successfully
- [ ] Product color can be selected
- [ ] Product size can be selected
- [ ] HS Code can be selected
- [ ] Product availability is updated after selecting the required options
- [ ] Product quantity can be increased
- [ ] Product quantity can be decreased
- [ ] Add to Cart button adds the product to the cart
- [ ] Buy It Now button proceeds to the checkout flow
- [ ] Add to Wishlist button adds the product to the wishlist
- [ ] Product category links open the corresponding category pages
- [ ] Product description section is displayed
- [ ] Facebook button redirects to the Facebook authorization/login page
- [ ] Twitter/X button redirects to the Twitter/X authorization/login page

### *Shopping Cart Functionality*

#### Shopping Cart Icon

- [ ] Shopping Cart counter is updated after adding a product
- [ ] Shopping Cart counter displays the correct number of products across all pages
- [ ] Clicking the Shopping Cart icon opens the Mini Cart

#### Mini Cart

- [ ] Added product is displayed in the Mini Cart
- [ ] Selected product color is displayed
- [ ] Selected product size is displayed
- [ ] Selected HS Code is displayed
- [ ] Product quantity is displayed correctly
- [ ] Product unit price is displayed correctly
- [ ] Total price is calculated correctly
- [ ] View Cart button opens the Shopping Cart page
- [ ] Checkout button redirects unauthenticated users to the login/registration page
- [ ] Shopping Cart tab opens the Shopping Cart page
- [ ] Checkout tab redirects unauthenticated users to the login/registration page
- [ ] Order Tracking tab opens the Order Tracking page

#### Shopping Cart Page

- [ ] Shopping Cart page opens successfully
- [ ] Added product is displayed in the shopping cart
- [ ] Selected product color is displayed
- [ ] Selected product size is displayed
- [ ] Selected HS Code is displayed
- [ ] Product unit price is displayed correctly
- [ ] Product quantity can be increased
- [ ] Product quantity can be decreased
- [ ] Product subtotal is updated after changing the quantity
- [ ] Update Cart recalculates the cart total
- [ ] Product can be removed from the shopping cart
- [ ] Empty cart message is displayed after removing all products

---

### *Checkout*

- [ ] Proceed to Checkout redirects unauthenticated users to the login/registration page
- [ ] Apple Pay button opens the Apple Pay authorization flow
- [ ] Google Pay button opens the Google Pay authorization flow

> **Note:** Payment authorization and order placement are out of scope for this portfolio project.

---

### *Order Tracking*

- [ ] Order Tracking page opens successfully
- [ ] Order ID field accepts input
- [ ] Billing Email field accepts input
- [ ] Submit button submits the form
- [ ] Validation is displayed for empty required fields

> **Note:** Full order tracking verification requires an existing order, which is out of scope for this portfolio project.

---

### *Search*
- [ ] Search returns relevant products
- [ ] Empty search displays an appropriate message

### *Wishlist*
- [ ] Wishlist requires authentication
- [ ] Unauthenticated users are redirected to the login page

### *Account*
- [ ] Account page requires authentication
- [ ] Unauthenticated users are redirected to the login page
- [ ] Authenticated users can access the Account page

> **Note:** Purchase history verification is out of scope for this portfolio project.

---


## **Workout Builder** (workout.mywhoosh.com)

- [ ] Unauthenticated users are redirected to the Login page
- [ ] After successful login, users return to the originally requested page
- [ ] Workouts section loads correctly for authenticated users
- [ ] My Training Plans section loads correctly
- [ ] Marketplace section loads correctly
- [ ] Subscriptions section loads correctly
- [ ] Visual style is consistent with the main website

---

## **UCI Cycling Esports World Championships** (uci.mywhoosh.com)


### *Header Navigation*

- [ ] 2025 UCI CEWC page opens correctly
- [ ] Explore Abu Dhabi page opens correctly
- [ ] Event Details page opens correctly
- [ ] Event Gallery page opens correctly
- [ ] Results page opens correctly
- [ ] Watch Replay button opens the replay page


### *Hero Section*

- [ ] Event date and time are displayed
- [ ] Event location is displayed
- [ ] Explore button opens the Explore Abu Dhabi page


### *Latest Results*

- [ ] Final tab displays the Final results
- [ ] Semi Final tab displays the Semi Final results
- [ ] Men tab displays the Men's results
- [ ] Women tab displays the Women's results
- [ ] View Full Results button opens the Results page


### *Latest Updates*

- [ ] Latest Updates section is displayed
- [ ] Timeline items are displayed


### *Social Media*

- [ ] Facebook link opens the official Facebook page
- [ ] LinkedIn link opens the official LinkedIn page
- [ ] Instagram link opens the official Instagram page
- [ ] X (Twitter) link opens the official X page
- [ ] YouTube link opens the official YouTube channel
- [ ] Strava link opens the official Strava page
- [ ] Twitch link opens the official Twitch channel


### *Download*

- [ ] Download Now button opens the download page


### *Partners*

- [ ] Shimano logo opens the partner website
- [ ] Tissot logo opens the partner website
- [ ] Santini logo opens the partner website


### *Footer*

- [ ] FAQ page opens correctly
- [ ] Contact Us page opens correctly

---

## *Podcast*

### *Podcast Landing*

- [ ] Podcast page loads successfully
- [ ] Podcast subscription links are displayed
- [ ] Apple Podcasts link opens the official podcast page
- [ ] Spotify link opens the official podcast page
- [ ] YouTube link opens the official podcast page


### *Episode Links*

- [ ] Apple Podcasts link opens the episode on Apple Podcasts
- [ ] Spotify link opens the episode on Spotify
- [ ] YouTube link opens the episode on YouTube


### *Episodes*

- [ ] Featured episode is displayed
- [ ] Episode list is displayed
- [ ] Episode page opens correctly
- [ ] Podcast episode can be played
- [ ] Episode description is displayed


### *Share*

- [ ] Share buttons are displayed
- [ ] Facebook share link opens correctly
- [ ] X (Twitter) share link opens correctly
- [ ] LinkedIn share link opens correctly
- [ ] WhatsApp share link opens correctly

> *Note:* Verification of additional sharing providers available through the "More" menu is outside the scope of this educational portfolio project — only the main visible sharing options are checked.

---

## *Home Page Footer*

- [ ] Footer is displayed on the Home page

### *Brand Information*

- [ ] MyWhoosh logo redirects to the Home page
- [ ] Email link opens the default email client

### *Navigation*

- [ ] Get Started page opens correctly
- [ ] About Us page opens correctly
- [ ] Download App page opens correctly
- [ ] Routes page opens correctly
- [ ] Ruleset page opens correctly
- [ ] Careers page opens correctly
- [ ] Terms and Conditions page opens correctly
- [ ] Troubleshoot page opens correctly

### *Community*

- [ ] Events page opens correctly
- [ ] Blog page opens correctly
- [ ] Results page opens correctly
- [ ] Media page opens correctly
- [ ] Teams page opens correctly
- [ ] Contact Us page opens correctly
- [ ] Support page opens correctly
- [ ] Privacy Notice page opens correctly
- [ ] Cookie Settings dialog opens correctly

### *Social Media*

- [ ] Facebook link opens the official Facebook page
- [ ] X (Twitter) link opens the official X page
- [ ] LinkedIn link opens the official LinkedIn page
- [ ] Instagram link opens the official Instagram page
- [ ] YouTube link opens the official YouTube channel
- [ ] Strava link opens the official Strava page
- [ ] Twitch link opens the official Twitch channel
- [ ] Discord link opens the official Discord server

---

## **Cross-Browser Compatibility**

- [ ] Website loads successfully in supported desktop browsers
- [ ] Navigation functions correctly in supported desktop browsers
- [ ] Download page functions correctly in supported desktop browsers
- [ ] No major visual differences are observed between supported desktop browsers

---

## **Accessibility**

- [ ] Images include alternative text where appropriate
- [ ] Interactive elements are accessible using keyboard navigation
- [ ] Form fields have associated labels
- [ ] Text and interactive elements have sufficient color contrast
- [ ] Visible focus indicators are displayed during keyboard navigation
