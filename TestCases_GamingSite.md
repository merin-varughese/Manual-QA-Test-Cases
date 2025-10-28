# Test Cases for Gaming Website

**Feature:** User Access and Content Loading
**Scope:** Login/Registration and Core Game Content Viewing.

| TC ID | Test Type | Scenario | Test Step | Expected Result | Pass/Fail | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **G-001** | Positive | User has valid, verified credentials. | 1. Navigate to the login page. <br> 2. Enter valid Username and Password. <br> 3. Click 'Sign In'. | User is successfully authenticated and redirected to the **Main Dashboard** or **Game Selection** page. | | **Happy Path** |
| **G-002** | Negative | User attempts to log in with an email address but no password. | 1. Navigate to the login page. <br> 2. Enter a valid email address. <br> 3. Leave the 'Password' field blank. <br> 4. Click 'Sign In'. | An immediate, clear **validation error message** (e.g., "Password is required") appears next to the password field. User remains on the login screen. | | **Missing Required Field** |
| **G-003** | Boundary | None. | 1. Click on the game thumbnail for the largest game file available. <br> 2. Wait for the game details page to load. | The page loads within **3 seconds**. All images, videos, and game descriptions display correctly without broken links or placeholders. | | **Performance/Load Time** |
| **G-004** | Positive (Navigation) | User is logged in. | 1. Navigate through three different game pages (A -> B -> C). <br> 2. Use the browser's 'Back' button. | The user successfully navigates back to **Page B**, then **Page A**, without session time-outs or page reload errors. | | **Browser Compatibility** |
| **G-005** | Negative (404) | None. | 1. Manually edit the browser URL to include a non-existent path (e.g., `/games/nonexistent-game-title`). | The site displays a custom, branded **'404 Page Not Found'** error, and the page contains a link back to the homepage. | | **Error Handling** |
