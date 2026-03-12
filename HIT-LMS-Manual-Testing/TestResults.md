# 📊 HIT LMS – Test Execution Results

## 1. Test Execution Summary

| Metric | Count |
|--------|-------|
| **Total Test Cases** | 50 |
| **Passed** | 34 |
| **Failed** | 2 |
| **Blocked** | 11 |
| **Not Applicable** | 1 |

---

## 2. Learner Registration Results

| TC ID | Scenario | Expected Result | Actual Result | Status |
|-------|----------|-----------------|---------------|--------|
| TC_LR_01 | Valid Registration | Account created | Account created and logged in | ✅ Pass |
| TC_LR_02 | Invalid Phone | Validation error | Validation error shown | ✅ Pass |
| TC_LR_03 | Empty Field | Error displayed | Error displayed | ✅ Pass |
| TC_LR_04 | Valid OTP | Verification successful | Verification successful | ✅ Pass |
| TC_LR_05 | Invalid OTP | Error message | Error message shown | ✅ Pass |
| TC_LR_06 | Resend OTP | New OTP generated | Static OTP prevents testing | 🚧 Blocked |

---

## 3. Login Module Results

| TC ID | Scenario | Expected Result | Actual Result | Status |
|-------|----------|-----------------|---------------|--------|
| TC_LG_01 | Valid Login | User logged in | User logged in | ✅ Pass |
| TC_LG_02 | Wrong Password | Error message | Error displayed | ✅ Pass |
| TC_LG_03 | Unregistered Phone | Login blocked | Error displayed | ✅ Pass |
| TC_LG_04 | Empty Phone | Validation error | Validation error shown | ✅ Pass |
| TC_LG_05 | Empty Password | Validation error | Validation error shown | ✅ Pass |
| TC_LG_06 | Password Visibility Toggle | One toggle icon | Two icons displayed | ❌ Fail |
| TC_LG_07 | Session Persistence | Stay logged in after refresh | User remained logged in | ✅ Pass |
| TC_LG_08 | Logout | Redirect to login | Redirected | ✅ Pass |
| TC_LG_09 | Back After Logout | Dashboard inaccessible | Stayed on login page | ✅ Pass |
| TC_LG_10 | Network Failure | Network error | Error displayed | ✅ Pass |

---

## 4. Course Browsing Results

| TC ID | Scenario | Expected Result | Actual Result | Status |
|-------|----------|-----------------|---------------|--------|
| TC_CB_01 | View Course List | Course list visible | Course list visible | ✅ Pass |
| TC_CB_02 | View Course Detail | Detail page opens | Detail page opens | ✅ Pass |
| TC_CB_03 | Search Course | Relevant results | Results displayed | ✅ Pass |
| TC_CB_04 | Filter Courses | Filter applied | Filter works | ✅ Pass |

---

## 5. Course Enrollment Results

| TC ID | Scenario | Expected Result | Actual Result | Status |
|-------|----------|-----------------|---------------|--------|
| TC_EN_01 | Enroll in Course | Enrollment successful | Enrolled | ✅ Pass |
| TC_EN_02 | Prevent Re-Enrollment | Duplicate prevented | Continue Learning shown | ✅ Pass |
| TC_EN_03 | Course Access | Lessons accessible | Lessons opened | ✅ Pass |
| TC_EN_04 | Enroll in Full Course | Enrollment blocked | No full course available | 🚧 Blocked |
| TC_EN_05 | Inactive User | Enrollment blocked | All users active | 🚧 Blocked |
| TC_EN_06 | Paid Course | Redirect to payment | No paid courses available | 🚧 Blocked |
| TC_EN_07 | Enrollment Confirmation | Confirmation message | Confirmation displayed | ✅ Pass |
| TC_EN_08 | Cancel Enrollment | Enrollment removed | Feature not available | ⚪ N/A |

---

## 6. Instructor Module Results

| TC ID | Scenario | Expected Result | Actual Result | Status |
|-------|----------|-----------------|---------------|--------|
| TC_IN_01 | Instructor Login | Dashboard opens | Dashboard opens | ✅ Pass |
| TC_IN_02 | Create Course | Course created | Course created | ✅ Pass |
| TC_IN_03 | Add Module | Module saved | Module saved | ✅ Pass |
| TC_IN_04 | Add Lesson | Lesson visible | Lesson visible | ✅ Pass |
| TC_IN_05 | Publish Course | Visible to learners | Course visible | ✅ Pass |
| TC_IN_06 | Edit Course | Changes saved | Changes reflected | ✅ Pass |
| TC_IN_07 | Delete Course | Clear delete behavior | Disabled button without message | ❌ Fail |
| TC_IN_08 | View Students | Student list visible | List displayed | ✅ Pass |

---

## 7. Mobile Responsiveness Results

| TC ID | Scenario | Expected Result | Status |
|-------|----------|-----------------|--------|
| TC_UI_01 | Layout | No UI overlap | ✅ Pass |
| TC_UI_02 | Buttons | Clickable | ✅ Pass |
| TC_UI_03 | Forms | Usable | ✅ Pass |
| TC_UI_04 | Orientation | Adjusts properly | ✅ Pass |
| TC_UI_05 | Scrolling | Smooth scrolling | ✅ Pass |

---

## 8. Security Test Results

| TC ID | Scenario | Expected Result | Actual Result | Status |
|-------|----------|-----------------|---------------|--------|
| TC_SEC_01 | Access dashboard without login | Redirect to login | Redirected | ✅ Pass |
| TC_SEC_02 | Learner accessing instructor URL | Access denied | Access denied | ✅ Pass |

---

## 9. Key Findings

Two issues were identified during testing:
1. **Duplicate password visibility icons** on login and registration pages.
2. **Disabled delete button without explanation** in instructor course management.

Additionally, several features such as course completion and certificate generation could not be tested due to placeholder content in the staging environment.

## 10. Conclusion

The HIT LMS platform shows stable core functionality for registration, login, course browsing, enrollment, and instructor course management.

However, improvements are needed in UI clarity and workflow communication, particularly for instructor actions such as course deletion.