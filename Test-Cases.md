# Test Cases

Manual test cases for the MyWhoosh web application covering key user flows and related functional, validation, usability, accessibility scenarios.

## Contents

- [Login](#test-cases-login)

- Registration - in progress



## Test Cases — Login

## 1. Login page elements display

**Precondition:** User is on the login page.

**Steps:**

1. Verify that all required login page elements are displayed.

**Expected Result:**

The login page displays the following elements:

- "SIGN IN" heading
- "Using your MyWhoosh account" subtitle
- "Email Address" field
- "Password" field
- "Forgot Password?" link
- reCAPTCHA verification
- "Submit" button
- "Stay signed in" checkbox
- "Create New Account?" link

---

## 2. Successful login with valid credentials

**Precondition:** A registered, active user account exists.

**Steps:**

1. Enter a valid email address into the "Email Address" field.
2. Enter the correct password into the "Password" field.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** User is successfully authenticated and redirected to the appropriate authenticated page.

---

## 3. Password masking

**Precondition:** User is on the login page.

**Steps:**

1. Enter characters into the "Password" field.

**Expected Result:** Password characters are masked and are not displayed as plain text.

---

## 4. Login via Enter key

**Precondition:** Valid email and password are entered and reCAPTCHA verification is completed.

**Steps:**

1. Place the cursor in the "Password" field.
2. Press the `Enter` key.

**Expected Result:** The login form is submitted and behaves the same as clicking the "Submit" button.

---

## 5. Login with incorrect password

**Precondition:** User is on the login page.

**Steps:**

1. Enter a valid email address.
2. Enter an incorrect password.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected and an appropriate error message is displayed. The message does not unnecessarily reveal sensitive account information.

---

## 6. Login with non-existent email

**Precondition:** User is on the login page.

**Steps:**

1. Enter an email address that is not registered.
2. Enter any password.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected and an appropriate error message is displayed without unnecessarily revealing whether the email address is registered.

---

## 7. Empty required fields

**Precondition:** User is on the login page.

**Steps:**

1. Leave the "Email Address" and "Password" fields empty.
2. Click the "Submit" button.

**Expected Result:** Login is not performed and validation messages are displayed for the required fields.

---

## 8. Invalid email format

**Precondition:** User is on the login page.

**Steps:**

1. Enter an invalid email format (e.g., `testuser`) into the "Email Address" field.
2. Enter a valid-format password.
3. Click the "Submit" button.

**Expected Result:** The email field displays an appropriate validation message indicating that the entered email format is invalid.

---

## 9. Login attempt without completing reCAPTCHA

**Precondition:** Valid email and password are entered.

**Steps:**

1. Enter a valid email address.
2. Enter the correct password.
3. Leave the reCAPTCHA verification incomplete.
4. Click the "Submit" button.

**Expected Result:** Login is not performed and the user is prompted to complete the reCAPTCHA verification.

---

## 10. Successful login with "Stay signed in" enabled

**Precondition:** A registered, active user account exists.

**Steps:**

1. Enter a valid email address.
2. Enter the correct password.
3. Complete the reCAPTCHA verification.
4. Select the "Stay signed in" checkbox.
5. Click the "Submit" button.
6. Close the browser.
7. Reopen the browser and navigate to the MyWhoosh website.

**Expected Result:** The user remains authenticated and is not required to enter their credentials again.

---

## 11. Email with leading/trailing spaces

**Precondition:** A registered, active user account exists.

**Steps:**

1. Enter a valid email address with leading and/or trailing spaces (e.g., ` test@mail.com `).
2. Enter the correct password.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Leading and trailing spaces are ignored, and the user is successfully authenticated.

---

## 12. Email with spaces inside

**Precondition:** User is on the login page.

**Steps:**

1. Enter an email address containing spaces inside the address (e.g., `test @mail.com`).
2. Enter the correct password.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is not performed and an appropriate validation message is displayed indicating that the email address format is invalid.

---

## 13. Email case sensitivity

**Precondition:** User is registered with an email address such as `test@mail.com`.

**Steps:**

1. Enter the same email address using different letter casing (e.g., `Test@Mail.com`).
2. Enter the correct password.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login succeeds when the email address is entered with different letter casing.

---

## 14. Multiple failed login attempts

**Precondition:** User is on the login page.

**Steps:**

1. Enter a valid email address and an incorrect password.
2. Complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat the failed login attempt several times.

**Expected Result:** The application applies an appropriate protection mechanism after repeated failed login attempts, such as rate limiting, temporary lockout, additional verification, or a security warning.

---

## 15. "Forgot Password?" link navigation

**Precondition:** User is on the login page.

**Steps:**

1. Click the "Forgot Password?" link.

**Expected Result:** The password recovery page is opened.

---

## 16. "Create New Account?" link navigation

**Precondition:** User is on the login page.

**Steps:**

1. Click the "Create New Account?" link.

**Expected Result:** The registration page is opened.

---

## 17. Maximum password field length

**Precondition:** User is on the login page.

**Steps:**

1. Enter an excessively long string (e.g., 500+ characters) into the "Password" field.
2. Check how the field handles the input.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** The "Password" field handles excessively long input gracefully without breaking the page layout or causing the application to crash or freeze. If a maximum length is enforced, an appropriate validation message is displayed.

---

## 18. Submit button state

**Precondition:** User is on the login page.

**Steps:**

1. Check the initial state of the "Submit" button.
2. Enter a valid email address.
3. Check the state of the "Submit" button.
4. Enter a valid password.
5. Check the state of the "Submit" button.
6. Complete the reCAPTCHA verification.
7. Check the state of the "Submit" button.

**Expected Result:** The "Submit" button changes its state according to the form validation requirements. Its state is consistent after entering the email, password, and completing the reCAPTCHA verification.

---

## 19. Login with pasted password

**Precondition:** A registered, active user account exists and the correct password is copied to the clipboard.

**Steps:**

1. Enter the registered email address into the "Email Address" field.
2. Click into the "Password" field.
3. Paste the copied password using `Cmd+V`.
4. Complete the reCAPTCHA verification.
5. Click the "Submit" button.

**Expected Result:** The password is pasted correctly into the "Password" field, remains masked, and is accepted during authentication. The user is successfully logged in.

---

## 20. Browser autofill

**Precondition:** The browser has previously saved login credentials for the MyWhoosh website.

**Steps:**

1. Open the login page.
2. Select the saved credentials from the browser's autofill suggestion.

**Expected Result:** The saved email and password are populated into the corresponding fields correctly, and the password remains masked.

---

## 21. Keyboard navigation

**Precondition:** User is on the login page.

**Steps:**

1. Click into the "Email Address" field.
2. Press the `Tab` key repeatedly to move through the interactive elements.

**Expected Result:** Focus moves through all interactive elements in a logical and predictable order without skipping elements or becoming trapped.

---

## 22. Double-click on Submit

**Precondition:** Valid email and password are entered and reCAPTCHA verification is completed.

**Steps:**

1. Click the "Submit" button twice in quick succession.

**Expected Result:** The login action is processed only once. No duplicate session, error, or unexpected behavior occurs.

---

## 23. Password containing special characters

**Precondition:** A registered, active user account exists with a password containing special characters.

**Steps:**

1. Enter the registered email address.
2. Enter the correct password containing special characters.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** The password is accepted and the user is successfully authenticated.

---

## 24. Password containing leading/trailing spaces

**Precondition:** A registered, active user account exists and the account password is known to the tester.

**Steps:**

1. Enter the registered email address.
2. Enter the correct password, including leading and/or trailing spaces.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** The password is processed according to the application's authentication rules. Leading and trailing spaces are not silently removed or modified.

> **Note:** This test is not executable because a test account with a password containing leading and/or trailing spaces is not available.

---

## 25. reCAPTCHA failure or expiration

**Status:** Additional / Potentially time-consuming

**Precondition:** User is on the login page.

**Steps:**

1. Enter a valid email address.
2. Enter the correct password.
3. Complete the reCAPTCHA verification.
4. Leave the login page inactive until the reCAPTCHA verification expires.
5. Attempt to submit the login form.

**Expected Result:** Login is not performed and the user is clearly informed that reCAPTCHA verification must be completed again.

> **Note:** Execution depends on the reCAPTCHA expiration behavior and may require an extended waiting period.

---

## 26. Login with inactive or disabled account

**Precondition:** An inactive or disabled user account is required.

**Steps:**

1. Enter the email address of the inactive or disabled account.
2. Enter the correct password.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected and an appropriate message is displayed according to the account status.

> **Note:** This test is not executable because an inactive or disabled test account is not available. Backend and staging environment access are outside the scope of this portfolio project.

---

## 27. Browser Back/Forward navigation after login

**Precondition:** A registered, active user account exists.

**Steps:**

1. Log in with valid credentials.
2. Verify that the user is successfully authenticated.
3. Click the browser's **Back** button.
4. Click the browser's **Forward** button.

**Expected Result:** The application maintains the correct authentication state. The user is not unexpectedly logged out or granted access to authenticated content without valid authentication.

---

## 28. Login with network connection failure

**Precondition:** User has valid login credentials.

**Steps:**

1. Clear the browser cache and cookies for the MyWhoosh website.
2. Open the MyWhoosh login page.
3. Enter a valid email address.
4. Enter the correct password.
5. Complete the reCAPTCHA verification.
6. Open browser DevTools and set Network throttling to `Offline`.
7. Click the "Submit" button.

**Expected Result:** Login does not complete. An appropriate network error or retry message is displayed, and the login page remains usable without crashing or entering an unexpected state.

---

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
