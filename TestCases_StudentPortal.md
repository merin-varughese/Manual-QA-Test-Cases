# Test Cases for Student Portal Enrollment

**Feature:** Course Registration and Schedule Viewing
**Scope:** Course search, enrollment, and schedule stability.

| TC ID | Test Type | Scenario | Test Step | Expected Result | Pass/Fail | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **S-001** | Positive | Student is logged in and has no holds on their account. | 1. Search for an available course (e.g., 'Math 101'). <br> 2. Click 'Enroll'. <br> 3. Confirm enrollment. | The student receives an **immediate confirmation message**, and the course appears instantly in their **'My Schedule'** view. | | **Happy Path** |
| **S-002** | Negative | Student is attempting to enroll in a course that is currently full (Capacity = 30; Enrolled = 30). | 1. Search for the full course. <br> 2. Click 'Enroll'. | The system displays a clear message stating **"Course is Full" or "Waitlist Only"**. Enrollment is blocked. | | **Capacity Constraint** |
| **S-003** | Edge (Prerequisite) | Student attempts to enroll in 'Calculus II' without having completed the prerequisite 'Calculus I'. | 1. Attempt to enroll in the advanced course. | The system displays a **specific error message** indicating the missing prerequisite course (e.g., "Prerequisite 'Calculus I' not met"). | | **Dependency Check** |
| **S-004** | Positive (Financial) | Student has a positive account balance. | 1. Navigate to the 'Financials' tab. <br> 2. Click 'Make Payment' and enter a valid amount less than the total balance. | The payment is processed, and the **'Current Balance' field updates instantaneously** to reflect the new remaining balance. | | **Data/Financial Integrity** |
| **S-005** | Negative (Session) | Student is logged in on their phone. | 1. The student closes the browser tab or app without logging out. <br> 2. After 15 minutes, the student attempts to open the app/tab again. | The student is redirected to the **login screen**, and the old session is invalidated due to an **automatic session timeout** for security. | | **Security/Session Management** |
