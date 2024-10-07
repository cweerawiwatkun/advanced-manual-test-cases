{\rtf1\ansi\ansicpg874\cocoartf2761
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fnil\fcharset0 HelveticaNeue;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww28300\viewh17700\viewkind0
\deftab560
\pard\pardeftab560\slleading20\partightenfactor0

\f0\fs26 \cf0 # Advanced Manual Test Cases for Web Application Login\
\
## Test Case 1: Valid Login with Two-Factor Authentication (2FA)\
**Objective**: Verify that the user can successfully log in with valid credentials and complete the 2FA process.\
\
| Step No | Action                                                        | Expected Result                              |\
|---------|---------------------------------------------------------------|----------------------------------------------|\
| 1       | Open the login page.                                           | Login page is displayed.                     |\
| 2       | Enter a valid username and password.                           | Credentials are entered.                     |\
| 3       | Click the "Login" button.                                      | User is prompted to enter 2FA code.          |\
| 4       | Enter valid 2FA code (received via SMS or email).              | User is authenticated and redirected to the dashboard. |\
| 5       | Verify the welcome message and user session.                   | "Welcome, [username]" is displayed, session is active. |\
\
---\
\
## Test Case 2: Session Timeout\
**Objective**: Verify that the system logs the user out after a period of inactivity (session timeout).\
\
| Step No | Action                                         | Expected Result                              |\
|---------|------------------------------------------------|----------------------------------------------|\
| 1       | Log in with valid credentials.                 | User is logged in and redirected to dashboard. |\
| 2       | Leave the session idle for a period (e.g., 10 minutes). | Session is inactive, no interaction.         |\
| 3       | Try to interact with the page (e.g., click a button). | System logs out user and redirects to the login page. |\
| 4       | Verify the session timeout message.            | "Session expired, please log in again" message is displayed. |\
\
---\
\
## Test Case 3: Cross-Browser Testing\
**Objective**: Verify that the login functionality works correctly across different browsers (Chrome, Firefox, Safari).\
\
| Step No | Action                                        | Expected Result                              |\
|---------|-----------------------------------------------|----------------------------------------------|\
| 1       | Open the login page on Chrome, Firefox, and Safari. | Login page is displayed correctly in each browser. |\
| 2       | Enter valid credentials in each browser.      | Credentials are entered correctly.           |\
| 3       | Click the "Login" button in each browser.     | User is logged in and redirected to dashboard in all browsers. |\
| 4       | Verify that the layout and functionality work consistently. | Dashboard is correctly displayed and usable in each browser. |\
\
---\
\
## Test Case 4: Device Compatibility (Mobile and Desktop)\
**Objective**: Verify that the login functionality works correctly on both mobile and desktop devices.\
\
| Step No | Action                                      | Expected Result                              |\
|---------|---------------------------------------------|----------------------------------------------|\
| 1       | Open the login page on a mobile device (iOS/Android). | Login page is responsive and displayed correctly. |\
| 2       | Open the login page on a desktop browser.   | Login page is displayed correctly on desktop. |\
| 3       | Enter valid credentials on both devices.    | Credentials are entered correctly.           |\
| 4       | Click the "Login" button on both devices.   | User is logged in and redirected to dashboard on both devices. |\
| 5       | Verify the layout and functionality are consistent across devices. | Dashboard works and is displayed properly on both devices. |\
\
---\
\
## Test Case 5: Brute Force Attack Prevention\
**Objective**: Verify that the system prevents brute force attacks by locking the account after multiple failed login attempts.\
\
| Step No | Action                                               | Expected Result                              |\
|---------|------------------------------------------------------|----------------------------------------------|\
| 1       | Enter invalid username/password multiple times (e.g., 5 attempts). | System shows "Invalid credentials" for each attempt. |\
| 2       | On the 6th attempt, enter valid credentials.         | System locks the account and shows "Account locked due to multiple failed login attempts". |\
| 3       | Try to reset the password or contact support.        | System provides instructions for account recovery. |\
\
---\
\
## Test Case 6: SQL Injection Test\
**Objective**: Verify that the system is secure against SQL injection attacks by entering malicious SQL code in the login fields.\
\
| Step No | Action                                               | Expected Result                              |\
|---------|------------------------------------------------------|----------------------------------------------|\
| 1       | Open the login page.                                 | Login page is displayed.                     |\
| 2       | Enter malicious SQL code in the username field (e.g., `' OR 1=1; --`). | Input is sanitized and rejected by the system. |\
| 3       | Verify that the system does not log in or return sensitive information. | System shows "Invalid credentials" or similar message without compromising security. |\
\
---\
\
## Test Case 7: Password Strength Validation\
**Objective**: Verify that the system enforces strong password policies during password creation or reset.\
\
| Step No | Action                                               | Expected Result                              |\
|---------|------------------------------------------------------|----------------------------------------------|\
| 1       | Navigate to the password creation/reset page.        | Password reset page is displayed.            |\
| 2       | Enter a weak password (e.g., "12345").               | System shows "Password too weak" error.      |\
| 3       | Enter a password without special characters.         | System shows "Password must include at least one special character". |\
| 4       | Enter a valid strong password (e.g., `P@ssw0rd!123`). | System accepts the password and allows the user to proceed. |\
\
---\
\
## Test Case 8: CAPTCHA Verification\
**Objective**: Verify that CAPTCHA functionality is enforced to prevent automated login attempts after multiple failed logins.\
\
| Step No | Action                                               | Expected Result                              |\
|---------|------------------------------------------------------|----------------------------------------------|\
| 1       | Enter invalid credentials multiple times (e.g., 3 attempts). | System shows CAPTCHA after the 3rd attempt.  |\
| 2       | Try to log in without solving CAPTCHA.               | System prevents login and shows CAPTCHA validation error. |\
| 3       | Solve the CAPTCHA and log in with valid credentials. | System allows the login and redirects to the dashboard. |\
\
---}