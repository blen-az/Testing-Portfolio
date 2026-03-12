# 🐛 Authentication Suite – Bug Reports

## Summary
| Bug ID | Title | Module | Severity | Priority | Status |
|--------|-------|--------|----------|----------|--------|
| [BUG_AUTH_01](#bug_auth_01) | Missing Brute Force Protection (Account Lockout) | Security | Critical | High | 🔴 Open |
| [BUG_AUTH_02](#bug_auth_02) | User Enumeration via Forgot Password | Password Reset | High | Medium | 🔴 Open |
| [BUG_AUTH_03](#bug_auth_03) | Missing empty-field validation on Login | Login | Low | Low | 🔴 Open |

---

## Detailed Reports

### <a id="bug_auth_01"></a>BUG_AUTH_01: Missing Brute Force Protection (Account Lockout)
**Module:** Security / Login  
**Severity:** Critical | **Priority:** High | **Status:** Open

**Steps to Reproduce:**
1. Navigate to the Login Page.
2. Enter a registered email address.
3. Enter an incorrect password and submit.
4. Repeat step 3 for over 20 consecutive attempts.

**Expected Result:**
The system should lock the account or enforce an exponentially increasing delay (e.g., lock for 15 minutes after 5 failed attempts) to prevent brute-force credential stuffing.

**Actual Result:**
The system allows infinite continuous login attempts with no friction, CAPTCHA, or lockout mechanism.

**Impact:**
Attackers can run automated scripts to guess user passwords.

---

### <a id="bug_auth_02"></a>BUG_AUTH_02: User Enumeration via Forgot Password
**Module:** Password Reset  
**Severity:** High | **Priority:** Medium | **Status:** Open

**Steps to Reproduce:**
1. Navigate to the "Forgot Password" page.
2. Enter a completely random, unregistered email address (e.g., `doesnotexist123@test.com`).
3. Click Submit.

**Expected Result:**
The system should return a generic message to preserve privacy (e.g., "If this email is registered, a password reset link has been sent.").

**Actual Result:**
The system displays an error message: "Email address not found in our system."

**Impact:**
Malicious actors can use this endpoint to harvest valid email addresses and confirm if a user has an account on the platform.

---

### <a id="bug_auth_03"></a>BUG_AUTH_03: Missing empty-field validation on Login
**Module:** Login  
**Severity:** Low | **Priority:** Low | **Status:** Open

**Steps to Reproduce:**
1. Navigate to the Login Page.
2. Leave both the Email and Password fields completely blank.
3. Click "Sign In".

**Expected Result:**
Client-side validation errors should immediately highlight the missing required fields (e.g., "Email is required").

**Actual Result:**
The form submits to the server, and a generic "Invalid Credentials" response is returned from the backend. The required fields are not highlighted.

**Impact:**
Poor user experience (extra server round-trip) and confusing error messaging for simple mistakes.
