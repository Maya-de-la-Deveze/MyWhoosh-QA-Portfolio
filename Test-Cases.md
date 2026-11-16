# Test Cases

Manual test cases for the MyWhoosh website covering key user flows and related functional, validation and usability scenarios.

## Contents

- [Login](#login)
- [Registration](#registration)
- Shop — planned
- Contact Form — planned

> **Note:** Each test case has a priority (High / Medium / Low). Test cases that cannot be executed are marked as **Blocked** in the test runs, with the reason stated in the test case. Out-of-scope testing types are listed in the [Testing Strategy](QA-Portfolio-Testing-Strategy.md#scope).

---

## Login

> **Test account:** Login test cases are executed with the dedicated test account `deveze.testing+recon@gmail.com`, which is registered and verified. Its password has 12 characters with uppercase and lowercase letters, digits and special characters (stored outside the repository).

### TC-LOGIN-01. Login page elements display

**Priority:** Medium

**Precondition:** The user is on the login page.

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

### TC-LOGIN-02. Successful login with correct credentials

**Priority:** High

**Precondition:** The test account is registered and verified. Its password has 12 characters with uppercase and lowercase letters, digits and special characters. The user is on the login page.

**Steps:**

1. Enter the email address of the test account into the "Email Address" field.
2. Enter the correct password of the test account into the "Password" field.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** The user is logged in. The header no longer shows "LOGIN" and shows the logged-in state instead.

---

### TC-LOGIN-03. Password masking

**Priority:** High

**Precondition:** The user is on the login page.

**Steps:**

1. Enter characters into the "Password" field.

**Expected Result:** Password characters are masked and are not displayed as plain text.

---

### TC-LOGIN-04. Login via Enter key

**Priority:** Medium

**Precondition:** The email address and the correct password of the test account are entered, and reCAPTCHA verification is completed.

**Steps:**

1. Place the cursor in the "Password" field.
2. Press the Enter key.

**Expected Result:** The login form is submitted and the user is logged in, the same as after clicking the "Submit" button.

---

### TC-LOGIN-05. Login with incorrect password

**Priority:** High

**Precondition:** The test account is registered and verified. The user is on the login page.

**Steps:**

1. Enter the email address of the test account.
2. Enter an incorrect password.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected and an error message is displayed. The message does not say whether the email or the password is wrong (e.g. "Invalid email or password").

---

### TC-LOGIN-06. Login with non-existent email

**Priority:** High

**Precondition:** The user is on the login page.

**Steps:**

1. Enter an email address that is not registered (`deveze.testing+notregistered@gmail.com`) into the "Email Address" field.
2. Enter `Test1234!` into the "Password" field.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected and the same error message as in [TC-LOGIN-05](#tc-login-05-login-with-incorrect-password) is displayed, so it is not possible to find out whether the email address is registered.

---

### TC-LOGIN-07. Empty required fields

**Priority:** High

**Precondition:** The user is on the login page.

**Steps:**

1. Leave the "Email Address" and "Password" fields empty.
2. Complete the reCAPTCHA verification.
3. Click the "Submit" button.

**Expected Result:** Login is not performed and validation messages are displayed for the required fields.

---

### TC-LOGIN-08. Invalid email format

**Priority:** High

**Precondition:** The user is on the login page.

**Test data:** `testuser` · `test@` · `test @mail.com` (space inside the address)

**Steps:**

1. Enter the first value from the test data (`testuser`) into the "Email Address" field.
2. Enter `Test1234!` into the "Password" field.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.
5. Repeat steps 1–4 for `test@` and `test @mail.com`.

**Expected Result:** For each value, login is not performed and a validation message for the "Email Address" field indicates that the email format is invalid.

> **Expected result is based on:** consistency with the registration form ([TC-REG-07](#tc-reg-07-invalid-email-format)): both forms of the product are expected to check the email format in the same way. The format check does not reveal any account information, unlike the account check in TC-LOGIN-05 and TC-LOGIN-06.

> **Note:** The result is recorded separately for each value. If a general error message (e.g. "Invalid email or password") is shown instead, the test case is marked as Failed with Minor severity.

---

### TC-LOGIN-09. Login attempt without completing reCAPTCHA

**Priority:** High

**Precondition:** The test account is registered and verified. The user is on the login page.

**Steps:**

1. Enter the email address of the test account.
2. Enter the correct password of the test account.
3. Leave the reCAPTCHA verification incomplete.
4. Click the "Submit" button.

**Expected Result:** Login is not performed and the user is prompted to complete the reCAPTCHA verification.

---

### TC-LOGIN-10. Successful login with "Stay signed in" enabled

**Priority:** Medium

**Precondition:** The test account is registered and verified. The user is on the login page. Chrome is set to open the New Tab page on startup (Settings → On startup), so that the previous session is not restored automatically.

**Steps:**

1. Enter the email address of the test account.
2. Enter the correct password of the test account.
3. Complete the reCAPTCHA verification.
4. Select the "Stay signed in" checkbox.
5. Click the "Submit" button.
6. Quit the browser completely (Cmd+Q).
7. Reopen the browser and navigate to the MyWhoosh website.

**Expected Result:** The user remains logged in and is not required to enter their credentials again.

---

### TC-LOGIN-11. Login with "Stay signed in" disabled

**Priority:** Medium

**Precondition:** The test account is registered and verified. The user is on the login page. Chrome is set to open the New Tab page on startup (Settings → On startup).

**Steps:**

1. Enter the email address of the test account.
2. Enter the correct password of the test account.
3. Complete the reCAPTCHA verification.
4. Leave the "Stay signed in" checkbox unselected.
5. Click the "Submit" button.
6. Quit the browser completely (Cmd+Q).
7. Reopen the browser and navigate to the MyWhoosh website.

**Expected Result:** The user is no longer logged in, and the header shows "LOGIN".

> **Expected result is based on:** common user experience. If the user stays logged in without "Stay signed in", the checkbox has no effect.

---

### TC-LOGIN-12. Email with leading/trailing spaces

**Priority:** Medium

**Precondition:** The test account is registered and verified. The user is on the login page.

**Steps:**

1. Enter the email address of the test account with leading and/or trailing spaces (e.g. `" deveze.testing+recon@gmail.com "`).
2. Enter the correct password of the test account.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Leading and trailing spaces are ignored, and the user is logged in.

> **Expected result is based on:** common user experience. Spaces around an email address are usually added by copying and pasting.

---

### TC-LOGIN-13. Email case sensitivity

**Priority:** Medium

**Precondition:** The test account is registered and verified. The user is on the login page.

**Steps:**

1. Enter the email address of the test account using different letter casing (e.g. `Deveze.Testing+Recon@Gmail.com`).
2. Enter the correct password of the test account.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login succeeds when the email address is entered with different letter casing.

> **Expected result is based on:** common user experience. Email providers, including Gmail, do not distinguish letter casing in email addresses.

---

### TC-LOGIN-14. Multiple failed login attempts

**Priority:** Medium

**Precondition:** The test account is registered and verified. The user is on the login page. A personal account is not used, as the account may be temporarily locked. This test case is executed last in the test run, after the Registration test cases.

**Steps:**

1. Enter the email address of the test account and an incorrect password.
2. Complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat steps 1–3 until 5 failed attempts have been made.
5. Log in with the correct password of the test account.

**Expected Result:** Each attempt requires a new reCAPTCHA verification. Each failed attempt shows the same error message as in [TC-LOGIN-05](#tc-login-05-login-with-incorrect-password). In step 5, the user is either logged in or a clear message about a temporary lock is displayed; both outcomes are acceptable.

> **Expected result is based on:** Google reCAPTCHA documentation: each reCAPTCHA response can be verified only once, so a new verification is needed for each attempt.

> **Note:** The number of attempts is limited to 5 to avoid generating unnecessary load on a production system. The lockout policy (number of attempts, lock duration) is not published, so whether the account is locked after 5 attempts is recorded as an observation, without a Passed/Failed status.

---

### TC-LOGIN-15. "Forgot Password?" link navigation

**Priority:** Medium

**Precondition:** The user is on the login page.

**Steps:**

1. Click the "Forgot Password?" link.

**Expected Result:** The password recovery page is opened.

---

### TC-LOGIN-16. "Create New Account?" link navigation

**Priority:** Medium

**Precondition:** The user is on the login page.

**Steps:**

1. Click the "Create New Account?" link.

**Expected Result:** The registration page is opened.

---

### TC-LOGIN-17. Password field handling of excessively long input

**Priority:** Low

**Precondition:** The user is on the login page.

**Steps:**

1. Enter an excessively long string (e.g. 500+ characters) into the "Password" field.
2. Verify how the field handles the input.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** The "Password" field handles excessively long input without breaking the page layout or causing the application to crash or freeze. If a maximum length is enforced, an appropriate validation message is displayed.

---

### TC-LOGIN-18. Login with pasted password

**Priority:** Medium

**Precondition:** The test account is registered and verified. Its correct password is copied to the clipboard. The user is on the login page.

**Steps:**

1. Enter the email address of the test account into the "Email Address" field.
2. Click the "Password" field.
3. Paste the copied password using Cmd+V.
4. Complete the reCAPTCHA verification.
5. Click the "Submit" button.

**Expected Result:** The password is pasted correctly into the "Password" field, remains masked, and is accepted. The user is logged in.

---

### TC-LOGIN-19. Double-click on Submit

**Priority:** Medium

**Precondition:** The email address and the correct password of the test account are entered, and reCAPTCHA verification is completed.

**Steps:**

1. Click the "Submit" button twice in quick succession.

**Expected Result:** The login action is processed only once. No duplicate session, error, or unexpected behavior occurs.

---

### TC-LOGIN-20. Correct password with an added trailing space

**Priority:** Medium

**Precondition:** The test account is registered and verified. The user is on the login page.

**Steps:**

1. Enter the email address of the test account.
2. Enter the correct password of the test account and add one space at the end.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected with the same error message as in [TC-LOGIN-05](#tc-login-05-login-with-incorrect-password). Spaces in the password are not silently removed.

---

### TC-LOGIN-21. reCAPTCHA expiration

**Priority:** Low

**Precondition:** The test account is registered and verified. The user is on the login page.

**Steps:**

1. Enter the email address of the test account.
2. Enter the correct password of the test account.
3. Complete the reCAPTCHA verification.
4. Leave the page inactive for at least 2 minutes.
5. Click the "Submit" button.

**Expected Result:** The reCAPTCHA verification expires and the checkbox is reset. Login is not performed until the reCAPTCHA verification is completed again.

> **Expected result is based on:** Google reCAPTCHA v2 documentation: a reCAPTCHA response is valid for two minutes.

---

### TC-LOGIN-22. Login with inactive or disabled account

**Priority:** Low

**Precondition:** An inactive or disabled account is required. The user is on the login page.

**Steps:**

1. Enter the email address of the inactive or disabled account.
2. Enter the correct password of the inactive or disabled account.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected and an appropriate message is displayed according to the account status.

> **Note:** Blocked — an inactive or disabled test account is not available. Backend and staging environment access are outside the scope of this portfolio project.

---

### TC-LOGIN-23. Browser Back/Forward navigation after login

**Priority:** Medium

**Precondition:** The test account is registered and verified. The login page is opened from the Home page.

**Steps:**

1. Log in with the test account.
2. Verify that the user is logged in.
3. Click the browser's **Back** button.
4. Click the browser's **Forward** button.

**Expected Result:** The user stays logged in after both steps. The login form is not submitted again, and no "Confirm Form Resubmission" warning or error page is shown.

---

### TC-LOGIN-24. Login with network connection failure

**Priority:** Low

**Precondition:** The test account is registered and verified.

**Steps:**

1. Open the MyWhoosh login page.
2. Enter the email address of the test account.
3. Enter the correct password of the test account.
4. Complete the reCAPTCHA verification.
5. Open browser DevTools and set Network throttling to `Offline`.
6. Click the "Submit" button.

**Expected Result:** Login does not complete. An appropriate network error or retry message is displayed, and the login page remains usable without crashing or entering an unexpected state.

---

## Registration

> **Execution order:** TC-REG-02 creates a new account (`deveze.testing+mywhoosh1@gmail.com`) for the registration and email verification checks. Before the verification link is opened, TC-REG-04 is executed; then TC-REG-03 and TC-REG-22. TC-REG-15 creates a child account (`deveze.testing+child1@gmail.com`). All other test cases do not create an account.
>
> **Validation test cases** (TC-REG-06 – TC-REG-14 and TC-REG-16 – TC-REG-19) use the already registered address `deveze.testing+recon@gmail.com`, unless the email field itself is tested. If an invalid value is unexpectedly accepted, the "already registered" message is shown and no extra account is created.
>
> **Dates** are given as DD.MM.YYYY; the "Date of birth" field shows them in the browser's date format.

### TC-REG-01. Registration page elements display

**Priority:** Medium

**Precondition:** The user is on the registration page (Login → "Create New Account?").

**Steps:**

1. Verify that all registration page elements are displayed.

**Expected Result:**

The registration page displays the following elements:

- "CREATE NEW ACCOUNT" heading and subtitle
- "First Name" and "Last Name" fields
- "Email Address" field
- "Gender" drop-down
- "Password" and "Confirm Password" fields
- "Select your Country" drop-down
- "Date of birth" field with a date picker
- "Weight (kg)" and "Height (cm)" fields
- Consent checkbox with "Privacy Notice" and "Terms & Conditions" links
- Newsletter checkbox ("I would like to receive news and updates from MyWhoosh.")
- reCAPTCHA verification
- "Submit" and "Cancel" buttons

---

### TC-REG-02. Successful registration with valid data

**Priority:** High

**Precondition:** The user is on the registration page. The email address `deveze.testing+mywhoosh1@gmail.com` has not been registered before.

**Test data:** First Name `Test` · Last Name `Deveze` · Email `deveze.testing+mywhoosh1@gmail.com` · Gender `Female` · Password: 12 characters with uppercase and lowercase letters, digits and special characters (stored outside the repository) · Country `Czech Republic` · Date of birth `18.11.1980` · Weight `70` · Height `175` · newsletter checkbox not selected

**Steps:**

1. Fill in all fields with the test data.
2. Select the consent checkbox.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.
5. Open the mailbox of the email address.

**Expected Result:** A message confirms that the account has been created and asks the user to verify the email address. A verification email from MyWhoosh arrives at the email address.

---

### TC-REG-03. Email verification and first login

**Priority:** High

**Precondition:** TC-REG-02 is passed and TC-REG-04 is executed. The verification email has not been opened yet.

**Steps:**

1. Open the verification email.
2. Click the verification link.
3. Click the "ENJOY YOUR RIDE" button.
4. Log in with the email address and the correct password of the account created in TC-REG-02.

**Expected Result:** The page "YOUR ACCOUNT HAS BEEN VERIFIED. THANK YOU!" is displayed. "ENJOY YOUR RIDE" opens a MyWhoosh page. The user can log in with the account created in TC-REG-02.

---

### TC-REG-04. Login before email verification

**Priority:** Medium

**Precondition:** TC-REG-02 is passed. The verification link has not been opened yet.

**Steps:**

1. Open the login page.
2. Enter the email address and the correct password of the account created in TC-REG-02.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Login is rejected with a message asking the user to verify the email address first.

---

### TC-REG-05. Submit button requires consent and reCAPTCHA

**Priority:** High

**Precondition:** The user is on the registration page.

**Steps:**

1. Fill in all fields with valid data. Check the state of the "Submit" button.
2. Select the consent checkbox. Check the state of the "Submit" button.
3. Clear the consent checkbox and complete the reCAPTCHA verification. Check the state of the "Submit" button.
4. Select the consent checkbox. Check the state of the "Submit" button.
5. Clear the consent checkbox. Check the state of the "Submit" button.

**Expected Result:** The "Submit" button is enabled only when both the consent checkbox is selected and the reCAPTCHA verification is completed. Otherwise, the button remains disabled. Registration is not possible without consent.

---

### TC-REG-06. Empty required fields

**Priority:** High

**Precondition:** The user is on the registration page.

**Steps:**

1. Leave all fields empty.
2. Select the consent checkbox.
3. Complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Registration is not performed. A validation message is displayed for each required field, and it is clear which fields are required.

> **Note:** The state of the "Submit" button depends only on the consent checkbox and the reCAPTCHA verification, not on the fields, so the button can be clicked with empty fields.

---

### TC-REG-07. Invalid email format

**Priority:** High

**Precondition:** The user is on the registration page. All other fields are filled with valid data.

**Test data:** `testuser` · `test@` · `test @mail.com` (space inside the address)

**Steps:**

1. Enter the first value from the test data (`testuser`) into the "Email Address" field.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat steps 1–3 for `test@` and `test @mail.com`.

**Expected Result:** For each value, registration is not performed and a validation message for the "Email Address" field indicates that the email format is invalid.

> **Note:** The result is recorded separately for each value.

---

### TC-REG-08. Registration with an already registered email

**Priority:** High

**Precondition:** An account with the email address `deveze.testing+recon@gmail.com` already exists. The user is on the registration page.

**Steps:**

1. Fill in all fields with valid data, using the already registered email address.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.

**Expected Result:** Registration is not performed. A message informs the user that an account with this email address already exists and suggests logging in or resetting the password. No second account is created.

---

### TC-REG-09. Password and Confirm Password do not match

**Priority:** High

**Precondition:** The user is on the registration page. All other fields are filled with valid data.

**Steps:**

1. Enter a valid password into the "Password" field.
2. Enter a different value into the "Confirm Password" field.
3. Select the consent checkbox and complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Registration is not performed and a validation message indicates that the passwords do not match.

---

### TC-REG-10. Password that does not meet the requirements

**Priority:** High

**Precondition:** The user is on the registration page. All other fields are filled with valid data.

**Test data:** `123` (too short) · `password` (letters only)

**Steps:**

1. Enter the first value from the test data (`123`) into the "Password" and "Confirm Password" fields.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat steps 1–3 for `password`.

**Expected Result:** For each value, registration is not performed and the message states the password requirements (e.g. minimum length, required character types).

> **Note:** The result is recorded separately for each value.

---

### TC-REG-11. Password masking

**Priority:** Medium

**Precondition:** The user is on the registration page.

**Steps:**

1. Enter characters into the "Password" field.
2. Enter characters into the "Confirm Password" field.

**Expected Result:** Characters in both fields are masked and are not displayed as plain text.

---

### TC-REG-12. Date of birth: minimum age of 6 years

**Priority:** High

**Precondition:** The user is on the registration page. The already registered address `deveze.testing+recon@gmail.com` is entered in the "Email Address" field. All other fields are filled with valid data.

**Test data:** the date exactly 6 years before the test date (boundary; e.g. `12.11.2020` when tested on 12.11.2026) · one day later (e.g. `13.11.2020`) · `03.02.2090` (future date)

**Steps:**

1. Type the first value from the test data (the boundary date) into the "Date of birth" field using the keyboard.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat steps 1–3 for the date one day later and for `03.02.2090`.

**Expected Result:** The boundary date is accepted (only the "already registered" message is shown). For the date one day later and for `03.02.2090`, registration is not performed and a message explains the minimum age.

> **Expected result is based on:** Terms & Conditions: "To be able to use the Site, App and Services, you must be at least 6 years of age or above."

> **Note:** An accepted date is shown by the "already registered" message (see [TC-REG-08](#tc-reg-08-registration-with-an-already-registered-email)) instead of a date error. This way no extra account is created. The result is recorded separately for each value.

---

### TC-REG-13. Date of birth: very old date

**Priority:** Medium

**Precondition:** The user is on the registration page. All other fields are filled with valid data.

**Steps:**

1. Type `03.02.1901` into the "Date of birth" field using the keyboard.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.

**Expected Result:** Registration is not performed and a validation message is displayed.

> **Note:** Whether the message states the allowed date range is recorded for the UX Review.

---

### TC-REG-14. Date of birth: non-existent date

**Priority:** Medium

**Precondition:** The user is on the registration page. All other fields are filled with valid data.

**Steps:**

1. Type `30.02.2000` into the "Date of birth" field using the keyboard.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.

**Expected Result:** Registration is not performed. The invalid date is rejected and a validation message is displayed.

> **Note:** The date is typed using the keyboard, because the date picker does not allow selecting a non-existent date.

---

### TC-REG-15. Registration of a user aged 6 to 18 requires parental consent

**Priority:** High

**Precondition:** The user is on the registration page. The email address `deveze.testing+child1@gmail.com` has not been registered before.

**Test data:** Email `deveze.testing+child1@gmail.com` · Date of birth exactly 10 years before the test date (e.g. `12.11.2016` when tested on 12.11.2026) · First Name, Last Name, Gender, Password, Country, Weight and Height as in the test data of [TC-REG-02](#tc-reg-02-successful-registration-with-valid-data)

**Steps:**

1. Fill in all fields with the test data.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.

**Expected Result:** The registration asks for the email address of a parent or legal guardian. The account is not activated until the parent or legal guardian gives consent by email.

> **Expected result is based on:** Terms & Conditions: "If you are between the ages of 6 and 18, you may register for an account only with parental consent." and "Parental consent is mandatory for account registration and will be verified through the parent's email address."

> **Note:** According to the Terms & Conditions, a child account without parental consent is deleted after one week.

---

### TC-REG-16. Weight: allowed range

**Priority:** Medium

**Precondition:** The user is on the registration page. The already registered address `deveze.testing+recon@gmail.com` is entered in the "Email Address" field. All other fields are filled with valid data.

**Test data:** `140` (boundary) · `141` · `0` · `-5` · letters `abc`

**Steps:**

1. Enter the first value from the test data (`140`) into the "Weight (kg)" field.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat steps 1–3 for `141`, `0`, `-5` and `abc`.

**Expected Result:** `140` is accepted (only the "already registered" message is shown). For `141`, the message "The weight field must be 140 or less" is displayed. `0` and `-5` are rejected with a validation message. The non-numeric value `abc` is not accepted.

> **Note:** An accepted value is shown by the "already registered" message (see [TC-REG-08](#tc-reg-08-registration-with-an-already-registered-email)) instead of a weight error. This way no extra account is created. The result is recorded separately for each value.

---

### TC-REG-17. Height: allowed range

**Priority:** Medium

**Precondition:** The user is on the registration page. The already registered address `deveze.testing+recon@gmail.com` is entered in the "Email Address" field. All other fields are filled with valid data.

**Test data:** `50` · `250` (boundaries) · `49` · `251` · letters `abc`

**Steps:**

1. Enter the first value from the test data (`50`) into the "Height (cm)" field.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat steps 1–3 for `250`, `49`, `251` and `abc`.

**Expected Result:** `50` and `250` are accepted (only the "already registered" message is shown). For `49` and `251`, the message "The height field must be between 50 and 250" is displayed. The non-numeric value `abc` is not accepted.

> **Note:** An accepted value is shown by the "already registered" message (see [TC-REG-08](#tc-reg-08-registration-with-an-already-registered-email)) instead of a height error. This way no extra account is created. The result is recorded separately for each value.

---

### TC-REG-18. Several validation errors at once

**Priority:** Medium

**Precondition:** The user is on the registration page. All other fields are filled with valid data.

**Steps:**

1. Enter `141` into the "Weight (kg)" field.
2. Enter `251` into the "Height (cm)" field.
3. Select the consent checkbox and complete the reCAPTCHA verification.
4. Click the "Submit" button.

**Expected Result:** Registration is not performed. Both validation messages are displayed at the same time, each next to its own field.

---

### TC-REG-19. First Name and Last Name validation

**Priority:** Medium

**Precondition:** The user is on the registration page. All other fields are filled with valid data.

**Test data:** only spaces · 300+ characters

**Steps:**

1. Enter the first value from the test data (only spaces) into the "First Name" field.
2. Select the consent checkbox and complete the reCAPTCHA verification.
3. Click the "Submit" button.
4. Repeat steps 1–3 with the second value from the test data (300+ characters).
5. Enter a valid value into the "First Name" field.
6. Repeat steps 1–4 for the "Last Name" field.

**Expected Result:** A name that contains only spaces is rejected with a validation message. A very long name is either limited to a maximum length or rejected with a validation message; the page layout is not broken.

> **Note:** The result is recorded separately for each value and each field.

---

### TC-REG-20. "Privacy Notice" and "Terms & Conditions" links

**Priority:** Medium

**Precondition:** The user is on the registration page. Some fields are already filled in.

**Steps:**

1. Click the "Privacy Notice" link.
2. Return to the registration page.
3. Click the "Terms & Conditions" link.
4. Return to the registration page.

**Expected Result:** Each link opens the corresponding document in a new tab. The registration page stays open, and the data already entered in the form is not lost.

---

### TC-REG-21. "Cancel" button

**Priority:** Low

**Precondition:** The registration page is opened from the login page (Login → "Create New Account?"). Some fields are already filled in.

**Steps:**

1. Click the "Cancel" button.

**Expected Result:** The registration form is closed without creating an account, and the login page is opened.

---

### TC-REG-22. Verification link opened a second time

**Priority:** Low

**Precondition:** TC-REG-03 is passed.

**Steps:**

1. Open the verification email again.
2. Click the verification link a second time.

**Expected Result:** A message informs the user that the account has already been verified. The user can still log in with the account created in TC-REG-02.
