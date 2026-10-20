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
- [Mobile Web](#mobile-web)

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

### **Workout Builder** (workout.mywhoosh.com)

*Execution: included in this cycle*

- [ ] Without logging in, the Workout Builder page opens and shows the Workouts, My Training Plans, MarketPlace and Subscriptions cards
- [ ] For a guest, "Explore" and "See Plans" open the MyWhoosh Sign In page
- [ ] Browser Back from the Sign In page returns the guest to the Workout Builder page
- [ ] Opening any section directly by URL without logging in shows a login prompt
- [ ] After logging in, the user is returned to the section that was requested
- [ ] For a logged-in user, each card opens its own section (Workouts, My Training Plans, MarketPlace, Subscriptions)

> **Note:** Creating, editing or buying workouts, training plans and subscriptions is out of scope for this portfolio project.

---

### **UCI Cycling Esports World Championships** (uci.mywhoosh.com)

*Execution: not executed in this cycle*

> **Note:** The page content changes with each championship (currently the 2026 UCI CEWC). Checks describe the page structure, not the content of a specific event.

#### *Header Navigation*

- [ ] "2026 UCI CEWC", "Event Details", "Event Gallery" and "Results" open their pages
- [ ] The highlighted button next to the menu (currently "Watch Semi-Final Recap Here") opens the Event Gallery page

#### *Hero Section*

- [ ] Event date and location are displayed
- [ ] "Explore" button opens the 2026 UCI CEWC page

#### *Latest Results*

- [ ] Latest Results shows the latest available results, or "Will be updated soon!" if there are none yet

#### *Latest Updates*

- [ ] Latest Updates shows timeline items from newest to oldest, each with its time and text

#### *Event Gallery*

- [ ] Event Gallery tabs (Live Coverage, Video Gallery, Image Gallery, Interviews) each show their own content

#### *Social Media and Download*

- [ ] Each social media icon (Facebook, LinkedIn, Instagram, X, YouTube, Strava, Twitch) opens the official page on that network
- [ ] "Download Now" opens the Download page

#### *Partners and Footer*

- [ ] Each UCI Official Partner logo (Shimano, Tissot, Santini) opens the partner's website
- [ ] Footer links FAQ and Contact us open their pages

---
### *Podcast*

*Execution: not executed — frozen baseline, see [Scope Freeze](QA-Portfolio-Testing-Strategy.md#scope-freeze)*

> **Note:** This checklist was written when "Podcast" was an item of the main menu. The menu item in this position later changed ("Podcast" → "Blog" → "MyWhoosh Hub"); "Blog" and "MyWhoosh Hub" open the same page. The Podcast page itself still exists and is linked from the footer and from the headers of some subdomains. The checklist is kept as a frozen baseline and is not executed.

> *Note:* Verification of the footer and partner links is outside the scope of this educational portfolio project and will be covered in separate checklists.

#### *Podcast Landing*

- [ ] Podcast page loads successfully
- [ ] Podcast subscription links are displayed
- [ ] Apple Podcasts link opens the official podcast page
- [ ] Spotify link opens the official podcast page
- [ ] YouTube link opens the official podcast page


#### *Episode Links*

- [ ] Apple Podcasts link opens the episode on Apple Podcasts
- [ ] Spotify link opens the episode on Spotify
- [ ] YouTube link opens the episode on YouTube


#### *Episodes*

- [ ] Featured episode is displayed
- [ ] Episode list is displayed
- [ ] Episode page opens correctly
- [ ] Podcast episode can be played
- [ ] Episode description is displayed


#### *Share*

- [ ] Share buttons are displayed
- [ ] Facebook share link opens correctly
- [ ] X (Twitter) share link opens correctly
- [ ] LinkedIn share link opens correctly
- [ ] WhatsApp share link opens correctly

> *Note:* Verification of additional sharing providers available through the "More" menu is outside the scope of this educational portfolio project — only the main visible sharing options are checked.

---

### **About Us**

*Execution: not executed in this cycle*

*Checks are performed without logging in.*

- [ ] Hovering over the About Us menu item opens a dropdown with "About MyWhoosh" and "Leadership"
- [ ] "About MyWhoosh" and "Leadership" open their pages

#### *About MyWhoosh*

- [ ] The page shows the "About MyWhoosh" heading and the Mission and Vision sections
- [ ] "Get Started" button opens the Get Started (How It Works) page

#### *Leadership*

- [ ] The page shows the message from the CEO with the CEO's name and title
- [ ] Board Members section lists each member with name and role

> **Note:** The Official Partners block is checked in [Get Started](#get-started-how-it-works). Page layout and images are evaluated in the UI Review.

---

### *Home Page Footer*

*Execution: not executed in this cycle*

*Checks are performed without logging in.*

> **Note:** These checks cover the footer of the main website (mywhoosh.com) only. Subdomains (event., results., store., workout., uci.) use different footers; the differences are documented as UI/UX observations for the UI Review.

#### *Brand Information*

- [ ] MyWhoosh logo opens the Home page
- [ ] The email link (support@mywhoosh.com) opens the default email client with the address filled in

#### *Navigation*

- [ ] Each link in the Navigation column (Get Started, About Us, Download App, Routes, Results, Careers, Terms and Conditions, Troubleshoot) opens its page

#### *Community*

- [ ] Each link in the Community column (Events, Podcast, Media, Teams, Contact Us, Support, Privacy Notice) opens its page
- [ ] "Cookie Settings" opens the cookie settings dialog

#### *Social Media*

- [ ] Each social media icon (Facebook, X, LinkedIn, Instagram, YouTube, Strava, Twitch, Discord) opens the official MyWhoosh page on that network

---

### **Cross-Browser Compatibility**

*Execution: included in this cycle*

> **Note:** Chrome and Safari on macOS (Tier 1) run the full execution scope. This section is the smoke set for Firefox on macOS (Tier 2), compared with Chrome. Mobile checks on iPhone are covered in [Mobile Web](#mobile-web).

- [ ] Home page loads with all blocks displayed, and main menu items open their pages
- [ ] Login with valid credentials succeeds, and the user stays logged in on workout.mywhoosh.com
- [ ] Download page buttons start the download or open the correct app store page
- [ ] In the Shop, a product with all options selected can be added to the cart, and the cart counter updates
- [ ] Fonts, spacing, images and alignment on the Home, Results and Shop pages look the same as in Chrome

---

### **Accessibility**

*Execution: included in this cycle*

> **Note:** Checks are performed on the Login and Download pages against WCAG 2.2 Level AA, using axe DevTools, Lighthouse and macOS VoiceOver with Safari. Findings are summarised in the Accessibility Review.

- [ ] All interactive elements can be reached and used with the keyboard only (Tab, Shift+Tab, Enter, Space)
- [ ] A visible focus indicator is shown on every focused element
- [ ] Form fields have labels that VoiceOver announces (e.g. "Email Address, text field")
- [ ] Form errors are shown as text, not only by colour, and VoiceOver announces them
- [ ] Informative images have meaningful alternative text; decorative images are ignored by VoiceOver
- [ ] Text contrast is at least 4.5:1 (3:1 for large text and UI components)
- [ ] Page content and functions remain available at 200% browser zoom

---

### **Mobile Web**

*Execution: included in this cycle*

> **Note:** Checks are performed on iPhone 12 Pro in Safari, in portrait orientation unless stated otherwise. Functionality already covered by other sections is not repeated; this section covers what is specific to a small touch screen.

- [ ] Home, Download, Results and Shop pages fit the screen width without horizontal scrolling
- [ ] The mobile menu opens and closes, and all main menu items are available in it
- [ ] About Us sub-items (About MyWhoosh, Leadership) can be opened by tap
- [ ] Download page: the iOS button opens the MyWhoosh app in the App Store app
- [ ] Login form: tapping the Email Address field opens the keyboard with "@", and the fields are not hidden by the keyboard
- [ ] Login with valid credentials succeeds, including reCAPTCHA completed by touch
- [ ] Event Results: the results table can be read; a wide table scrolls inside its block, not the whole page
- [ ] Shop: product options can be selected, the product can be added to the cart by tap, and the cart counter updates
- [ ] Carousels on the Home page can be swiped
- [ ] Rotating the phone to landscape and back keeps the layout intact, without overlapping or cut-off content
