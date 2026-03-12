# 📊 Authentication Suite – Test Execution Results

## 1. Execution Summary

| Metric | Count |
|--------|-------|
| **Total Test Cases** | 17 |
| **Passed** | 14 |
| **Failed** | 3 |
| **Blocked** | 0 |
| **Not Applicable** | 0 |

---

## 2. Module Breakdown

### 2.1 Registration Module (Pass Rate: 100%)
| TC ID | Scenario | Status |
|-------|----------|--------|
| TC_REG_01 | Valid Registration | ✅ Pass |
| TC_REG_02 | Duplicate Email | ✅ Pass |
| TC_REG_03 | Weak Password | ✅ Pass |
| TC_REG_04 | Invalid Email Format | ✅ Pass |

### 2.2 Login Module (Pass Rate: 75%)
| TC ID | Scenario | Status |
|-------|----------|--------|
| TC_LOG_01 | Valid Login | ✅ Pass |
| TC_LOG_02 | Invalid Password | ✅ Pass |
| TC_LOG_03 | Unregistered Email | ✅ Pass |
| TC_LOG_04 | Empty Fields | ❌ Fail (No validation message) |

### 2.3 Password Reset (Pass Rate: 80%)
| TC ID | Scenario | Status |
|-------|----------|--------|
| TC_PR_01 | Valid Password Reset Request | ✅ Pass |
| TC_PR_02 | Reset Password Execution | ✅ Pass |
| TC_PR_03 | Unregistered Email | ❌ Fail (Shows explicit "Email not found" instead of generic message, exposing user data) |
| TC_PR_04 | Expired Reset Link | ✅ Pass |
| TC_PR_05 | Reuse Reset Link | ✅ Pass |

### 2.4 Security & Account Lockout (Pass Rate: 75%)
| TC ID | Scenario | Status |
|-------|----------|--------|
| TC_SEC_01 | Account Lockout | ❌ Fail (User can attempt login infinite times) |
| TC_SEC_02 | Session Timeout | ✅ Pass |
| TC_SEC_03 | Concurrent Logins | ✅ Pass |
| TC_SEC_04 | Back Button After Logout | ✅ Pass |

---

## 3. Key Findings

Testing revealed three issues, two of which are high-severity security concerns:
1. **Missing Brute-Force Protection:** The system allows infinite login attempts without locking the account (TC_SEC_01).
2. **User Enumeration Vulnerability:** The "Forgot Password" feature confirms whether an email exists in the database or not, which is a security risk (TC_PR_03).
3. **Missing Client-Side Validation:** The Login form does not show validation errors when submitting entirely blank fields (TC_LOG_04).
