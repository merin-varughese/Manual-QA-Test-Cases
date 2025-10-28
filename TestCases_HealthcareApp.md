# Test Cases for Healthcare Patient Record System

**Feature:** Viewing and Editing Patient Data
**Scope:** Access control, data validation, and sensitive information display.

| TC ID | Test Scenario | Pre-condition | Test Step | Expected Result | Pass/Fail | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **H-001** | **Successful viewing of accurate patient medication data.** | Authorized Physician is logged in. Patient record is active and contains medication data. | 1. Select patient and navigate to the 'Medications' tab. <br> 2. View the list of active prescriptions. | All active prescriptions (Drug Name, Dosage, Dates) are displayed and match the **latest record stored in the database**. | |  |
| **H-002** | **Unauthorized user attempting to view sensitive data.** | Unauthorized User (e.g., Hospital Admin) is logged in without specific patient access privileges. | 1. Attempt to access a patient's **Social Security Number (SSN)** field via the UI. | The field is **masked or hidden** on the UI, and the system prevents viewing the raw data. | |  |
| **H-003** | **Data validation check for a future Date of Birth (DOB).** | User is entering a patient's Date of Birth (DOB). | 1. User attempts to enter a DOB one day **into the future**. <br> 2. Click 'Save' or 'Update'. | The system prevents saving and displays a clear **validation error** stating the DOB cannot be in the future. | | **Boundary Value** |
| **H-004** | **Verifying traceability after updating patient vital information.** | A Nurse updates a patient's 'Last Vitals Taken' timestamp. | 1. Update and save the timestamp field. <br> 2. Check the Audit Log via the backend. | The **Nurse's User ID** and the **exact field change** (Old Value -> New Value) are recorded in the immutable audit log. | | **Defect ID**|
| **H-005** | **Testing the system's ability to handle large text inputs in notes fields.** | Physician is entering notes in the 'Consultation Summary' text area. | 1. Paste in a block of text containing **10,000 characters**. <br> 2. Attempt to save the record. | The system either **saves the note successfully** or provides a clear, controlled error message stating the exact **maximum character limit** (e.g., 4000) before saving. | | **Input Handling** |
