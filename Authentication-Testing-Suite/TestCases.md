# 🧪 Test Cases: Authentication Suite

## 1. Registration Module
| TC ID | Scenario | Steps | Expected Result |
|-------|----------|-------|-----------------|
| TC_REG_01 | Valid Registration | Enter valid email and strong password → Submit | Account created successfully; Welcome email sent. |
| TC_REG_02 | Duplicate Email | Enter an email that is already registered | Validation error: "Email already exists." |
| TC_REG_03 | Weak Password | Enter password missing requirements (e.g., no numbers) | Validation error showing missing password rules. |
| TC_REG_04 | Invalid Email Format | Enter email without @ symbol | Validation error: "Invalid email format." |

## 2. Login Module
| TC ID | Scenario | Steps | Expected Result |
|-------|----------|-------|-----------------|
| TC_LOG_01 | Valid Login | Enter correct email and password | User logged in to dashboard. |
| TC_LOG_02 | Invalid Password | Enter correct email, wrong password | Generic error: "Invalid credentials." |
| TC_LOG_03 | Unregistered Email | Enter email not in database | Generic error: "Invalid credentials." |
| TC_LOG_04 | Empty Fields | Click login with blank email/password | Validation error on required fields. |

## 3. Password Reset (Forgot Password)
| TC ID | Scenario | Steps | Expected Result |
|-------|----------|-------|-----------------|
| TC_PR_01 | Valid Password Reset Request | Enter registered email → Click "Forgot Password" | Reset link sent to user's email. |
| TC_PR_02 | Reset Password Execution | Click link → Enter new valid password | Password updated; user can log in. |
| TC_PR_03 | Unregistered Email | Enter unregistered email for reset | System shows "If email exists, a link was sent" (Security best practice). |
| TC_PR_04 | Expired Reset Link | Wait 24 hours → Click reset link | Link rendered invalid; error message. |
| TC_PR_05 | Reuse Reset Link | Use link, change password → Click link again | Link rendered invalid; error message. |

## 4. Security & Account Lockout
| TC ID | Scenario | Steps | Expected Result |
|-------|----------|-------|-----------------|
| TC_SEC_01 | Account Lockout | Enter wrong password 5 times consecutively | Account locked for designated time (e.g., 15 mins). |
| TC_SEC_02 | Session Timeout | Log in → leave browser idle for 30 minutes | User automatically logged out. |
| TC_SEC_03 | Concurrent Logins | Log in on Chrome → Log in on Firefox simultaneously | Earlier session invalidated (if policy requires). |
| TC_SEC_04 | Back Button After Logout | Log out → Click browser "Back" button | Cached pages might load, but any action redirects to Login. |
