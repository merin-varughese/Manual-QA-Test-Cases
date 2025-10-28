# Test Cases for Healthcare Patient Record System

**Feature:** Viewing and Editing Patient Data
**Scope:** Access control, data validation, and sensitive information display.

| TC ID | Test Type | Scenario | Test Step | Expected Result | Pass/Fail | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **H-001** | Positive (Data View) | Authorized Physician is logged in. Patient record is active. | 1. Select patient and navigate to the 'Medications' tab. <br> 2. View the list of active prescriptions. | All active prescriptions (Drug Name, Dosage, Start/End Date) are displayed and match the **latest record stored in the database**. | |  |
| **H-002** | Negative (HIPAA/Security) | Unauthorized User (e.g., Hospital Admin without patient privileges) is logged in. | 1. Attempt to access a patient's **Social Security Number (SSN)** field directly via URL manipulation or database query attempt. | The field is **masked** on the UI, and the direct data access attempt is rejected, resulting in a **"Permission Denied"** server error logged in the security audit. | | |
| **H-003** | Edge (Data Validation) | User is entering a patient's Date of Birth (DOB). | 1. User attempts to enter a DOB one day **into the future**. <br> 2. Click 'Save'. | The system prevents saving and displays a clear, client-side and server-side **validation error** stating the DOB cannot be in the future. | | **Boundary Condition** |
| **H-004** | Positive (Audit Log) | A Nurse updates a patient's 'Last Vitals Taken' timestamp. | 1. Update and save the timestamp field. <br> 2. Check the Audit Log via the backend. | The **Nurse's User ID** and the **exact field change** (Old Value -> New Value) are recorded in the immutable audit log. | |  |
| **H-005** | Stress (Input) | Physician is entering notes in the 'Consultation Summary' text area. | 1. Paste in a block of text containing **10,000 characters**. <br> 2. Attempt to save the record. | The system either **saves the note successfully** or provides a clear, controlled error message stating the exact **maximum character limit** (e.g., 4000) before saving. | | **Input Handling** |
