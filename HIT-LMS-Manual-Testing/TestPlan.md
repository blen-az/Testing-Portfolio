# 📝 Test Plan: HIT LMS (Learning Management System)

## 1. Introduction
### 1.1 Objective
The objective of this manual testing phase is to ensure the functional stability, usability, and basic security of the core features of the **HIT Learning Management System (LMS)** staging environment before production rollout.

### 1.2 Scope
This test plan covers End-to-End (E2E) manual testing of the platform from both the **Learner** and **Instructor** perspectives. 
**In-Scope:**
- User Registration (Learner/Instructor)
- Authentication (Login/Logout, OTP, Session management)
- Course Discovery & Browsing
- Course Enrollment workflows
- Instructor Course Management (Create, Edit, Publish, Delete courses)
- Mobile Responsiveness (iOS)
- Basic Security and Negative testing

**Out of Scope:**
- Payment gateway processing (Staging limitation)
- Load & Performance testing
- Automated API testing

---

## 2. Test Strategy
### 2.1 Testing Types
- **Functional Testing:** Validating core features against expected behavior.
- **UI / UX Testing:** Ensuring layout, forms, and responsive design work smoothly on Laptop and Mobile browsers.
- **Negative Testing:** Intentionally invalid inputs (e.g., wrong passwords, missing data, invalid OTPs) to ensure graceful error handling.

### 2.2 Entry Criteria
- The staging environment URL is accessible.
- Valid test accounts (Learner & Instructor) are available or can be created.
- Test scenarios and this Test Plan are approved.

### 2.3 Exit Criteria
- 100% of defined Test Cases have been executed.
- All "High" and "Critical" severity bugs are documented and reported to the development team.
- A final Test Execution Report is generated and attached to the portfolio.

---

## 3. Test Environment

| Environment Type | Device | OS | Browser |
|------------------|--------|----|---------|
| **Functional Desktop** | Laptop | Windows / macOS | Google Chrome |
| **Mobile UI** | iPhone | iOS | Safari |

**Staging Details:**
- **Learner Frontend URL:** `https://hit-lms-frontend-production-ncfb4.ondigitalocean.app`
- **Instructor Portal URL:** `https://hit-lms-frontend-production-ncfb4.ondigitalocean.app/instructor/register`
- **Test OTP Code:** `123456`

---

## 4. Test Deliverables
The following artifacts will be produced and added to this QA Portfolio upon the completion of testing:
1. **[Test-Cases.md](./Test-Cases.md):** The comprehensive suite of E2E manual functional test cases.
2. **[TestResults.md](./TestResults.md):** The pass/fail status and metric summary of all executed test cases.
3. **[Bug-Reports.md](./Bug-Reports.md):** Detailed bug write-ups including replication steps and severity tracking.
4. **Screenshots Directory:** Visual evidence documenting failures and critical UI features.

---

## 5. Risks & Mitigation
| Risk | Impact | Mitigation |
|------|--------|------------|
| **Staging Environment Instability** | Blocks testing execution if server goes down. | Report downtime immediately to DevOps. Reroute testing to offline documentation if needed. |
| **Placeholder / Mock Data Limitations** | Prevents testing of downstream workflows (e.g. Certificate Generation). | Clearly document "Blocked" status for these specific flows in the final Test Results. |
