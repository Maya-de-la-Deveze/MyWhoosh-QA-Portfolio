# **Test Cases — Login**

### 1. Login page elements display
**Precondition:** User has opened the login page.

**Steps:**
1. Observe the login form.

**Expected Result:** The following elements are displayed: "Email Address" and 
"Password" fields, reCAPTCHA checkbox ("No soy un robot"), "Submit" button, 
"Forgot Password?" link, "Stay signed in" checkbox, and "Create New Account?" link.

---

### 2. Successful login with valid credentials
**Precondition:** A registered, active user account exists.

**Steps:**
1. Enter a valid email into the "Email Address" field.
2. Enter the correct password into the "Password" field.
3. Check the reCAPTCHA checkbox.
4. Click the "Submit" button.

**Expected Result:** Login is successful; the user is redirected to the homepage 
or dashboard.

---

### 3. Password masking
**Precondition:** User is on the login page.

**Steps:**
1. Enter characters into the "Password" field.

**Expected Result:** Characters are displayed as dots or asterisks.

---

### 4. Login via Enter key
**Precondition:** Correct email and password are entered, reCAPTCHA is checked.

**Steps:**
1. Press the `Enter` key on the keyboard.

**Expected Result:** Login succeeds (same behavior as clicking "Submit").

---

### 5. Login with incorrect password
**Precondition:** User is on the login page.

**Steps:**
1. Enter a valid email.
2. Enter an incorrect password.
3. Check the reCAPTCHA checkbox.
4. Click "Submit".

**Expected Result:** Login is rejected; an error message is displayed (e.g. 
"Incorrect email or password").

---

### 6. Login with non-existent email
**Precondition:** User is on the login page.

**Steps:**
1. Enter an email that does not exist in the database.
2. Enter any password.
3. Check the reCAPTCHA checkbox.
4. Click "Submit".

**Expected Result:** Login is rejected; an error message is displayed.

---

### 7. Empty fields
**Precondition:** User is on the login page.

**Steps:**
1. Leave the "Email Address" and "Password" fields empty.
2. Click "Submit".

**Expected Result:** Login is not performed; validation hints appear under 
the required fields.

---

### 8. Invalid email format
**Precondition:** User is on the login page.

**Steps:**
1. Enter text without an `@` symbol or domain into the "Email Address" field 
   (e.g. `testuser`).
2. Fill in the "Password" field.
3. Click "Submit".

**Expected Result:** A warning about invalid input format is displayed.

---

### 9. Login attempt without completing reCAPTCHA
**Precondition:** Correct email and password are entered.

**Steps:**
1. Enter a valid email.
2. Enter the correct password.
3. Do not check the reCAPTCHA checkbox.
4. Click "Submit".

**Expected Result:** Login is not performed; a message requiring reCAPTCHA 
verification is displayed.

---

### 10. Successful login with "Stay signed in" enabled
**Precondition:** A registered, active user account exists.

**Steps:**
1. Enter a valid email.
2. Enter the correct password.
3. Check the reCAPTCHA checkbox.
4. Check the "Stay signed in" checkbox.
5. Click "Submit".
6. Close the page.
7. Reopen the page.

**Expected Result:** Login persists; on reopening, the dashboard is shown 
directly without requiring re-authentication.

---

### 11. Email with leading/trailing spaces
**Precondition:** A registered, active user account exists.

**Steps:**
1. Enter an email with a leading and/or trailing space (e.g. ` test@mail.com `).
2. Enter the correct password.
3. Check the reCAPTCHA checkbox.
4. Click "Submit".

**Expected Result:** Spaces are trimmed and login succeeds (or, if not trimmed, 
a clear error message is shown rather than a silent failure).

---

### 12. Email case sensitivity
**Precondition:** User is registered with a lowercase email (e.g. `test@mail.com`).

**Steps:**
1. Enter the same email in a different case (e.g. `Test@Mail.com`).
2. Enter the correct password.
3. Check the reCAPTCHA checkbox.
4. Click "Submit".

**Expected Result:** Login succeeds — email case does not affect authentication.

---

### 13. Multiple failed login attempts
**Precondition:** User is on the login page.

**Steps:**
1. Enter a valid email and an incorrect password.
2. Click "Submit".
3. Repeat steps 1–2 several times in a row (e.g. 5 times).

**Expected Result:** After a certain number of failed attempts, additional 
protection is triggered (e.g. temporary lockout, additional captcha, or 
warning message).

---

### 14. "Forgot Password?" link navigation
**Precondition:** User is on the login page.

**Steps:**
1. Click the "Forgot Password?" link.

**Expected Result:** User is redirected to the password recovery page.

---

### 15. "Create New Account?" link navigation
**Precondition:** User is on the login page.

**Steps:**
1. Click the "Create New Account?" link.

**Expected Result:** User is redirected to the registration page.

---

### 16. Maximum field length
**Precondition:** User is on the login page.

**Steps:**
1. Enter a very long string (500+ characters) into the "Email Address" field.
2. Enter a very long string (500+ characters) into the "Password" field.
3. Check the reCAPTCHA checkbox.
4. Click "Submit".
   
**Expected Result:** The form either limits input length gracefully or handles 
the long input without breaking the layout or crashing; a clear validation 
message is shown if the input is rejected.

---

### 17. Submit button state (enabled/disabled)
**Precondition:** User is on the login page.

**Steps:**
1. Observe the "Submit" button before filling in any fields.
2. Fill in "Email Address" and "Password" fields.
3. Observe the "Submit" button state again.
   
**Expected Result:** The button's enabled/disabled behavior is consistent — either 
active at all times, or disabled until required fields are filled, without 
inconsistent or unexpected states.

---

### 18. Password paste via Ctrl+V
**Precondition:** A password is copied to the clipboard.

**Steps:**
1. Click into the "Password" field.
2. Paste the copied password using `Ctrl+V` (or `Cmd+V`).
   
**Expected Result:** The password is pasted correctly into the field and 
displayed masked, same as manually typed input.

---

### 19. Browser autofill
**Precondition:** Browser has previously saved login credentials for this site.

**Steps:**
1. Open the login page.
2. Click into the "Email Address" field and select the browser's autofill 
   suggestion (if offered).

**Expected Result:** Email and password fields are correctly populated with 
the saved credentials, without corruption or mismatched values.

---

### 20. Keyboard navigation (Tab key)
**Precondition:** User is on the login page.

**Steps:**
1. Click into the "Email Address" field.
2. Press `Tab` repeatedly to move through the form.
   
**Expected Result:** Focus moves through form elements in a logical order 
(Email → Password → reCAPTCHA → Stay signed in → Submit, or similar), without 
skipping elements or jumping unpredictably.

---

### 21. Double-click on Submit during form processing
**Precondition:** Correct email and password are entered, reCAPTCHA is checked.

**Steps:**
1. Click "Submit" twice in quick succession.
   
**Expected Result:** The form is submitted only once; no duplicate login
requests are sent, and no error or duplicate session results from the 
double click.

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
