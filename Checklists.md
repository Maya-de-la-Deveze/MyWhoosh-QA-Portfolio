# MyWhoosh Website

## QA Checklist

*Based on the testing scope and priorities defined in the [Product Analysis](Product-Analysis.md) and [QA Portfolio Testing Strategy](QA-Portfolio-Testing-Strategy.md).*

### Table of Contents

- [Navigation](#navigation)
- [Get Started (How It Works)](#get-started-how-it-works)
- [Download](#download)
- [Subdomain Integration](#subdomain-integration)
- [Routes](#routes)
- [Events](#events)
- [Results](#results-resultsmywhooshcom)
- [Shop](#shop-storemywhooshcom)
- [Workout Builder](#workout-builder-workoutmywhooshcom)
- [UCI Cycling Esports World Championships](#uci-cycling-esports-world-championships-ucimywhooshcom)
- [Podcast](#podcast)
- [About Us](#about-us)
- [Home Page Footer](#home-page-footer)
- [Cross-Browser Compatibility](#cross-browser-compatibility)
- [Accessibility](#accessibility)

---

### **Navigation**

*Execution: included in this cycle*

- [ ] All main menu items are clickable and lead to the correct page
- [ ] Logo redirects to the homepage from any page
- [ ] No broken links (404) are found in the main navigation
- [ ] Main menu items, their order and labels are the same on all main website pages
- [ ] A non-existent URL shows a 404 page with a link back to the homepage

> **Note:** Footer link verification is covered separately in the [Home Page Footer](#home-page-footer) section.

---

> **Note:** Authentication flows (Login and Registration) are covered by dedicated [Test Cases](Test-Cases.md) due to their validation rules and multi-step workflows.

---
### **Get Started (How It Works)**

*Checks are performed without logging in.*

*Execution: not executed in this cycle*

- [ ] Get Started page loads and all sections are displayed (Get the App, The Essentials, Start Riding, What's New)
- [ ] "Download App" buttons open the download page (/getting-started-mywhoosh-cycling-app/)
- [ ] Each tab (Bike / Devices / Smart Trainer / Dictionary) shows its own content when selected
- [ ] Carousel switches slides automatically
- [ ] Carousel arrows move to the next and previous slide
- [ ] Each carousel slide shows its image and text
- [ ] Pagination indicators below the carousel switch between slides
- [ ] Partner logos are displayed in their categories (Bikes, Garage Items, Trainers, Partners, Team Partners) without broken images
- [ ] "View All" expands the full list of partners, and "View Less" collapses it
- [ ] Each partner logo opens the website of that partner

---

### **Download**

*Execution: included in this cycle*

*Checks are performed without logging in.*

- [ ] All supported platforms are listed (iOS, Android, MyWhoosh (Windows), MyWhoosh HD (Windows), macOS, Apple TV, Link app iOS, Link app Android)
- [ ] MyWhoosh, MyWhoosh HD and macOS buttons each start downloading their own installer
- [ ] iOS, Apple TV and Link app iOS buttons open the MyWhoosh app page in the App Store; Android and Link app Android buttons open it in Google Play

---

### **Subdomain Integration**

*Execution: included in this cycle*

MyWhoosh Web Ecosystem:

- Main Website — `mywhoosh.com`
- Results — `results.mywhoosh.com`
- Shop — `store.mywhoosh.com`
- Workout Builder — `workout.mywhoosh.com`
- UCI CEWC — `uci.mywhoosh.com`
- Authentication / User Account — `event.mywhoosh.com`

Checks:

- [ ] Shop menu item on `mywhoosh.com` opens `store.mywhoosh.com`
- [ ] Workout Builder menu item on `mywhoosh.com` opens `workout.mywhoosh.com`
- [ ] Results menu item on `mywhoosh.com` opens `results.mywhoosh.com`
- [ ] UCI CEWC menu item on `mywhoosh.com` opens `uci.mywhoosh.com`
- [ ] All subdomains open the same way from the main website (all in the same tab or all in a new tab)
- [ ] Login redirects users to the `event.mywhoosh.com` authentication page when required
- [ ] After logging in, the user stays logged in when moving to other subdomains that use the MyWhoosh account
- [ ] After logging out, the user is logged out on all subdomains that use the MyWhoosh account
- [ ] Browser Back returns the user to the previous page after moving between subdomains
- [ ] Each subdomain has a working link back to `mywhoosh.com`

---

### **Routes**

*Execution: not executed in this cycle*

*Checks are performed without logging in.*

- [ ] Routes page shows the side menu with all destinations
- [ ] Selecting a destination in the side menu shows its content and highlights it in the menu
- [ ] Destination page shows its title, description and background image
- [ ] Summary shows Total Routes, Total Distance (km) and Total Elevation Gain (m)
- [ ] Total Routes equals the number of routes in the table
- [ ] Total Distance and Total Elevation Gain equal the sums of the values in the table
- [ ] Routes table lists each route with its name, distance (km) and elevation (m), with no empty cells

> **Note:** The Official Partners block is shared across pages and is checked in [Get Started](#get-started-how-it-works)

---

### **Events**

*Execution: not executed in this cycle*

*Checks are performed without logging in.*

**Scope note:** Only the `/events/` listing page is covered. Event detail pages are opened only to verify card links and data; their functionality (e.g. Register Now, Requirements) is out of scope for this project.

- [ ] Event card elements (date, image, title, "Explore") all open the detail page of the same event (the page title matches the card title)
- [ ] Date, time, distance (km), and elevation (m) on each card match the event detail page and are not empty
- [ ] Upcoming events are listed in date order
- [ ] Event times are shown in GMT+4 regardless of the computer's time zone and browser language
- [ ] Each "Other Events / Ways To Ride" card shows its image, title and description

---

### **Results** (results.mywhoosh.com)

*Execution: included in this cycle*

*Checks are performed without logging in.*

#### Results List

*The main Results page with the list of all past events.*

- [ ] Selecting Men or Women shows only events of that gender (events marked "Both" are shown in each)
- [ ] Searching by the full name of an existing event returns that event
- [ ] A search with no matches shows the "No Events Found" message
- [ ] Selecting a category (Open, Category 1–4) shows only events that include that category (verified on the event results page)
- [ ] Selecting a date range shows only events within that range
- [ ] Selecting a date range with no events shows the "No Events Found" message
- [ ] Gender, search, category and date applied together show only events that match all of them
- [ ] "Reset" clears all filters and the search field and shows all events again
- [ ] All Events are listed from newest to oldest
- [ ] Each event card shows date, time, image, location, title, distance, elevation, number of players, gender and Official/Unofficial status
- [ ] Multi-stage event tabs (Overall, Stage 1, Stage 2) show the data of the selected stage
- [ ] "View Results" opens the results page of the same event (the page title matches the card title)
- [ ] Pagination shows different events on each page without duplicates, and "Next" opens the next page

#### Event Results

*The results table of a single event, opened via "View Results".*

> **Note:** Checks are performed on one representative event results page.

- [ ] Event date, distance and elevation at the top of the page match the event card in the Results list
- [ ] "Overall" tab is selected by default and shows the overall ranking
- [ ] Selecting a day (Day - 1, Day - 2) shows the results of that day
- [ ] After a day is selected, the Checkpoint 1–4 and Finish Line buttons each show the ranking at that checkpoint
- [ ] Selecting a category (Category - 1 to Category - 6) shows only participants of that category
- [ ] Typing in the category and day dropdowns filters their options
- [ ] Searching by the full name of a participant shows that participant
- [ ] A participant search with no matches shows an empty-state message
- [ ] Day, category and search applied together show only participants that match all of them
- [ ] Reset clears the day, category and search and shows the overall ranking again
- [ ] Rank numbers are sequential (1, 2, 3…) without gaps or duplicates
- [ ] In the Overall tab, participants are ordered by points from highest to lowest
- [ ] Each row shows rank, name, country flag, team, Avg (W/kg), Avg (W), Avg (HR), points and prize money
- [ ] Changing "Rows per page" changes the number of rows shown
- [ ] With more participants than rows per page, each page shows different participants without duplicates

---

### **Shop** (store.mywhoosh.com)

*Execution: partially included — see subsections*

*Checks are performed without logging in, unless stated otherwise.*

#### *Shop Home Page*

*Execution: not executed in this cycle*

- [ ] Header links Home, Shop and Contact Us open their pages
- [ ] Logo opens the Shop Home page
- [ ] Hero slider switches slides automatically and with the arrows
- [ ] "Shop Collection" button opens the Shop page
- [ ] Category cards (Active Wear, Jersey, Mug, Shirts) open their category pages
- [ ] "Women's Clothing" and "Men's Clothing" banners open their collection pages
- [ ] "Men's Jersey" and "Women's Jersey" banners open their product pages
- [ ] Product cards in Featured Product and Top Rating open their product pages
- [ ] Footer links open the corresponding pages
- [ ] "Back to top" button scrolls the page to the top

#### *Shop Page*

*Execution: not executed in this cycle*

- [ ] Category circles (Accessories, Active Wear, Bag, Bottles) open their category pages
- [ ] Each category in the Categories sidebar shows only products of that category
- [ ] The number next to each category matches the number of products shown when it is opened
- [ ] "Showing X–Y of Z item(s)" matches the products on the page and the total number of products
- [ ] "Sort by price: low to high" and "Sort by price: high to low" order products by price correctly
- [ ] "Sort by average rating" shows products with a higher rating first
- [ ] The selected sort order is kept when moving to the next page
- [ ] View mode buttons switch between the 2-, 3- and 4-column grids and the list layout
- [ ] Pagination shows different products on each page without duplicates
- [ ] Product cards open their product pages

#### *Product Page*

*Execution: included in this cycle*

- [ ] Breadcrumbs and category links open the corresponding category pages
- [ ] Thumbnails and arrows switch the main product image
- [ ] Product name, price, short description and the Description tab are displayed
- [ ] Color, Size and HS Code options can be selected
- [ ] After all options are selected, the stock quantity is shown (e.g. "11 in stock")
- [ ] "Add to Cart" and "Buy It Now" become active only after all options are selected
- [ ] Quantity "+" increases the quantity by 1; "−" decreases it by 1 and does not go below 1

#### *Cart Icon and Mini Cart*

*Execution: included in this cycle*

- [ ] The cart counter shows the total quantity of products in the cart
- [ ] The cart counter is the same on all Shop pages (Shop Home, Shop, product page, Cart)
- [ ] An empty Mini Cart shows "No products in the cart.", and "Go to shop" opens the Shop page
- [ ] Each Mini Cart item shows image, name, color, size, HS Code, quantity and unit price
- [ ] The Mini Cart total equals the sum of unit price × quantity
- [ ] "View Cart" opens the Cart page
- [ ] The × button removes the product from the Mini Cart

#### *Cart Page*

*Execution: included in this cycle*

- [ ] The "Shopping Cart" tab shows the number of items in the cart, e.g. "Shopping Cart (2)"
- [ ] Each row shows image, name, color, size, HS Code, price, quantity and subtotal
- [ ] Row subtotal equals price × quantity
- [ ] Subtotal in Cart totals equals the sum of row subtotals
- [ ] VAT equals 5% of the Subtotal (UAE VAT rate)
- [ ] Total equals Subtotal + VAT
- [ ] "Continue Shopping" opens the Shop page
- [ ] "Order Tracking" tab opens the Order Tracking page

> **Note:** Adding products, changing quantity, Update Cart, removing products and keeping the cart after login are covered by test cases TC-SHOP (in progress). Cart state persistence is covered by exploratory sessions ES-01 – ES-04.

#### *Checkout*

*Execution: included in this cycle*

- [ ] For a guest, "Proceed to Checkout", the Mini Cart "Check Out" button and the "Checkout" tab show "Login Required" with a "Go To Login" button

> **Note:** Payment and order placement are out of scope for this portfolio project. The Checkout page for logged-in users is not tested, and no orders are placed.

#### *Order Tracking*

*Execution: not executed in this cycle*

- [ ] Submitting with empty Order ID and Billing Email shows validation messages
- [ ] Submitting an invalid email format shows a validation message
- [ ] Submitting a non-existent Order ID shows an error message

> **Note:** Tracking a real order requires an existing order, which is out of scope for this portfolio project.

#### *Search*

*Execution: included in this cycle*

- [ ] Search icon opens the search panel, and "Close" closes it
- [ ] Results appear while typing and update with each character
- [ ] The character counter shows the number of characters entered (e.g. "2/50 characters")
- [ ] The search field does not accept more than 50 characters
- [ ] Searching by the full name of an existing product returns that product
- [ ] A search with no matches shows an empty-state message
- [ ] Each search result opens its product page

#### *Wishlist*

*Execution: included in this cycle*

- [ ] An empty Wishlist shows "There are no products on the Wishlist!"
- [ ] "Add to Wishlist" on the product page adds the product, and the wishlist counter increases by 1
- [ ] The heart icon on a product card on the Shop page adds the product to the Wishlist
- [ ] Each Wishlist item shows image, name, price, date added and stock status
- [ ] The × button removes the product, and the wishlist counter decreases by 1
- [ ] "Copy" copies the wishlist link to the clipboard
- [ ] The wishlist link opened in a private window shows the same products

#### *Account*

*Execution: included in this cycle*

- [ ] For a guest, the Account icon opens the MyWhoosh Sign In page
- [ ] After logging in, the Account icon opens the account page

> **Note:** Purchase history verification is out of scope for this portfolio project.

#### *Contact*

*Execution: included in this cycle*

- [ ] Contact page shows the map and the contact form (Full Name, Email Address, Subject, Message, reCAPTCHA, Submit)

> **Note:** Contact form validation is covered by test cases TC-CONTACT. Valid messages are not submitted, as they would reach the real MyWhoosh support team.

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

> *Note:* Verification of the footer, partner links, and social sharing services is outside the scope of this educational portfolio project and will be covered in separate checklists.

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

## **About Us**

- [ ] About Us dropdown opens on hover/click
- [ ] "About MyWhoosh" link opens the correct page
- [ ] "Leadership" link opens the correct page

### *About MyWhoosh*

- [ ] Page loads successfully without authentication
- [ ] Hero image and heading are displayed correctly
- [ ] "Get Started" CTA button navigates to the Get Started (How It Works) page
- [ ] Page content displays without layout shifts or overlapping text
- [ ] All images load correctly

### *Leadership*

- [ ] Page loads successfully without authentication
- [ ] Leadership team member cards/photos are displayed
- [ ] Content displays without layout issues

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
